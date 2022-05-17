---
description: Account-related HTTP requests.
---

# Accounts

### Get RCH balance for a Single Address

Returns the RCH balance of a given address

```
https://explorer.rchapi.com/api/v1
?module=account
&action=balance
&address=0x3f349bBaFEc1551819B8be1EfEA2fC46cA749aA1
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description                                                                                                          |
| --------- | -------------------------------------------------------------------------------------------------------------------- |
| address   | the string representing the address to check for balance                                                             |
| tag       | the string pre-defined block parameter, either earliest, pending or latest, if null the result is from the database. |
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
   "status":"1",
   "message":"OK",
   "data":"154476596514118000947297331"
}

```

> :book: **Tip:** The `data` is returned in <mark style="color:yellow;">**wei**</mark>**.**  1 <mark style="color:yellow;">**RCH**</mark> = 10\*\*18 <mark style="color:yellow;">**wei**</mark>
{% endtab %}
{% endtabs %}

### Get  Balance for Multiple Addresses in a Single Call

Returns the balance of the accounts from a list of addresses.

```
https://explorer.rchapi.com/api/v1
?module=account
&action=balancemlti
&address=0x3f349bBaFEc1551819B8be1EfEA2fC46cA749aA1,0x4bF01a5A576bE1254C5E19fbE5EB195D6cFBeBdD
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

|         |                                                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| address | <p>the <code>strings</code> representing the addresses to check for balance, separated by <code>,</code> commas<br><br>up to <strong>20</strong> <strong>addresses</strong> per call</p> |
| tag     | the string pre-defined block parameter, either earliest, pending or latest, if null the result is from the database.                                                                     |
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
   "code":"1",
   "message":"msg",
   "data":[
      {
         "account":"0x3f349bBaFEc1551819B8be1EfEA2fC46cA749aA1",
         "balance":"37700000000000001"
      },
      {
         "account":"0x4bF01a5A576bE1254C5E19fbE5EB195D6cFBeBdD",
         "balance":"4999777740000000000"
      },
      {
         "account":"0x70F657164e5b75689b64B7fd1fA275F334f28e18",
         "balance":"57443177693229716"
      }
   ]
}
```

{% hint style="info" %}
:book: **Tip:** The `balance` is returned in <mark style="color:yellow;">**wei**</mark>**.**  1 <mark style="color:yellow;">**RCH**</mark> = 10\*\*18 <mark style="color:yellow;">**wei**</mark>
{% endhint %}
{% endtab %}
{% endtabs %}

### Get a list of 'Normal' Transactions By Address

Returns the list of transactions performed by an address, with optional pagination.

{% hint style="warning" %}
**​**​ ​ :pencil: **Note :** This API endpoint returns a maximum of **10000 records** only.
{% endhint %}

