## Setup & Run Blockscout Explorer on your Network with (Docker Approach)

### Pre-requisites:
- Required the RPC and Websocket URLs of the Network
- Required the Chain ID of the Network
- Required the ETHEREUM_JSONRPC_VARIANT name
  - We need to create the elixir file with the name of the above variant in the production folder at path apps/explorer/config/prod 
  - In general, you can use these variant names (geth, ganache)
- Docker Install in your machine
- [General Requirements](https://docs.blockscout.com/for-developers/information-and-settings/requirements) Tools must installed

### Step 1:
- Clone the main repo of [blockscout](https://github.com/blockscout/blockscout)
- Open the repo in VSCode IDE

### Step 2:
- Replace the variable below variable in the ```common-blockscout.env``` file at the path
```docker-compose/envs/common-blockscout.env```
```
ETHEREUM_JSONRPC_VARIANT
ETHEREUM_JSONRPC_HTTP_URL
ETHEREUM_JSONRPC_TRACE_URL
COIN_NAME
```

### Step 3: 
- Replace below environment variables in the ```docker-compose/docker-compose.yml``` file

```
   environment:       
	 ETHEREUM_JSONRPC_HTTP_URL: https://testnet.rebus.money/rpc
       ETHEREUM_JSONRPC_TRACE_URL: https://testnet.rebus.money/rpc
       ETHEREUM_JSONRPC_WS_URL: wss://testnet.rebus.money/ws
       CHAIN_ID: '3333'
```

### Step 4:
- Start the docker desktop
- In the repo run the following commands in sequence
  - ```cd ./docker-compose```
  - ```docker-compose up --build```

#### Explorer Runs at
[http://127.0.0.1](http://127.0.0.1/)
