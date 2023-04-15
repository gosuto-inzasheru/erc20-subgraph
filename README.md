# ERC20 Subgraph: Approvals

Inspired by [`erc20-subgraph`](https://thegraph.com/explorer/subgraph/georgeroman/erc20-subgraph), `erc20-subgraph-approvals` indexes all approvals on ERC20-compliant tokens.

## Installation
In a first terminal, have a local instance of [`ganache`](https://trufflesuite.com/ganache/) running on IP address `0.0.0.0`:
```
ganache-cli -h 0.0.0.0
```

Then in a second terminal, fire up The Graph's local dockerised [Graph Node](https://github.com/graphprotocol/graph-node):
```
$ cd ..
$ git clone git@github.com:graphprotocol/graph-node.git
$ docker-compose up
```

Be sure to note the [additional instructions here](https://github.com/graphprotocol/graph-node/tree/master/docker) in case you are running on a non-intel MacBook.

Finally, in a third terminal, navigate back to the `erc20-subgraph-approvals` repo and deploy the subgraph locally:
```
$ cd ../erc20-subgraph-approvals
yarn install && yarn codegen && yarn build && yarn create-local && yarn deploy-local
```

The subgraph can now be queried at `http://localhost:8000/subgraphs/name/gosuto-inzasheru/erc20-subgraph-approvals/`.

Ganache (raw RPC calls) logs to stdout in its terminal, as does the graph node (via docker stdout).
