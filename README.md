# Koinos contracts AS

In this repo there are several contracts for koinos blockchain written in assemblyscript.

## Installation

Run `yarn install` to install the required dependencies.

Create a copy of `env.example`, rename it to `.env`, and update its values as explained in the file. This will be needed for the deployment and interaction with the contracts.

## Token Contract

This is a contract to deploy any type of token. Go to `contracts/token/assembly/Token.ts` to update `_name`, `_symbol`, and `_decimals` with your preferred values.

Run:

```
yarn token:build
```

This will make a precompilation in the `contracts/token/build` folder, and it will build the final compilation in `contracts/token/build/release/token.wasm`.

Finally deploy the contract:

```
yarn token:deploy
```

Now you can consult a blockexplorer, like koinosblocks.com to check your deployment

## Verify code

In order to verify the authenticity of the deployed code, this repo contains a Dockerfile to compile the code and get the wasm file with its corresponding sha256 identifier. Then these values can be compared with the code deployed in the blockchain to prove its authenticity.

Run:

```
yarn token:docker
```

You should see at the end some info from the contract selected:

```
contract: token
file:     /contracts/contracts/token/build/release/token.wasm
size:     35743 bytes (34.91 kB)
sha256:   b431afde0d72b4398584784c8142de9d7f33452294917af6c402cc0f70f9b85f
```

## Acknowledgments

Many thanks to the sponsors of this work: @levineam, @Amikob, @motoeng, @isaacdozier, @imjwalker, and the private sponsors.

If you would like to contribute to the maintenance and development of these and more contracts consider becoming a sponsor in https://github.com/sponsors/joticajulian.

## License

MIT License

Copyright (c) 2022 Julián González

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
