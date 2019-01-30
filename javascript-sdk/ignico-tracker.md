---
description: 'Sample tracking code you can find here: [link]'
---

# Ignico Tracker

## Installation and configuration

Open zipped folder with the tracking code and plugins. Please note that JavaScript files in production version are downloaded directly with the use of HTTPS protocol from your Ignico instance, i.e. **your\_workspace\_name.igni.co**

### **Including tracker code into your website**

Include following script in the `<body>` ****section on every page you would like to have your users tracked \(not only on the transaction page\):

```markup
<script type="text/javascript" >
    (
        function(w, s, t, i, a, b, n) {
            w["QuenObject"] = a;
            w[a] = w[a] || function() {
                (
                    w[a].q = w[a].q || []
                ).push(arguments)
            };
            w[a].tl=1*new Date();

            b = s.createElement(t),
                n = s.getElementsByTagName(t)[0];
            b.async = 1;
            b.src = i;
            n.parentNode.insertBefore(b, n);
        }
    )(window, document, "script", "dist/bundle.js", "iq");

    iq("create", "TRACKER_ID", "TARGET_ADDRESS");
</script>

```

You need to replace following parameters in code listed above:

| Param | Description |
| :--- | :--- |
| **TRACKER\_ID** | ID generated while adding a new tracker in Ignico  |
| **TARGET\_ADDRESS** | Address where requests will be sent – for the development phase we recommend to use following tool: [https://requestbin.fullcontact.com/](https://requestbin.fullcontact.com/) |

### Tracker plugins configuration

To include a plugin into Ignico tracker:

1. Include JavaScript code of this plugin \(before initialization of the tracker\):
2.   ```markup
   <script type="text/javascript" src="dist/plugins/referrer.js"></script>
   ```

3. Declare plugin initialization within the tracker:  


   ```javascript
   iq("require", "referrer");
   ```

### **Tracker parameters configuration**

Independently of the plugins you can setup different model parameters by the following command:

```javascript
iq("set", "userId", "USER_ID");
```

Paremeters should be set up before using `send` ****command.

#### Available parameters

| Param | Description |
| :--- | :--- |
| **version** | Tracker version |
| **trackingId** | TRACKER\_ID |
| **subjectId** | Visitor ID |
| **userId** | User ID |
| **referrerId** | Referring User ID |
| **referrerSubjectId** | Referring Visitor ID |
| **type** | Action \(referral or conversion\) type in form of a slug |
| **utmSource** | UTM Source |
| **utmMedium** | UTM Medium |
| **utmCampaign** | UTM Campaign |
| **utmTerm** | UTM Term |
| **utmContent** | UTM Content |
| **loadTime** | Loading time |

### Sending actions \(conversions or referrals\)

To send an action \(conversion or referral\) you need to initialize `send` ****command – with or without parameters – there are 2 types of initialization:

```javascript
iq("send", "order", {value: 100});
iq("send", {type: "order", params: {value: 140, points: 20}});
```

Second parameter `type` ****is an action slug, third parameter \(optional\) is action parameter. Sending of an action should be performed on the payment / transaction success page.

## Plugins description

### Referral Plugin

A plugin that enables saving, reading and sending of an `__igrc` parameter \(known Referring User ID\) and `__igrs` parameter \(unique Visitor ID that is not a user in Ignico – this parameter is always assigned to each visitor\) – based on this parameters Ignico is tracking the referrals.

### Facebook Plugin

Plugin that adds `__igrs` and `__igrc` parameters \(that identify the referral\) to the standard Facebook share button controls.

Please note that when you already know Ignico user ID, then before initializing this plugin you should set this user ID like in the example below:

```javascript
iq("set", "userId", "USER_ID");
iq("require", "facebook");
```

It is also possible to track clicks in Like / Share button of each user however it requires using the Facebook API – if you are interested in this feature, please contact us.

### Event Tracker Plugin

Plugin that helps you to easily catch events like button click, page loading, moving the mouse over the object and send an action to Ignico.

Sample use case where after clicking on the button plugin sends an action of a type `order` with value `100`:

```markup
<input type="button" id="button1" value="button1" ig-on="click" ig-hit-type="order" ig-value="100" />
```

