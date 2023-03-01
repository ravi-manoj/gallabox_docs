# Bot Actions

### 1. What is Bot Actions?&#x20;

At the end of any bot flow, the option to assign a conversation to an agent or update information generated from a response is called bot actions. The response will be updated in the contact details and this can be useful to create segments for broadcasting.&#x20;

![](<../../.gitbook/assets/image (6).png>)

### 2. How to Setup Bot Actions?&#x20;

#### a. Response Update Type Bot Action:

![](<../../.gitbook/assets/Untitled design (1).gif>)

* Drag and drop an _ask a question_ card or _send a message_ card.&#x20;
* Switch **On** the bot action button.&#x20;
* To replace/update information: **Select the field** to be updated from the drop-down list, click <mark style="color:green;">select</mark> '**get response from bot**' and select '**Replace**'.&#x20;

![](<../../.gitbook/assets/image (4).png>)

* To add pre-defined labels from a response within a flow: In this example, you can see that we would like to replace our lead probability stage based on the response. Select your **update tag** from the drop-down list, <mark style="color:red;">deselect</mark> '**get response from bot**' fill in/select your **required text** and click select '**replace**'. &#x20;
* This method of bot actions can be used by businesses who wish to define their customers based upon the conversational flow.

{% hint style="warning" %}
Note: The field to be filled can either be text, number or a drop-down. This depends on the tag type. **Eg: text, number, select, multi-select, etc.**&#x20;

The option to **'Append'** will be showcased if the **tag type is a multi-select** else, the option to **'Replace'** will be available. ****&#x20;
{% endhint %}

#### b. Response Assignment/Resolution Type Bot Action:

![](<../../.gitbook/assets/Untitled design (2) (1).gif>)

* Drag and drop an _ask a question_ card or _send a message_ card.&#x20;
* Switch **On** the bot action button.&#x20;
* Assign Conversation: select the action type as '**assign conversation**' select your '**assignee**'.&#x20;
* Unassign Conversation: select the action type as '**unassign conversation**'. This will ensure that once the bot flow ends the conversation is directed to the unassigned tab.&#x20;
* Resolve Conversation: select the action type as '**resolve conversation**'. This will ensure that once the bot flow ends the conversation is resolved.&#x20;

### 3. What is Append?&#x20;

Append is to add more information rather than to replace valuable data. The append option will be available when your data type is multi-select and multi-text.&#x20;

Example: **Lead Stage - **<mark style="color:blue;">**Prospect**</mark>

After receiving a response from the flow you **append** the lead stage to '<mark style="color:blue;">Interested</mark>'.&#x20;

The updated contact detail will read: **Lead Stage - **<mark style="color:blue;">**Prospect, Interested**</mark>

### 4. What is Replace?&#x20;

Replace as the name suggests is to replace information/ update information from the existing data. This option will be available for all field types.&#x20;

Example: **Phone Number -** <mark style="color:blue;">90000 90000</mark>

After receiving the bot response the action is to **replace** the field with the given information ' <mark style="color:blue;">90001 90001</mark> '.&#x20;

The updated contact detail will read: **Phone Number -** <mark style="color:blue;">90001 90001</mark>

### 5. Does the bot action responses depend on your defined additional fields?&#x20;

Yes, the response you would like to store as customer data depends on the additional fields you have created within your Gallabox account.&#x20;

### 6. When should you use 'get response from bot' as an action?&#x20;

'Get response from bot' action should be employed in situations wherein you require to replace or update the data given by the user. It works on the principle of asking and receiving information.&#x20;
