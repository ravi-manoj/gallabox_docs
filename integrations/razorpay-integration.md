# RazorPay Integration

![Update Gallabox Webhook](../.gitbook/assets/razorpay-integration-999.gif)

1. Access your **RazorPay** dashboard.
2. Select '**Settings**' in your _dashboard left panel_
3. Click on the _**Webhook**_ tab.
4. Create **Add New Webhook**
5. Enter your **Webhook URL, Secret** given by Gallabox Team
6.  Enter **Alert Email** to **developers@gallabox.com**

    Check **Active Events** based on your needs, key events are below

    * **`payment.captured`** - Triggered when a payment is successfully captured
    * **`payment.failed`** - Triggered when a payment fails
    * **`invoice.paid`** - Triggered when an invoice is successfully paid
    * **`refund.processed` -** Triggered when the refund is successfully processed.

    _Refer below links for other event descriptions_

    Payment Events - [https://razorpay.com/docs/webhooks/payloads/payments/](https://razorpay.com/docs/webhooks/payloads/payments/)

    Invoice Events - [https://razorpay.com/docs/webhooks/payloads/invoices/](https://razorpay.com/docs/webhooks/payloads/invoices/)

    Refund Events - [https://razorpay.com/docs/webhooks/payloads/refunds/](https://razorpay.com/docs/webhooks/payloads/refunds/)
7. Create Webhook by submitting the form

