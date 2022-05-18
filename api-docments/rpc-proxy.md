---
description: >-
  For the convenience of users, we proxy some RPC interfaces to facilitate users
  to use http requests to access
---

# RPC Proxy

{% hint style="info" %}
For the full documentation of available parameters and descriptions, please visit the official [**Ethereum JSON-RPC**](https://eth.wiki/json-rpc/API) docs.
{% endhint %}

### rch\_blockNumber

Returns the number of most recent block

```
http://192.168.0.154:9091/api/v1
?module=proxy
&action=rch_blockNumber
```

{% tabs %}
{% tab title="Request" %}
No parameters required.
{% endtab %}

{% tab title="Response" %}
Sample response

```
{
    "code": 1,
    "message": "ok",
    "data": "0x28be43"
}
```
{% endtab %}
{% endtabs %}

### rch\_getBlockByNumber

Returns the block info of the given block number

```
http://192.168.0.154:9091/api/v1
?module=proxy
&action=rch_getBlockByNumber
&blocknumber=0x234
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter   | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| blockNumber | the block number, in hex eg. `0xC36B3C` or a decimal number |
{% endtab %}

{% tab title="Response" %}
Sample response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "difficulty": "0x88b8",
        "extraData": "0xd883010910846765746888676f312e31352e34856c696e7578",
        "gasLimit": "0x7a1200",
        "gasUsed": "0x0",
        "hash": "0x7408323203f58ad2fed35029622457496fc185cce20e33552651ae13b69cd552",
        "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
        "miner": "0x47c25d26431ea4e7fa15f6a1dcbd6331d44e6617",
        "mixHash": "0x937c7addb9ea36af6a6143a21a3b6ceb532c439180754fa6bcc26e95f0204f4d",
        "nonce": "0x2ca03d594307c437",
        "number": "0x3042",
        "parentHash": "0xf572f4f70dcfdcb81e7a6fa30f944444ad13551e6abfb09bf7f31586ebf0d800",
        "receiptsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": "0x219",
        "stateRoot": "0x684a3d80357064f6b9a01aab182fec80103d2939e3581eb6a5324656b475666b",
        "timestamp": "0x5ff62230",
        "totalDifficulty": "0x11759cdf",
        "transactions": [],
        "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "uncles": []
    }
}

```
{% endtab %}
{% endtabs %}



### rch\_getBlockByHash

Returns the block info of the given hash

```
http://192.168.0.154:9091/api/v1
?module=proxy
&action=rch_getBlockByHash
&hash=0x234
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description    |
| --------- | -------------- |
| hash      | the block hash |
{% endtab %}

{% tab title="Response" %}
Sample response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "difficulty": "0x88b8",
        "extraData": "0xd883010910846765746888676f312e31352e34856c696e7578",
        "gasLimit": "0x7a1200",
        "gasUsed": "0x0",
        "hash": "0x7408323203f58ad2fed35029622457496fc185cce20e33552651ae13b69cd552",
        "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
        "miner": "0x47c25d26431ea4e7fa15f6a1dcbd6331d44e6617",
        "mixHash": "0x937c7addb9ea36af6a6143a21a3b6ceb532c439180754fa6bcc26e95f0204f4d",
        "nonce": "0x2ca03d594307c437",
        "number": "0x3042",
        "parentHash": "0xf572f4f70dcfdcb81e7a6fa30f944444ad13551e6abfb09bf7f31586ebf0d800",
        "receiptsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": "0x219",
        "stateRoot": "0x684a3d80357064f6b9a01aab182fec80103d2939e3581eb6a5324656b475666b",
        "timestamp": "0x5ff62230",
        "totalDifficulty": "0x11759cdf",
        "transactions": [],
        "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "uncles": []
    }
}
```
{% endtab %}
{% endtabs %}



### rch\_getTransactionByHash

Returns the transaction info of the given hash

```
http://192.168.0.154:9091/api/v1
?module=proxy
&action=rch_getTransactionByHash
&hash=0x234
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description          |
| --------- | -------------------- |
| hash      | the transaction hash |
{% endtab %}

{% tab title="Response" %}
Sample response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
        "blockNumber": "0x28be89",
        "from": "0xa1f3b0d5189c25ff45133a058aa1c428a24a3041",
        "gas": "0x175890",
        "gasPrice": "0x3b9aca00",
        "hash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
        "input": "0x38ed173900000000000000000000000000000000000000000000000540665406a3c27d890000000000000000000000000000000000000000000000003394af27e1771d0f00000000000000000000000000000000000000000000000000000000000000a0000000000000000000000000a1f3b0d5189c25ff45133a058aa1c428a24a304100000000000000000000000000000000000000000000000000000000628466590000000000000000000000000000000000000000000000000000000000000002000000000000000000000000e038beef31e21f85c33d279e95721e8d546b0cc5000000000000000000000000bb5b7bf5987fbc7b1026f2534d433fa922ce4740",
        "nonce": "0x9e86",
        "r": "0xd7b08dd16ea46e99bb9f7dfbba145dae1c27a55f15fa1b5427d207e8b8361a17",
        "s": "0x4eae5e7473bcc6126f3d0c0e925334f8990ce030fef07474cb7af254009c4d30",
        "to": "0x8c0d4fecf251b896a63e5cd25b5cb8dcfb2cbfed",
        "transactionIndex": "0x0",
        "v": "0xa7",
        "value": "0x0"
    }
}
```
{% endtab %}
{% endtabs %}



### rch\_getTransactionReceiptByHash

Returns the receipt transaction info of the given hash

```
http://192.168.0.154:9091/api/v1
?module=proxy
&action=rch_getTransactionReceiptByHash
&hash=0x234
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description          |
| --------- | -------------------- |
| hash      | the transaction hash |
{% endtab %}

{% tab title="Response" %}
Sample response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
        "blockNumber": "0x28be89",
        "contractAddress": null,
        "cumulativeGasUsed": "0x1a0fa",
        "from": "0xa1f3b0d5189c25ff45133a058aa1c428a24a3041",
        "gasUsed": "0x1a0fa",
        "logs": [
            {
                "address": "0xe038beef31e21f85c33d279e95721e8d546b0cc5",
                "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
                "blockNumber": "0x28be89",
                "data": "0x00000000000000000000000000000000000000000000000540665406a3c27d89",
                "logIndex": "0x0",
                "removed": false,
                "topics": [
                    "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
                    "0x000000000000000000000000a1f3b0d5189c25ff45133a058aa1c428a24a3041",
                    "0x0000000000000000000000009364bc6f2598bf22d1bda020b7c484bda595f730"
                ],
                "transactionHash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
                "transactionIndex": "0x0"
            },
            {
                "address": "0xbb5b7bf5987fbc7b1026f2534d433fa922ce4740",
                "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
                "blockNumber": "0x28be89",
                "data": "0x00000000000000000000000000000000000000000000000033d70a1612323ea7",
                "logIndex": "0x1",
                "removed": false,
                "topics": [
                    "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
                    "0x0000000000000000000000009364bc6f2598bf22d1bda020b7c484bda595f730",
                    "0x000000000000000000000000a1f3b0d5189c25ff45133a058aa1c428a24a3041"
                ],
                "transactionHash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
                "transactionIndex": "0x0"
            },
            {
                "address": "0x9364bc6f2598bf22d1bda020b7c484bda595f730",
                "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
                "blockNumber": "0x28be89",
                "data": "0x00000000000000000000000000000000000000000000057f3778aa52ee920a4f000000000000000000000000000000000000000000008e26043c8bbdd969cfe2",
                "logIndex": "0x2",
                "removed": false,
                "topics": [
                    "0x1c411e9a96e071241c2f21f7726b17ae89e3cab4c78be50e062b03a9fffbbad1"
                ],
                "transactionHash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
                "transactionIndex": "0x0"
            },
            {
                "address": "0x9364bc6f2598bf22d1bda020b7c484bda595f730",
                "blockHash": "0xa9bc9f8839961c8f4959b035bb0f949e10c209a71df0cce7f3e4260bb4f19b1e",
                "blockNumber": "0x28be89",
                "data": "0x000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000540665406a3c27d8900000000000000000000000000000000000000000000000033d70a1612323ea70000000000000000000000000000000000000000000000000000000000000000",
                "logIndex": "0x3",
                "removed": false,
                "topics": [
                    "0xd78ad95fa46c994b6551d0da85fc275fe613ce37657fb8d5e3d130840159d822",
                    "0x0000000000000000000000008c0d4fecf251b896a63e5cd25b5cb8dcfb2cbfed",
                    "0x000000000000000000000000a1f3b0d5189c25ff45133a058aa1c428a24a3041"
                ],
                "transactionHash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
                "transactionIndex": "0x0"
            }
        ],
        "logsBloom": "0x00200000000000080004000080000000000000000000000000000000000000000000000000000000000000000000000000000800000000000000000000000000000000000000000000000008000000200000000000000000000000000800000000000000000000000000000000000000000000000000000012000010000000000000000000000000000000000000000000000002000000080010004000001000000000080000000000000000000800002000000000000000000000000000000000000002000020100000000000000000000000000000001000000000000000040000020000000000000000000000100000000000000000000000000080000000",
        "status": "0x1",
        "to": "0x8c0d4fecf251b896a63e5cd25b5cb8dcfb2cbfed",
        "transactionHash": "0x4ece5ebf0fd55fbc9984367386c5ea26f683b6a8db67506cdeae6d43ccaf9da2",
        "transactionIndex": "0x0"
    }
}
```
{% endtab %}
{% endtabs %}
