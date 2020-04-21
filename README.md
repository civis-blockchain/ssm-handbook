# The Signing State Machines Handbook 

This is a comprehensive documentation for the [Signing State Machines](https://github.com/civis-blockchain/blockchain-ssm) Blockchain operation, with use cases and tutorials for the client SDKs.

## Getting started

### SSM Blockchain deployment

For an initial deployment, check the SSM [local deployment README](https://github.com/civis-blockchain/blockchain-ssm/tree/master/deployment/local).
You will need to install the binaries for [Hyperledger fabric v1.4](https://hyperledger-fabric.readthedocs.io/en/release-1.4/) or later.

In order to use a REST API, you can install the [Node.js REST server](https://github.com/civis-blockchain/ssm-sdk-js/blob/master/sdk/node/README.md) from the JS SDK.

### Client SDK

You can access the SSM blockchain with different SDk.

  * Command Line Interface - The [CLI SDK](https://github.com/civis-blockchain/blockchain-ssm/blob/master/sdk/cli/README.md) distributed with the SSM chaincode sources includes a [tutorial](https://github.com/civis-blockchain/blockchain-ssm/blob/master/sdk/cli/tutorial.md)
  * [JavaScript SDK](https://github.com/civis-blockchain/ssm-sdk-js) with a [Node.js REST server](https://github.com/civis-blockchain/ssm-sdk-js/blob/master/sdk/node/README.md) and a [REST client tutorial](https://github.com/civis-blockchain/ssm-sdk-js/blob/master/sdk/www/README.md) with a [development web app](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001).
  * The [Java SDK](https://github.com/civis-blockchain/ssm-sdk-java) supports also a REST server and development tools.
