---
title: Claim with UART
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
A serial terminal {% infoHover %}Such as ESPlorer or PuTTY.{% /infoHover %} with a baud rate of 115200
{% /prereqText %}

{% /prereqList %}


{% tabs %}

{% tab label="Evaluation Board or USB to Serial Adapter Board" %}

{% contextualCallout severity="info" %}
If you are using the Evaluation Board: Select the UART bus, by flicking the I2C → UART switch.
{% /contextualCallout %}

1. Connect the USB-C cable to a computer


{% tab label="Windows" %}

2. [Install the Virtual COM Port (VCP) driver](https://ftdichip.com/drivers/vcp-drivers/)

  The virtual COM port appears under "Ports (COM & LPT)" in Device Manager.

  ![Screenshot of the Windows Device Manager](assets/device-manager.png)

{% /tab %}

{% /tab %}

{% /tabs %}

3. [Go to the Devices page on the Portal](https://portal.fingoti.com/devices)

4. Press Claim Device

5. Enter the serial number

6. Press Start Claim

  {% contextualCallout severity="warning" %}
  You have fifteen minutes to finish the claim.
  {% /contextualCallout %}

7. Press the device

   ![Screenshot of a device](assets/fingoti-device.png)

8. Take note of the Claim code

  ![Screenshot of the Device Overview dialogue displaying the Claim code](assets/claim-code.png)

9. Copy the following request

  ```json
  {
    "request": [
      {
        "property": "deviceSetup",
        "operation": 1,
        "payload": {
          "ssid": "my_wifi_ssid",
          "password": "my_wifi_password",
          "code": "my_claim_code"
        }
      }
    ]
  }
  ```

10. Replace `my_wifi_ssid` with the name of the WiFi network you want the device to connect to

11. Replace `my_wifi_password` with the password of the WiFi network you want the device to connect to

12. Replace `my_claim_code` with the claim code

13. Send the request
