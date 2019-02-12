# Accelerator
Accelerator is a software component designed to improve the performance of a blockchain network, e.g. Hyperledger Fabric, in terms of transaction throughput. Accelerator enables the blockchain network to deal with a huge number of transaction requests from applications. 

This project, named Innovation Sandbox, provides tools and methods to download, test, and reproduce the improved performance results using Accelerator on Hyperledger Fabric. The intent is to enable blockchain developers to run it to see how much performance benefits they can expect in reproducible ways.

## Innovation Sandbox

### Caliper with Accelerator Adaptor 
Caliper is a blockchain performance benchmark framework which is one of the Hyperledger projects. This project, Innovation Sandbox, also uses Caliper to measure the improved performance by Accelerator. The project was generated by forking Caliper project, and a new adaptor module and smart contracts were added to utilize Accelerator.

- [Caliper User Guide](https://hyperledger.github.io/caliper)
- [Caliper Github](https://github.com/hyperledger/caliper)


### Getting Started
#### Prerequisites
To use Hyperledger Caliper, you must install the following tools in advance.
- NodeJS 8.X
- node-gyp
- Docker
- Docker-compose

##### Windows Extras
To mount `/var/run/docker.sock`, an environment variable may be exported. For more details, please visit the issue on [Github](https://github.com/docker/for-win/issues/1829#issuecomment-376328022).
- COMPOSE_CONVERT_WINDOWS_PATHS=1

Every drive used for volume mounting should be shared to be available from the containers. Please enable drive sharing on Docker Settings panel.

#### Installing
Install the node modules from `innovation-sandbox` folder via the npm executable command.
```bash
$ npm install
```
Install the modules for the fabric through the following command in that folder.
```bash
$ npm run fabric-v1.2-deps
```

#### Running the tests
The current version supports two benchmark scenarios, simple and smallbank which are provided by Caliper. 

Move to the benchmark scenario directory (e.g. `benchmark/simple`, `benchmark/smallbank` ) and run `main.js` with option.
For example, the following command executes the performance evaluation with Accelerator in 1 organization with 2 peers network.
```bash
$ node main.js -n ../../network/fabric-v1.2/1org2peeraccelerator/fabric-go.json
```

The command automatically downloads a docker image of Accelerator, configure Fabric network, and run benchmark tests.

## Whitepaper
Whitepaper includes:
- The key design features of Accelerator enabling high performance enterprise-wide blockchain technology
- The evaluation results that show the performance improvement of Hyperledger Fabric by Accelerator in practical scenarios
- The use cases that provide an insight for understanding industrial blockchain platforms

## Further information
For further information please contact Samsung SDS(nexledger.h@samsung.com).

