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
&address=0x
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

{% endtab %}
{% endtabs %}

### Get BNB Balance for Multiple Addresses in a Single Call

