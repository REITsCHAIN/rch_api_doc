---
description: Account-related HTTP requests.
---

# Account

### Get RCH balance for a Single Address

Returns the RCH balance of a given address

```
https://explorer.rchapi.com/api/v1
?module=account
&action=balance
&address=0x3f349bBaFEc1551819B8be1EfEA2fC46cA749aA1
```

> Try this endpoint in your [<mark style="color:yellow;">**browser**</mark>](https://explorer.rchapi.com/api/v1?module=account\&action=balance\&address=0x)<mark style="color:yellow;">****</mark>

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description                                                                |
| --------- | -------------------------------------------------------------------------- |
| address   | the string representing the address to check for balance                   |
| tag       | the string pre-defined block parameter, either earliest, pending or latest |
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

Try this endpoint in your [<mark style="color:yellow;">**browser**</mark>](https://explorer.rchapi.com/api/v1?module=account\&action=balancemulti\&address=0x3f349bBaFEc1551819B8be1EfEA2fC46cA749aA1,0x4bF01a5A576bE1254C5E19fbE5EB195D6cFBeBdD)<mark style="color:yellow;">****</mark>

{% tabs %}
{% tab title="Request" %}
Query Parameters

|         |                                                                                                                                                                                          |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| address | <p>the <code>strings</code> representing the addresses to check for balance, separated by <code>,</code> commas<br><br>up to <strong>20</strong> <strong>addresses</strong> per call</p> |
| tag     | the string pre-defined block parameter, either earliest, pending or latest                                                                                                               |
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

> Try this endpoint in your [**browser**](https://explorer.rchapi.com/api/v1?module=account\&action=txlist\&address=0xF426a8d0A94bf039A35CEE66dBf0227A7a12D11e\&startblock=0\&endblock=99999999\&page=1\&pagesize=10\&sort=asc) :link:&#x20;

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





