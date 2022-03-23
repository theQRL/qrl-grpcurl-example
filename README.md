# qrl-grpc-cli

Example use of ``grpcurl`` to interact with a QRL node

## Requirements

- [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm)
- [grpcurl](https://github.com/fullstorydev/grpcurl)
- [jq](https://stedolan.github.io/jq/download/) (recommended)

## Use

1. Clone this repository & change to dir
2. Run ``npm install`` (a post-install script will ensure the google protos are installed in the correct location for use)
3. Access QRL GRPC API calls!  See the enclosed ``qrl.proto`` file or [the api docs](https://api.theqrl.org/#qrl-api) for more details.

## Example

``grpcurl -plaintext -proto qrl.proto mainnet-1.automated.theqrl.org:19009 qrl.PublicAPI/GetStats | jq``

->

```
{
  "nodeInfo": {
    "version": "3.0.1 python",
    "state": "SYNCED",
    "numConnections": 70,
    "numKnownPeers": 692,
    "uptime": "33277",
    "blockHeight": "1975583",
    "blockLastHash": "su1Gwq7a0FfZAWGyjzyFZmRF5+RFFsaJpc0oOAAAAAA=",
    "networkId": "The sleeper must awaken"
  },
  "epoch": "19755",
  "uptimeNetwork": "118012440",
  "blockLastReward": "1916549323",
  "coinsTotalSupply": "105000000",
  "coinsEmitted": "76098819798463188"
}
```