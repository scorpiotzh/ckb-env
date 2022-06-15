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