---
title: Webhooks
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

{% contextualCallout severity="info" %}
You can have one or more webhooks per device property. [Device properties are listed on the Reference &rarr; Protocol page](https://documentation.fingoti.com/reference).
{% /contextualCallout %}

Webhooks enable communication between two APIs {% infoHover %}Application programming interfaces permit services to communicate with each other using documented inputs and outputs. There is no requirement to understand the internal programming of a service, only how its API will respond to a request.{% /infoHover %}. They are used by web apps to receive information.

As a demonstration: the temperature and humidity sensor on the Evaluation Board will be polled, and the result will be sent to our Node-RED service {% infoHover %}Node-RED is a browser-based interface, used to interweave '[hardware devices, APIs and online services in new and interesting ways](https://nodered.org/)'. Our Node-RED service can transform raw data from the temperature sensor into graphs and gauges.{% /infoHover %}.

If you own an Evaluation Board, you can follow this tutorial interactively.

![Screenshot of the Node-RED interface](assets/node-red.png)

## Adding a Webhook

1. [Go to the Webhooks page](https://portal.fingoti.com/webhooks)

2. Press "Add Webhook"

3. Insert the URL of the service

4. Select one or more properties

    Properties are covered in [the Reference &rarr; Protocol page](https://developer.fingoti.com/hardware/protocol).
    
    In this case, `i2cData` is required.

5. Select one or more devices

    These devices will be used as data points for the webhook.

6. Press "Save"

Whenever a Ripple is made {% infoHover %}A Ripple is a request and response sent from the Fingoti Cloud.{% /infoHover %} using the selected properties, it will be sent to the webhook.

The Fingoti Node-RED instance will convert the raw data, and present it in a human-readable fashion.

{% callout %}
Node-RED does not possess the ability to process I2C device data out of the box - this has been done by our developers, for your convenience.
{% /callout %}

## Sending commands

Commands sent using the Fingoti Cloud will trigger the webhook.


{% contextualCallout severity="info" %}
The device must have Cloud usage enabled. Refer to [Reference &rarr; Protocol &rarr; Device](https://documentation.fingoti.com/reference).
{% /contextualCallout %}

To poll the temperature and humidity sensor every ten minutes, you can:


- [Use the I2C Profile Builder to communicate with the sensor](5-Portal/2-I2C-Profile-Builder.md) 
- [Retrieve the payload object from the Command Log](5-Portal/3-Command-Log.md)
- [Insert the payload into the command object](5-Portal/4-Timer.md)
- [Set the interval using the Timer](5-Portal/4-Timer.md)

### I2C Profile Builder


1. [Follow the "Getting there" steps to open the Profile Builder](5-Portal/2-I2C-Profile-Builder.md)

2. Change the address to `68`

{% callout %}
`68` is the address of the temperature and humidity sensor.
{% /callout %}


3. Insert the following profile

    [Reference &rarr; Hardware &rarr; Evaluation Board](https://documentation.fingoti.com/reference) documents the features of the temperature and humidity sensor. This profile can be found in the "Measure and fetch" section.


    ```json
    ["S","W34","W54","S","W224","W0","S","R6","P"]
    ```

4. Press the "Send" button

You have now sent a command, which will appear on Node-RED as a point on the graph.

### Command Log

[Copy the previous command from the Command Log by following these instructions](5-Portal/3-Command-Log.md).

### Timer

1. [Follow the "Getting there" steps to open the Timer](5-Portal/4-Timer.md)

2. [Follow the "Constructing a request" steps to construct a request](5-Portal/4-Timer.md)

    Insert the payload object from the Command Log.
    
3. Add the request to the Request textbox

4. Set the interval to ten minutes

5. Press the Repeat button

6. Press the Enable button