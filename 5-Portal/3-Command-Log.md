---
title: Command Log
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

{% /prereqList %}

If you have previously run a command {% infoHover %}Within the past 24 hours.{% /infoHover %} which you want to execute recurrently, you can review the Command Log and fetch the payload.

{% callout %}
After [building an I2C Profile](5-Portal/2-I2C-Profile-Builder.md), you can retrieve the command.
{% /callout %}

1. [Go to the Command Log page](https://portal.fingoti.com/reports/command-log)

   ![Screenshot of the Command Log page](assets/command-log-page.png)

2. Select a device

   ![Screenshot of the device dropdown](assets/device.png)

3. Choose the direction

   ![Screenshot of the direction dropdown](assets/direction.png)

   ![Screenshot of the direction dropdown](assets/directions.png)

   Outbound - The request

   Inbound - The reply

4. Pick a suitable time frame

   ![Screenshot of the time frame buttons](assets/time.png)

5. Press Get Logs

   ![Screenshot of the Get Logs button](assets/get.png)

   Look through the logs to find the command you want.

   ![Screenshot of the logs](assets/logs.png)

6. Press the Copy Message Data button

   ![Screenshot of the API request](assets/payload.png)

   ![Screenshot of the Copy Message Data button](assets/copy.png)
