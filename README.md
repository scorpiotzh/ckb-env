# ckb-env

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