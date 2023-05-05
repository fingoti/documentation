---
title: Power a device
---

{% prereqList %}

None.

{% /prereqList %}

## Methods

You can power a device using:

{% tabs %}

{% tab label="USB to Serial Adapter Board" %}



- A USB-C cable
- A 5V power supply

{% contextualCallout severity="info" %}
Before connecting, ensure the Fingoti logo on your Adapter Board is facing downwards, and the Fingoti logo on your device is facing upwards.
{% /contextualCallout %}

{% contextualCallout severity="warning" %}
If wired incorrectly, the device will not power on.
{% /contextualCallout %}

{% /tab %}

{% tab label="Evaluation Board" %}



- A USB-C cable
- A 5V power supply

{% contextualCallout severity="info" %}
Before connecting, ensure the Fingoti logo on your device is facing upwards.
{% /contextualCallout %}

{% contextualCallout severity="warning" %}
If wired incorrectly, the device will not power on.
{% /contextualCallout %}

{% /tab %}

{% tab label="Generic USB to Serial Adapter Board" %}


- An adequate power supply (refer to the documentation supplied by the manufacturer)
- Jumper wires to connect the header pins, according to the pinout diagram

{% contextualCallout severity="warning" %}
If wired incorrectly, the device will not power on.
{% /contextualCallout %}

{% /tab %}

{% tab label="Breadboard or Direct Connection" %}


- An adequate power supply (refer to the documentation supplied by the manufacturer)
- Jumper wires to connect the header pins, according to the pinout diagram

{% contextualCallout severity="warning" %}
If wired incorrectly, the device will not power on.
{% /contextualCallout %}

{% /tab %}

{% /tabs %}

## Key


When the device has powered on, it will turn {% badge bgColor="#FF0000" textColor="#FFFFFF" %}Red{% /badge %}.

When the device has connected to the WiFi network, it will turn {% badge bgColor="#FFFF00" textColor="#000000" %}Yellow{% /badge %}.

When the device has connected to the Fingoti Cloud (or a custom broker), it will turn {% badge bgColor="#008000" textColor="#FFFFFF" %}Green{% /badge %}.
