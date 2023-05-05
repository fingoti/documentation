---
title: Send commands to a device
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

{% callout %}
If you claimed using serial, you've already sent a command!
{% /callout %}

With device commands, you can request information or actions.

To request the colour of the device's LED {% infoHover %}Light-emitting diodes (LEDs) are effectively small lightbulbs, some of which can change colour.{% /infoHover %} using the Timer:

```json
{
  "request": [
    {
      "property": "deviceColour",
      "operation": 0
    }
  ]
}
```


{% contextualCallout severity="info" %}
API requests are composed differently depending on the method used. Consult the truth table in Reference &rarr; API for more information.
{% /contextualCallout %}

The device will then reply.

```json
{
  "property": "deviceColour",
  "success": true,
  "result": {
    "colour": [0, 255, 0]
  }
}
```

The `"colour"` array represents the red, green, and blue colour channels, respectively. Values can be between 0 and 255 {% infoHover %}Known as RGB values{% /infoHover %}. In this case, the colour is green.