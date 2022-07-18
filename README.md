# ckb-env

## Install & Run

### Prepare environment

First of all, you need a ubuntu server environment(>= 18.4, 2C4G and 200GB SSD).

Then you need docker(>= 20.10) and its compose plugin and they can be installed with following commands:

```shell
sudo apt update
sudo apt install docker
sudo apt install docker-compose-plugin
```

After install, remember check your binary version with:

```shell
$: docker -v
Docker version 20.10.16, build aa7e414 # example ourput, maybe different on your machine
$: docker compose version
Docker Compose version v2.5.0 # example ourput, maybe different on your machine
```

### Run and debug

* mainnet: use the file `ckb.mainnet.toml`,`ckb-miner.mainnet.toml`
* testnet: use the file `ckb.testnet.toml`,`ckb-miner.testnet.toml`, and change `CKB_NETWORK=testnet` in file `.env`
* chasing blocks for 24 hours to 48 hours.

```shell
git clone https://github.com/scorpiotzh/ckb-env.git
cd ckb-env

cp docker-compose.example.yaml docker-compose.yaml
vim docker-compose.yaml

cp .env.example .env
vim .env 

cp ckb-node/ckb.*.toml ckb-node/ckb.toml
cp ckb-node/ckb-miner.*.toml ckb-node/ckb-miner.toml 
```

* inspect the api of ckb node

```shell
curl --location --request POST 'http://127.0.0.1:8114' \
--header 'Content-Type: application/json' \
--data-raw '{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "get_tip_header",
  "params": []
}'
```

* inspect the api of ckb indexer

```shell
curl --location --request POST 'http://127.0.0.1:8116' \
--header 'Content-Type: application/json' \
--data-raw '{
  "id": 1,
  "jsonrpc": "2.0",
  "method": "get_tip",
  "params": null
}'

```
