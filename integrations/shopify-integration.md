# Shopify Integration

### Generating API Key

![](../.gitbook/assets/shopify-keys-1.gif)

1. Access the [**Apps**](https://www.shopify.com/admin/apps) section of your Shopify Store's admin console.
2. Click on '**Manage private apps**' at the bottom of the page.
3. Click on the '**Create new private app**' button. Create a new app by entering the necessary information.
4. Under "App details"
   * Private app name - "Gallabox"
   * Emergency developer email - "developers@gallabox.com"
5. Under 'Admin API' section, we would need **read** permission on the following modules&#x20;
   * Fulfillment services&#x20;
   * Orders&#x20;
   * Order editing&#x20;
   * Product listings&#x20;
   * Products Shipping&#x20;
   * Third-party fulfillment orders&#x20;
   * ScriptTag (**need both read/write permission**, this to add WhatsApp Widget to your shopify website)
6. Please select Latest (2021-10) Webhook API version
7. You can leave the 'Storefront API' unchecked, as currently we are not using storefront related information..
8. Upon app creation, scroll down, and you will see your API key, Password, and Shared Secret.
9. Share the API key, Password, and Shared Secret to developers@gallabox.com.
