# ZeoCollect GTM Template
## Integration details input
The tag will contain 3 sections: Initialisation Options, Track page views and events, and Login and identities setting

## Initialisation options
- ***Write Key:*** When you create a GTM-based source in your Collect account, a write key will be provided in source details. This is a mandatory field for recording events.
- ***User Country:*** ISO Alpha 3 country code. This will be used to determine region for storage. If this is not sent, our servers will use the IP Address to determine the same, so please use this if your account is set up only for specific regions.
- ***Event Key:*** The key against which event names are stored in the dataLayer object. You can choose not to fill this, if you use the GTM's default key - event.
- ***Consent Method:*** The Collect SDK has 3 options that can be used to determine consent actions.
    - **Option ‘Default Opt-in’:** This will set the corresponding options:optOut = false and use this permission to record events. You can choose this if a: You fire the tag only for consented users or b: Consent communication will happen via other methods (like an API integration or file upload etc).
    - **Option ‘Check TCF CMP’:** This will set the corresponding options:useConsent and options:checkForCMP to true. The javascript will automatically check for the presence of the cmp.js script and the __cmp variable in global scope, and query the TCF API to fetch the latest publisher consent before recording the events on each Javascript load.


## Track page views and events

- **Page View Tracking Event Name:** We track pageview by default for event name 'gtm.js'. If some other event name is used, the same should be updated in the input for overriding.
- **Event Tracking - Event name:** Enter a regex pattern that matches all event names you want to track. If you want to track just a single event, just enter that event name. By default, we will use this pattern  .* to identify events.
- **Special Events - Event Name:** If there are event names that you want to track apart from the regex provided, you can add all such events here.
- **Pre Defined Properties:** Input the properties you'd like to attach or override. You can define the values from your variables or provide static values for them.
- **PII to be excluded:** Enter all the PII and user related fields in the dataLayer that need to be excluded in event properties. For eg: If email is pushed into datalayer in the raw form.

