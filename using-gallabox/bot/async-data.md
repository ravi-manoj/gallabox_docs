# Async Data

You can use async data to push or pull information from the any server provides HTTP API

![](<../../.gitbook/assets/image (17).png>)

#### **Type**

**Message**: When you want send text message based on the response of the HTTP API

**Options**: When you need send option message based on the response of the HTTP API

**Attachments**: When you need send media message based on the response of the HTTP API

#### Method, URL, Headers, Content Type

This can be configured based on your API requirement

Currently we support only JSON content-type

#### Body

The JSON body can be constructed with the required information.

You can [use the user’s prompt value](https://www.notion.so/Bot-Async-Data-f366ebb7548a41008a43bdfbae22c5e0) as part of the JSON to push / pull.

**Sample Body JSON**

```json
{
  "name": "{{response.full_name}}", // full_name prompt value
  "email": "{{response.email_address}}", // email_address prompt value
  "gender": "{{responseValue.gender}}" // gender prompt selected Option label
}
```

#### Transform Template

You can transform the response from the http API to format and send message back to the user.

We use [st.js](https://github.com/SelectTransform/st.js#readme) to transform the http response data.

Based on the [Type](https://www.notion.so/Bot-Async-Data-f366ebb7548a41008a43bdfbae22c5e0) you need to [transform the response](https://www.notion.so/Bot-Async-Data-f366ebb7548a41008a43bdfbae22c5e0) for sending dynamic message based on the HTTP response.

#### Variables

You can create multiple variables based on the http response which can be referred on following prompts.

You can create variable key and dynamic value based on the http response.

You can refer this variable as `{{variables.<variable_key>}}`

### Send prompt value to HTTP API

All the prompt values given by the user will be stored in the `response` object.

You can refer the previous prompt value(s) by its `name` attribute.

****

**For "Text", "Number", "Email", "Phone" and "URL" response type**

If the prompt type is text, then the value of the prompt can be refer as `{{response.<name_of_the_prompt>}}` i.e. `{{response.full_name}}`

****

**For “Options” prompt type**

If the prompt type contains Options, then the value of the prompt can be refer as `{{response.<name_of_the_prompt>}}` i.e. `{{response.brand}}` which would return the **`id`** field.

To get Options label you can use `{{responseValue.<name_of_the_prompt>}}` i.e. `{{responseValue.brand}}`

****

**For "File" response type**

If the prompt type is `File`, then the value of the prompt can be refer as `{{response.<name_of_the_prompt>[0].contentUrl}}`&#x20;

ex. `{{response.your_photo[0].contentUrl}}`

****

**For "Location" response type**

If the prompt type is `Location`, then the value of the prompt can be refer as  `{{response.<name_of_the_prompt>[0].content.<latitude|longitude>}}`&#x20;

**ex:**  `{{response.home[0].content.latitude}}`  or/and `{{response.home[0].content.longitude}}`

### **Get data from HTTP API and send dynamic message**

We use [st.js](https://github.com/SelectTransform/st.js#readme) to transform the http response data

\<aside> 💡 Use can use this playground to tryout on the transformation[https://selecttransform.github.io/playground/](https://selecttransform.github.io/playground/)

\</aside>

#### **Dynamic "Message" (text)**

**Template:**

```json
{
    "label": "{{<path_to_your_field>}}"
}
```

**Example:** _Sample Response from HTTP API:_

```json
{
    "data": {
        "id": 2,
        "email": "janet.weaver@reqres.in",
        "first_name": "Janet",
        "last_name": "Weaver",
        "images": [{ "url": "<https://reqres.in/img/faces/2-image.jpg>", "type": "image/jpeg" }]
    },
    "support": {
        "url": "<https://reqres.in/#support-heading>",
        "text": "To keep ReqRes free, contributions towards server costs are appreciated!"
    }
}
```

_Transform template:_

```json
{
    "label": "This is your email {{data.email}}. To do any changes please contact our support at {{support.url}}"
}
```

#### Advance Samples

_Sample Response from HTTP API:_

```json
{
    "request": {
        "subject": "Need an External Monitor",
        "id": "2582000001136623",
        "assigned_time": null,
        "group": null,
    },
    "response_status": {
        "status_code": 2000,
        "status": "success"
    }
}
```

_Transform template:_

```json
[
    {
    "{{#if request !== 'undefined'}}": {
      "label": "Thanks for letting us know your query, we shall get back to you as soon as possible."
    }
  },
  {
    "{{#else}}": {
      "label": "We couldn't able to submit your request now, please try again later."
    }
  }
]
```

#### **Dynamic "Options"**

**Template:**

```json
{
    "{{#each <path_to_your_array_field>}}": {
        "id": "{{<path_to_id_inside_the_array>}}",
        "value": "{{<path_to_text_inside_the_array>}}", // display text
        "description": "{{<path_to_description_inside_the_array>}}", // optional
    }
}
```

**Example:** _Sample Response from HTTP API:_

```json
{
    "id": 2,
    "name": "Shirts",
    "sub_category": [
        { "id": 21, "name": "Formal Shirts" },
        { "id": 22, "name": "Casual Shirts" }
    ]
}
```

_Transform template:_

```json
{
    "{{#each sub_category}}": {
        "id": "{{id}}",
        "value": "{{name}}"
    }
}
```

#### **Dynamic "Attachments"**

**Template:**

```json
{
    "{{#each <path_to_your_array_field>}}": {
        "contentType": "{{<path_to_content_type_inside_the_array>}}",
        "contentUrl": "{{<path_to_content_url_inside_the_array>}}",
        "name": "{{<path_to_attachment_name_inside_the_array>}}", // optional
        "caption": "{{<path_to_caption_inside_the_array>}}" // optional
    }
}
```

**Example:** _Sample Response from HTTP API:_

```json
{
    "id": 2,
    "email": "janet.weaver@reqres.in",
    "first_name": "Janet",
    "last_name": "Weaver",
    "images": [{ "url": "<https://reqres.in/img/faces/2-image.jpg>", "type": "image/jpeg" }]
}
```

_Transform template:_

```json
{
    "{{#each images}}": {
        "contentType": "{{type}}",
        "contentUrl": "{{url}}"
    }
}
```
