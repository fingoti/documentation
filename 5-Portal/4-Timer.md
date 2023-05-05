---
title: Timer
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

- Send a valid JSON request at a set interval {% infoHover %}From once every 24 hours, to once every second.{% /infoHover %}

  ![Screenshot of the Interval dialogue](assets/interval.png)

- Turn the timer on or off

  {% callout %}
  Toggling the timer triggers a `timerStatus` request, which consumes a Ripple.
  {% /callout %}

- Run it once, or continuously

  ![Screenshot of the Actions dialogue](assets/actions.png)

## Getting there

1. [Go to the Devices page on the Portal](https://portal.fingoti.com/devices)

   ![Screenshot of the Devices page](assets/devices.png)

2. Press the Settings cog for the device you wish to use

   ![Screenshot of the Settings cog](assets/settings.png)

3. Press Timer

   ![Screenshot of the Timer menu entry](assets/timer-menu.png)

## Constructing a request

![Screenshot of the Request dialogue](assets/request.png)


JSON requests are arrays composed of a command object {% infoHover %}[Information required by the API endpoint](https://documentation.fingoti.com/reference).{% /infoHover %} and a payload object {% infoHover %}[Commands that will be executed by the device](https://documentation.fingoti.com/reference).{% /infoHover %}.

As an example, reading the temperature and humidity using the Evaluation Board would entail:

- The `sendrequest` command object

  {% contextualCallout severity="info" %}
  <https://api.fingoti.com/v1/device/sendrequest> is the URL used to send a request to a device.

  Where `api.fingoti.com` is the address of the service, `v1` is the version of the API, `device` is the category of command, and `sendrequest` is the endpoint.
  {% /contextualCallout %}


  ```json
  {
    "response": true,
    "serial": "string",
    "request": ["string"]
  }
  ```

- The `i2cData` payload object


  ```json
  {
    "property": "i2cData",
    "operation": 1,
    "payload": {
      "address": 0,
      "profile": []
    }
  }
  ```

Up to eight commands can be executed in a single array, either written by hand, or by [copying the payload from the Command Log](5-Portal/3-Command-Log.md).