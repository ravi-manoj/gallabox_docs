---
description: Sending WhatsApp Message via HTTP Form Post
---

# HTTP Form POST

{% swagger method="post" path="/form" baseUrl="https://workflow.gallabox.com/webhook/messages/whatsapp" summary="Send Message via Form Post" expanded="true" %}
{% swagger-description %}
We provide [api ](https://bit.ly/GallaboxApiDocs)to send message via HTTP POST with JSON as body content-type.&#x20;

In some cases you would not be able to control the body of HTTP being sent, in that you can use the below API to send message by passing header and body values.
{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" required="true" %}
Account API Key
{% endswagger-parameter %}

{% swagger-parameter in="header" name="apisecret" required="true" %}
Account API Secret
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelId" required="true" %}
Get at channel Id from 

[https://app.gallabox.com/channels/whatsapp](https://app.gallabox.com/channels/whatsapp)


{% endswagger-parameter %}

{% swagger-parameter in="body" name="templateName" required="true" %}
Name of the approved WhatsApp template
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientName" required="true" %}
Recipient Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="recipientPhone" required="true" %}
WhatsApp Number to which message to be sent ex. +919840985908 or 9840985908
{% endswagger-parameter %}

{% swagger-parameter in="body" name="<<variable name 1>>" %}
Variable value to be passed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="<<variable name 2>>" %}
Variable value to be passed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="headerMediaUrl" %}
Media Url to override the header media
{% endswagger-parameter %}

{% swagger-parameter in="body" name="headerMediaName" %}
Media Name to override the header media
{% endswagger-parameter %}

{% swagger-parameter in="body" name="footerButtonDomain" %}
URL prefix of the dynamic footer button
{% endswagger-parameter %}

{% swagger-parameter in="body" name="footerButtonUrl" %}
Dynamic footer button url value
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}
<pre class="language-json"><code class="lang-json">{
    "id": "&#x3C;&#x3C;message id>>",
<strong>    "status": "ACCEPTED",
</strong>    "message": "Message received and being sent to recipient"
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="form" baseUrl="https://workflow.gallabox.com/webhook/contacts/upsert/" summary="Upsert Contact via Form Post" %}
{% swagger-description %}
We provide [api ](https://bit.ly/GallaboxApiDocs)to upsert contact via HTTP POST with JSON as body content-type.&#x20;

In some cases you would not be able to control the body of HTTP being sent, in that you can use the below API to send message by passing header and body values.
{% endswagger-description %}

{% swagger-parameter in="header" name="apikey" required="true" %}
Account API Key
{% endswagger-parameter %}

{% swagger-parameter in="header" name="apisecret" required="true" %}
Account API Secret
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" required="true" %}
Name of the contact
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" %}
Email of the contact
{% endswagger-parameter %}

{% swagger-parameter in="header" name="apikeysecret" %}
If you can also pass both apikey and apisecret in this one header separated with colon (:)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phone" required="true" %}
WhatsApp Phone number 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="contactOwnerId" %}
Pass the email of the agent to be mapped
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" required="false" %}
Comma separated tag names
{% endswagger-parameter %}

{% swagger-parameter in="body" name="<<field value name 1>>" %}
Field Value
{% endswagger-parameter %}

{% swagger-parameter in="body" name="<<field value name 2>>" %}
Field Value
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "status":"ok"
}
```
{% endswagger-response %}
{% endswagger %}
