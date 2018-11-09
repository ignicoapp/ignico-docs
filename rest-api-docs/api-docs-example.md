---
description: >-
  To interact with other endpoints your requests have to be authorized using
  OAuth2 access token. To obtain a token your application can get it in exchange
  for API Keys using client credentials grant.
---

# Authorization

{% api-method method="post" host="https://{{workspace}}.igni.co/api/v1" path="/oauth2/token" %}
{% api-method-summary %}
Issue new access token
{% endapi-method-summary %}

{% api-method-description %}
Sign in using OAuth2 client credentials grant and fetch access token
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Accept" type="string" required=true %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/x-www-form-urlencoded
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="grant\_type" type="string" required=true %}
client\_credentials
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=true %}
Your Client ID
{% endapi-method-parameter %}

{% api-method-parameter name="client\_secret" type="string" required=true %}
Your Client Secret
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Token successfully issued.
{% endapi-method-response-example-description %}

```javascript
{
    "token_type": "Bearer",
    "expires_in": 172800,
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciiIsImp0aSI6IjVhODFiMjgyZjY5NzRkOGQ2YWU0N2UxZGI4ZWFiMTUyNWRjMmQ0YjlkYWNlNjM3YTczZTdmMTUwZjU1MDYyMjEyNjk4YmM0MTMyYWIwYWM3In0.eyJhdWQiOiIxIiwianRpIjoiNWE4MWIyODJmNjk3NGQ4ZDZhZTQ3ZTFkYjhlYWIxNTI1ZGMyZDRiOWRhY2U2MzdhNzNlN2YxNTBmNTUwNjIyMTI2OThiYzQxMzJhYjBhYzciLCJpYXQiOjE1NDE3NzAyNTgsIm5iZiI6MTU0MTc3MDI1OCwiZXhwIjoxNTQxOTQzMDU4LCJzdWIiOiIiLCJzY29wZXMiOltdfQ.YkXTWC-3DBXOKbi9AppkXcC8OAUxHYsRvw7XZFdBDqBcwVXD-J0yHe8jwE5amp2qfTNkFVV_f-0_H2b6rxDJDH_oWR7pRiaF1BjqPpegEdAUDPNMH_WVokFmRwBfOwiDB8HV6FCvFMtcFRmP737a8jfFmmawrBvC1_d3xUK-eIulVLLmjoTiJjFY4U1lswsskJtZtPgx1LZb2Re2YGdwpv3117SgMzfp-27rq6X95kmDpqWIm7f6Y1bmL19ujUhQVygCH-Yk6vPT8aG-o67XV6YA__CfB1AeiJGCI8SQH3D1SvdQJG_8BDBOZT4WaEMNOJ__mz1IGffsAffE3vPUuiaQxhdlA"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Client authentication failed.
{% endapi-method-response-example-description %}

```javascript
{
    "error": "invalid_client",
    "message": "Client authentication failed"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



