# Blocks

### Get Latest Block Info form block chain

{% hint style="info" %}
Note: the data is from explorer, May be a little delayed from the real data on-chain
{% endhint %}

```
https://explorer.rchapi.com/api/v1
   ?module=block
   &action=blocklatest
```

{% tabs %}
{% tab title="Request" %}
No Query Parameters
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "difficulty": "865980409",
        "extraData": "0xd883010910846765746888676f312e31372e37856c696e7578",
        "gasLimit": 8000000,
        "gasUsed": 0,
        "hash": "0xe63c302add140373dc859b6452b87aac30f497f678a87595d1c2795fef04bb7a",
        "miner": "0xe1afc49aad79e778735772ea12b7da1ddc1a6733",
        "nonce": "0x71919da91e1c9817",
        "number": 2667539,
        "parentHash": "0x74ef5d41745058e71280a2ecbf8d7a83623a17c9e3105e9d75390539792c3d38",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": 540,
        "stateRoot": "0x2e03def6506df7b3dde3d90e1c0b3fb55f02eb049332c3d0f3a3f19268c8ca26",
        "timestamp": 1652775531,
        "totalDifficulty": "2009981990840343",
        "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "txns": 0,
        "uncles": []
    }
}
```
{% endtab %}
{% endtabs %}

### Get Block Data By Hash

```
https://explorer.rchapi.com/api/v1
   ?module=block
   &action=getblockbyhash
   &hash=0x
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description                      | Type   |
| --------- | -------------------------------- | ------ |
| hash      | the block hash to get block data | string |
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "difficulty": "865980409",
        "extraData": "0xd883010910846765746888676f312e31372e37856c696e7578",
        "gasLimit": 8000000,
        "gasUsed": 0,
        "hash": "0xe63c302add140373dc859b6452b87aac30f497f678a87595d1c2795fef04bb7a",
        "miner": "0xe1afc49aad79e778735772ea12b7da1ddc1a6733",
        "nonce": "0x71919da91e1c9817",
        "number": 2667539,
        "parentHash": "0x74ef5d41745058e71280a2ecbf8d7a83623a17c9e3105e9d75390539792c3d38",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": 540,
        "stateRoot": "0x2e03def6506df7b3dde3d90e1c0b3fb55f02eb049332c3d0f3a3f19268c8ca26",
        "timestamp": 1652775531,
        "totalDifficulty": "2009981990840343",
        "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "txns": 0,
        "uncles": []
    }
}
```
{% endtab %}
{% endtabs %}





### Get Block Data By Block Number

```
https://explorer.rchapi.com/api/v1
   ?module=block
   &action=getblockbyblocknumber
   &number=34
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter   | Description                        | Type |
| ----------- | ---------------------------------- | ---- |
| blocknumber | the block number to get block data | int  |
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
    "code": 1,
    "message": "ok",
    "data": {
        "difficulty": "865980409",
        "extraData": "0xd883010910846765746888676f312e31372e37856c696e7578",
        "gasLimit": 8000000,
        "gasUsed": 0,
        "hash": "0xe63c302add140373dc859b6452b87aac30f497f678a87595d1c2795fef04bb7a",
        "miner": "0xe1afc49aad79e778735772ea12b7da1ddc1a6733",
        "nonce": "0x71919da91e1c9817",
        "number": 2667539,
        "parentHash": "0x74ef5d41745058e71280a2ecbf8d7a83623a17c9e3105e9d75390539792c3d38",
        "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
        "size": 540,
        "stateRoot": "0x2e03def6506df7b3dde3d90e1c0b3fb55f02eb049332c3d0f3a3f19268c8ca26",
        "timestamp": 1652775531,
        "totalDifficulty": "2009981990840343",
        "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
        "txns": 0,
        "uncles": []
    }
}
```
{% endtab %}
{% endtabs %}