```
https://explorer.rchapi.com/api/v1
   ?module=account
   &action=txlist
   &address=0xF426a8d0A94bf039A35CEE66dBf0227A7a12D11e
   &startblock=0
   &endblock=99999999
   &page=1
   &pagesize=10
   &sort=asc
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter  | Description                                                                             | Type                    |
| ---------- | --------------------------------------------------------------------------------------- | ----------------------- |
| address    | the representing the addresses to check for balance                                     | `string`                |
| startblock | the block number to start searching for transactions                                    | `integer`               |
| endblock   | <p><br>the block number to stop searching for transactions</p>                          | `integer`               |
| page       | the page number, if pagination is enabled                                               | `integer`               |
| offset     | the number of transactions displayed per page                                           | `integer`               |
| sort       | the sorting preference, use `asc` to sort by ascending and `desc` to sort by descending | `asc` 、`desc`\[default] |



{% hint style="info" %}
:bulb: **Tip:** Specify a smaller `startblock` and `endblock` range for faster search results.
{% endhint %}
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
   "status":"1",
   "message":"OK",
   "data":[
      {
         "blockNumber":"10475175",
         "timeStamp":"1630314219",
         "hash":"0x9c12ea64ffe659114e1404509ae82d52ca8b785851ef99405d31a6b65fb4d0a2",
         "nonce":"851069",
         "blockHash":"0x52754e796549fe9ab7a4550e0f7d8286fdc8efcac185aad7e7c63ff7c0fb1e5a",
         "transactionIndex":"22",
         "from":"0x161ba15a5f335c9f06bb5bbb0a9ce14076fbb645",
         "to":"0xf426a8d0a94bf039a35cee66dbf0227a7a12d11e",
         "value":"90541060000000000",
         "gas":"207128",
         "gasPrice":"10000000000",
         "isError":"0",
         "txreceipt_status":"1",
         "input":"0x",
         "contractAddress":"",
         "cumulativeGasUsed":"894108",
         "gasUsed":"21000",
         "confirmations":"2362"
      },
      {
         "blockNumber":"10477535",
         "timeStamp":"1630321300",
         "hash":"0xf95f98ec21315ce7b397be1911719c9b3ab0e9386a34103e052ab36e41e9dc3f",
         "nonce":"3",
         "blockHash":"0xaa8e7de4eaced07d438438dfab90c84fea2e270f50a71418a89c87852d2b2a2a",
         "transactionIndex":"253",
         "from":"0xf426a8d0a94bf039a35cee66dbf0227a7a12d11e",
         "to":"0x10ed43c718714eb63d5aa57b78b54704e256024e",
         "value":"0",
         "gas":"254285",
         "gasPrice":"5000000000",
         "isError":"0",
         "txreceipt_status":"1",
         "input":"0x38ed173900000000000000000000000000000000000000000000000805e99fdcc5d000000000000000000000000000000000000000000000000000976181709dbde2904900000000000000000000000000000000000000000000000000000000000000a0000000000000000000000000f426a8d0a94bf039a35cee66dbf0227a7a12d11e00000000000000000000000000000000000000000000000000000000612e1ec5000000000000000000000000000000000000000000000000000000000000000300000000000000000000000055d398326f99059ff775485246999027b3197955000000000000000000000000bb4cdb9cbd36b01bd1cbaebf2de08d9173bc095c0000000000000000000000002d5c9167fdd5c068c8fcb8992e6af639b42fbf70",
         "contractAddress":"",
         "cumulativeGasUsed":"45034490",
         "gasUsed":"199442",
         "confirmations":"2"
      }
   ]
}
```
{% endtab %}
{% endtabs %}

### Get "Internal Transactions" by Block Range



Returns the list of internal transactions performed by an address, with optional pagination.

{% hint style="warning" %}
**​**​ ​ :pencil: **Note :** This API endpoint returns a maximum of **10000 records** only.
{% endhint %}

```
https://explorer.rchapi.com/api/v1
   ?module=account
   &action=txlistinternal
   &address=0xF426a8d0A94bf039A35CEE66dBf0227A7a12D11e
   &startblock=0
   &endblock=99999999
   &page=1
   &pagesize=10
   &sort=asc
```

{% tabs %}
{% tab title="Request" %}
Query Parameters



| Parameter  | Description                                                                                                                                | Type                    |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------- |
| address    | Optional. the representing the addresses to check for balance; When no address is passed, all current transactions will be returned        | `string`                |
| hash       | Optional.  Filter by hash                                                                                                                  | `string`                |
| startblock | the block number to start searching for transactions                                                                                       | `integer`               |
| endblock   | <p><br>the block number to stop searching for transactions, When the incoming value is 0, it is represented as the latest block number</p> | `integer`               |
| page       | the page number, if pagination is enabled                                                                                                  | `integer`               |
| offset     | the number of transactions displayed per page                                                                                              | `integer`               |
| sort       | the sorting preference, use `asc` to sort by ascending and `desc` to sort by descending                                                    | `asc` 、`desc`\[default] |
{% endtab %}

