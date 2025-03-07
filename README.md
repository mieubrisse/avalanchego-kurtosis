# AvalancheGo Kurtosis Example

This repository includes examples for spinning up a local Avalanche network
using both [Kurtosis](https://www.kurtosistech.com/) and Docker Compose. Both
examples utlize [AvalancheGo](https://github.com/ava-labs/avalanchego), the
official node implementation for the Avalanche network.

# Kurtosis

_Configuration that will run AvalancheGo tests using the Kurtosis framework_

```
cd kurtosis
./scripts/build-and-run.sh all
```

It will:
* Create and boot up an image of the avalanche-testing suite
* Run tests against `avalanchego:latest`


## Docker Compose

_Configuration that will bootstrap a local Avalanche network using Docker
Compose_

```
cd docker-compose
docker-compose pull && docker-compose up
```

It will:
* Create 5 instances of `avalanchego:latest` and hook them together to bootstrap a local network
* Ensure you have the `avalanchego:latest` by doing a `docker-compose pull`
* Expose the API ports of the nodes on:

```
localhost:9650 -> node1:9650
localhost:9652 -> node2:9650
localhost:9653 -> node3:9650
localhost:9654 -> node4:9650
localhost:9655 -> node5:9650
```

* Expose the Staking ports of the nodes on:

```
localhost:9660 -> node1:9651
localhost:9662 -> node2:9651
localhost:9663 -> node3:9651
localhost:9664 -> node4:9651
localhost:9665 -> node5:9651
```
