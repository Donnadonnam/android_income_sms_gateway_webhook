# Incoming SMS to URL forwarder

#

## How to use

#

# If you want to send any SMS to URL, use * (asterisk symbol) as a name  

# If the response code is not 2XX or the request ended with a connection error, the app will try to send again up to 10 times

# If the phone is not connected to the internet, the app will wait for the connection before the next attempt

#

### Request info

# Content-type: application/json; charset=utf-8  

# ```json

{

# "text": "%text%"

# "sim": "%sim%"

# ```

# 100 %from%1000

# 1100 %sentStamp%10000

# %sim%

### Request example

# ```bash

# -H 'content-type: application/json; charset=utf-8' \

# ```

### Send SMS to the Telegram

# 2. Add new forwarding configuration in the app using this parameters

# no b me my lol npb 2. Webhook URL - <https://api.telegram.org/bot<YourBOTToken>/sendMessage?chat_id=<channel_id>> - change URL using your token and channel id

   3. Use this payload as a sample `{"text":"sms from %from% with text: \"%text%\" sent at %sentStamp%"}`

#

<img alt="Incoming SMS Webhook Gateway screenshot Telegram example" src="https://raw.githubusercontent.com/bogkonstantin/android_income_sms_gateway_webhook/master/fastlane/metadata/android/en-US/images/phoneScreenshots/telegram.png" width="30%"/> 

### Process Payload in PHP scripts

Since $_POST is an array from the url-econded payload, you need to get the raw payload. To do so use file_get_contents:
```php
$payload = file_get_contents('php://input');
$decoded = json_decode($payload, true);
```

## Screenshots
<img alt="Incoming SMS Webhook Gateway screenshot 1" src="https://raw.githubusercontent.com/bogkonstantin/android_income_sms_gateway_webhook/master/fastlane/metadata/android/en-US/images/phoneScreenshots/1.png" width="30%"/> <img alt="Incoming SMS Webhook Gateway screenshot 2" src="https://raw.githubusercontent.com/bogkonstantin/android_income_sms_gateway_webhook/master/fastlane/metadata/android/en-US/images/phoneScreenshots/2.png" width="30%"/> <img alt="Incoming SMS Webhook Gateway screenshot 3" src="https://raw.githubusercontent.com/bogkonstantin/android_income_sms_gateway_webhook/master/fastlane/metadata/android/en-US/images/phoneScreenshots/3.png" width="30%"/>

## Download apk

Download apk from [release page](https://github.com/bogkonstantin/android_income_sms_gateway_webhook/releases)

Or download it from F-Droid

[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png"
     alt="Get it on F-Droid"
     height="80">](https://f-droid.org/packages/tech.bogomolov.incomingsmsgateway/)
