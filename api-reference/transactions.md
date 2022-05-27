# Transactions

## Check Transaction Receipt Status

Returns the status code of a transaction execution.

```
https://explorer.rchapi.com/api
   ?module=transaction
   &action=gettxreceiptstatus
   &hash=0xe9975702518c79caf81d5da65dea689dcac701fcdd063f848d4f03c85392fd00
```

{% tabs %}
{% tab title="Request" %}
Query Parameters

| Parameter | Description                                                                  | Type   |
| --------- | ---------------------------------------------------------------------------- | ------ |
| hash      | the `string` representing the transaction hash to check the execution status | string |
{% endtab %}

{% tab title="Response" %}
Sample Response

```
{
   "code":1,
   "message":"OK",
   "data":{
      "status":1
   }
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
:book: **Tip:** The `status` field returns -1 for **failed transactions** and `1` for **successful transactions** 2 for **pending transactions(12 blocks confirms).**
{% endhint %}
