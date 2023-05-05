---
title: Claim with the browser
---

{% prereqList %}

{% prereqLink link="1-Account-management/1-Create-an-account.md" %}
Create an account
{% /prereqLink %}

{% prereqLink link="2-Organisation-management/5-Join-an-Organisation.md" %}
Join an Organisation
{% /prereqLink %}

{% prereqLink link="3-Device-management/1-Power-a-device.md" %}
Power a device
{% /prereqLink %}

{% prereqLink link="3-Device-management/2-Claim-a-device.md" %}
Claim a device
{% /prereqLink %}

{% prereqText %}
Local network connection {% infoHover %}You must be connected to the same network as the device.{% /infoHover %}
{% /prereqText %}

{% /prereqList %}

1. [Go to the Devices page on the Portal](https://portal.fingoti.com/devices)

2. Press Claim Device (at the top-right &nearr; of the page)

   ![Screenshot of the Claim Device button](assets/claim-device-button.png)

3. Enter the device's serial number

   ![Screenshot of the Claim Device dialogue](assets/claim-device-dialogue.png)

4. Press Start Claim

    {% contextualCallout severity="warning" %}
    You have fifteen minutes to finish the claim.
    {% /contextualCallout %}

5. Press the device

   ![Screenshot of a device](assets/fingoti-device.png)

6. Take note of the Claim code

   ![Screenshot of the Device Overview dialogue displaying the Claim code](assets/claim-code.png)
   

7. Connect to the device's WiFi network (from a phone, tablet, laptop, or computer)

    {% contextualCallout severity="info" %}
    `A1B2C3D4E5` is only an example of a device serial number.
    {% /contextualCallout %}

    ```json
    FINGOTI-A1B2C3D4E5
    ```

8. Enter the default WiFi password

   ```json
   fingoftheinternet
   ```

9. [Go to device.fingoti.com](http://device.fingoti.com) {% infoHover %} Alternatively, go to <http://169.254.0.1>. {% /infoHover %}

   ![Screenshot of the Setup page](assets/setup.png)

   Use a Chromium-based browser {% infoHover %}Including Google Chrome, Microsoft Edge, Opera, Brave, Vivaldi, and others.{% /infoHover %}.

10. Enter the details of the WiFi network you want the device to connect to

    {% contextualCallout severity="info" %}
    The SSID is the name of the WiFi network.
    {% /contextualCallout %}

11. Enter the claim code

12. Press Start Setup

   ![Screenshot of the Setup page](assets/waiting.png)
