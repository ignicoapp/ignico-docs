---
description: >-
  Manage Actions that your users have taken. May it be a sale, a lead, a meeting
  or any other activity you wish to use to reward your user.
---

# Actions

{% api-method method="get" host="https://{{workspace}}.igni.co/api/v1" path="/actions" %}
{% api-method-summary %}
List all actions
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Sample request

{% tabs %}
{% tab title="cURL" %}
```text
curl -X GET \
  https://{{workspace}}.igni.co/api/v1/actions \
  -H 'Accept: application/vnd.api+json' \
  -H 'Authorization: Bearer {{token}}' \
  -H 'Content-Type: application/vnd.api+json'
```
{% endtab %}

{% tab title="HTTP" %}
```text
GET /api/v1/actions HTTP/1.1
Host: {{workspace}}.igni.co
Content-Type: application/vnd.api+json
Accept: application/vnd.api+json
Authorization: Bearer {{token}}
```
{% endtab %}
{% endtabs %}

{% api-method method="get" host="https://{{workspace}}.igni.co/api/v1" path="/actions/:id" %}
{% api-method-summary %}
Fetch single action
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

