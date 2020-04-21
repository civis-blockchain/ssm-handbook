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


## Modeling use cases with state machines

  *  [Transaction](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001&fcn=ssm&arg=Transaction)

```
{
  "name": "Transaction",
  "transitions": [
    {
      "from": 0,
      "to": 1,
      "role": "Initiator",
      "action": "Propose"
    },
    {
      "from": 1,
      "to": 2,
      "role": "Validator",
      "action": "Accept"
    }
  ]
}
```

  *  [Loop](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001&fcn=ssm&arg=Loop)

```
{
  "name": "Loop",
  "transitions": [
    {
      "from": 0,
      "to": 0,
      "role": "Looper",
      "action": "Loop"
    }
  ]
}
```

  *  [Operation request](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001&fcn=ssm&arg=Operation%20request)

```
{
  "name": "Operation request",
  "transitions": [
    {
      "from": 0,
      "to": 1,
      "role": "User",
      "action": "Request"
    },
    {
      "from": 1,
      "to": 0,
      "role": "Admin",
      "action": "Grant"
    },
    {
      "from": 1,
      "to": 0,
      "role": "Admin",
      "action": "Deny"
    }
  ]
}
```

  *  [Negociation](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001&fcn=ssm&arg=Negociation)

```
{
  "name": "Negociation",
  "transitions": [
    {
      "from": 0,
      "to": 1,
      "role": "Initiator",
      "action": "Propose"
    },
    {
      "from": 1,
      "to": 2,
      "role": "Validator",
      "action": "Accept"
    },
    {
      "from": 1,
      "to": 3,
      "role": "Validator",
      "action": "Reject"
    },
    {
      "from": 1,
      "to": 4,
      "role": "Validator",
      "action": "Amend"
    },
    {
      "from": 4,
      "to": 1,
      "role": "Initiator",
      "action": "Update"
    },
    {
      "from": 4,
      "to": 2,
      "role": "Initiator",
      "action": "Accept"
    },
    {
      "from": 4,
      "to": 3,
      "role": "Initiator",
      "action": "Reject"
    }
  ]
}
```

  *  [Triple treaty](http://lyriarte.free.fr/blockchain-ssm/index.html?host=peer1.pr-bc0.thingagora.org&port=8001&fcn=ssm&arg=Triple%20treaty)

```
{
  "name": "Triple treaty",
  "transitions": [
    {
      "from": 0,
      "to": 1,
      "role": "Agent 1",
      "action": "Sign"
    },
    {
      "from": 0,
      "to": 2,
      "role": "Agent 2",
      "action": "Sign"
    },
    {
      "from": 0,
      "to": 3,
      "role": "Agent 3",
      "action": "Sign"
    },
    {
      "from": 2,
      "to": 5,
      "role": "Agent 3",
      "action": "Sign"
    },
    {
      "from": 3,
      "to": 5,
      "role": "Agent 2",
      "action": "Sign"
    },
    {
      "from": 3,
      "to": 4,
      "role": "Agent 1",
      "action": "Sign"
    },
    {
      "from": 1,
      "to": 4,
      "role": "Agent 3",
      "action": "Sign"
    },
    {
      "from": 4,
      "to": 6,
      "role": "Agent 2",
      "action": "Sign"
    },
    {
      "from": 5,
      "to": 6,
      "role": "Agent 1",
      "action": "Sign"
    },
    {
      "from": 1,
      "to": 7,
      "role": "Agent 2",
      "action": "Sign"
    },
    {
      "from": 2,
      "to": 7,
      "role": "Agent 1",
      "action": "Sign"
    },
    {
      "from": 7,
      "to": 6,
      "role": "Agent 3",
      "action": "Sign"
    }
  ]
}
```