{% tab title="Response" %}
```
{
    "code":1,
    "message":"ok",
    "data":[
        {
            "blockNumber":2666495,
            "from":"0x8c0D4fecF251b896A63E5cD25b5CB8Dcfb2CBfeD",
            "gasCost":7842225,
            "hash":"0xe0e2cc49ea5ff12c4e50f700f59b29eca4a3e61a95b22e60e075791e6a70455d",
            "status":true,
            "timestamp":1652749744,
            "to":"0xE038BeEF31e21F85c33d279E95721e8d546b0cC5",
            "tracer":"CALL_0",
            "value":"0x0"
        },
        {
            "blockNumber":2666400,
            "from":"0x8c0D4fecF251b896A63E5cD25b5CB8Dcfb2CBfeD",
            "gasCost":7842351,
            "hash":"0x8123b55bbda0a9f87bebb16b5d12479be1007f8fd0c43f574197e517f5029b07",
            "status":true,
            "timestamp":1652747371,
            "to":"0xE038BeEF31e21F85c33d279E95721e8d546b0cC5",
            "tracer":"CALL_0",
            "value":"0x0"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

### Get a list of 'RCH20 Token Transfer Events' by Address

Returns the list of BEP-20 tokens transferred by an address, with optional filtering by token contract.

```
https://explorer.rchapi.com/api/v1
   ?module=account
   &action=tokentx
   &contractaddress=0xc9849e6fdb743d08faee3e34dd2d1bc69ea11a51
   &address=0x7bb89460599dbf32ee3aa50798bbceae2a5f7f6a
   &page=1
   &offset=5
   &startblock=0
   &endblock=999999999
   &sort=asc
```

Usage:

* RCH-20 transfers from an **address**, specify the `address` parameter&#x20;
* RCH-20 transfers from a **contract address**, specify the `contract address` parameter
* RCH-20 transfers from an **address** filtered by a **token contract**, specify both `address` and `contract address` parameters.

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter       | Description                                                                             | Type   |
| --------------- | --------------------------------------------------------------------------------------- | ------ |
| address         | Optional, Filter by this address                                                        | string |
| contractaddress | Required                                                                                | string |
| hash            | Optional                                                                                | string |
| page            | Required, min is 1                                                                      | int    |
| offset          | Optional, max is 1000                                                                   | int    |
| startblock      | Optional                                                                                | int    |
| endblock        | Optional                                                                                | int    |
| sort            | the sorting preference, use `asc` to sort by ascending and `desc` to sort by descending | string |
{% endtab %}

{% tab title="Response" %}
```
{
    "code": 1,
    "message": "ok",
    "data": [
        {
            "blockHash": "0xee359fedde05b76168a9dfd8c2b26b66afecc5819719ad932c2cbc8c473028de",
            "blockNumber": 2666830,
            "contract": "0xB9bcB70202bD2F79Ed8e0B1128a55786020b690A",
            "from": "0xE1c3a81C4E6B47d6a7fd4C5bBaB3521911b620Eb",
            "gas": 1530000,
            "gasPrice": "1000000000",
            "gasUsed": 113357,
            "index": 0,
            "nonce": 43086,
            "timestamp": 1652757887,
            "to": "0x00D7f1924289dEa25D8faA5A31539DAC66ae8A02",
            "tokenDecimal": 18,
            "tokenName": "RDX Token",
            "tokenSymbol": "RDX",
            "transactionHash": "0xa9a1c14741e79fc2d4c449e53320b832b815647fe5f2e0613437bc31dcc6111d",
            "value": "0x37"
        },
        {
            "blockHash": "0xf350d2d2328f45c3e7ade96c5d64dc2e5ead4169d6d4b4e1ff0487341dc13697",
            "blockNumber": 2666822,
            "contract": "0xB9bcB70202bD2F79Ed8e0B1128a55786020b690A",
            "from": "0xCE4fd777d886f573DA5A353c231050221BcBB4e1",
            "gas": 1530000,
            "gasPrice": "1000000000",
            "gasUsed": 113485,
            "index": 0,
            "nonce": 43180,
            "timestamp": 1652757723,
            "to": "0x00D7f1924289dEa25D8faA5A31539DAC66ae8A02",
            "tokenDecimal": 18,
            "tokenName": "RDX Token",
            "tokenSymbol": "RDX",
            "transactionHash": "0x4ab69d5be4b71f5134900723d40de8049a82f74b6e86c2775447e5bad0c295ce",
            "value": "0x8f37"
        }
    ]
}
```
{% endtab %}
{% endtabs %}
