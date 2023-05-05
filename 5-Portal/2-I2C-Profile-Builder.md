---
title: I2C Profile Builder
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
(Optional) An Evaluation Board
{% /prereqText %}

{% /prereqList %}

The I2C protocol {% infoHover %}A protocol establishes a common language for computers to communicate with. It defines a set of semantic rules for how data should be formatted and processed.{% /infoHover %} enables communication between controllers (processors and microcontrollers) {% infoHover %}There can be one or more controllers present, which are responsible for managing the integrated circuits.{% /infoHover %} and targets (integrated circuits) {% infoHover %}Integrated circuits are peripheral devices installed on the same board as the controllers, and can be anything from a real-time clock, to an LED display.{% /infoHover %}.

The Evaluation Board has three targets - a temperature and humidity sensor, a 64-Kb memory chip {% infoHover %}Otherwise known as electrically erasable programmable read-only memory (EEPROM){% /infoHover %}, and an ambient light sensor.

## Getting there

1. [Go to the Devices page on the Portal](https://portal.fingoti.com/devices)

   ![Screenshot of the Devices page](assets/devices.png)

2. Press the Settings cog for the device you wish to use

   ![Screenshot of the Settings cog](assets/settings.png)

3. Press I2C (to the left &larr; of the page)

   ![Screenshot of the I2C menu](assets/i2c.png)

## Your first profile

Welcome to the Profile Builder page. Don't worry about the Setup or Device Detection sections at this stage.

{% callout %}
When device detection is enabled, the `i2cDetect` command is sent, which consumes a Ripple.
{% /callout %}

![Screenshot of the Profile Builder page](assets/builder.png)

As a demonstration, data will be written to the memory chip on the Evaluation Board.

If you own an Evaluation Board, you can follow this tutorial interactively.

{% contextualCallout severity="warning" %}
The Write Protection Register (WPR) on the memory chip must be disabled.

If you have modified the value of this register, see Section 8.2 "Write Protection Register", on pages 21-22 of the datasheet.

Otherwise, you do no need to take any action, and can continue following the tutorial.
{% /contextualCallout %}

![Screenshot of the Profile Builder dialogue](assets/profile-builder.png)

1.  Set the address {% infoHover %}The device address is the logical location of the integrated circuit on a given board.{% /infoHover %} to `80`

    ![Screenshot of the Address spinner](assets/address.png)

    The device's address is assigned at the factory, and corresponds to a value between 3 and 119.

    {% callout %}
    The I2C Profile Builder automatically inserts the device address and read/write bit into the Start condition.
    {% /callout %}

2.  Press Add

    ![Screenshot of the Add button](assets/command-add.png)

    {% callout %}
    The default command is Start, which initiates a transaction. Profiles must begin with a Start condition.
    {% /callout %}

3.  Press Command

    ![Screenshot of the Command dropdown](assets/command.png)

4.  Press Write

    ![Screenshot of the Command dropdown with Write selected](assets/write.png)

    The next time you press Add, it will add a Write condition.

    ![Screenshot of the Write Command](assets/write-dropdown.png)

    At this stage, you want to set the word address. The word address functions like a cursor - you place the mouse cursor where you want to start writing.

    Here, the value of the 0th byte should be `0`, and the value of the 1st byte should be `1`.

    {% contextualCallout severity="info" %}
    Refer to [Reference &rarr; Hardware &rarr; Evaluation Board](https://documentation.fingoti.com/reference) for more information.
    {% /contextualCallout %}

5.  Press Add

    ![Screenshot of the Add button](assets/add.png)

    The default value of bytes is `0`.

    ![Screenshot of the Bytes textbox](assets/bytes-0.png)

6.  Change bytes to `1`

    ![Screenshot of the Bytes textbox](assets/bytes-1.png)

7.  Press Add

    ![Screenshot of the Add button](assets/add.png)

8.  Change bytes to `180`

    ![Screenshot of the Bytes textbox](assets/bytes-180.png)

9.  Press Add

    ![Screenshot of the Add button](assets/add.png)

10. Press Command

    ![Screenshot of the Write Command](assets/write-dropdown.png)

11. Press Stop

    ![Screenshot of the Stop Command](assets/stop.png)

    {% callout %}
    The Stop command terminates a transaction. Profiles must end with a Stop condition.
    {% /callout %}

12. Press Add

    ![Screenshot of the Add button](assets/add.png)

13. Press Send

    ![Screenshot of the Send button](assets/send.png)

Data has now been written to the memory chip, and will be saved persistently {% infoHover %}In other words, non-volatile memory - memory which is accessible even after power has been removed.{% /infoHover %}.

The Profile Builder is an interface, and will construct commands for you. The command that was built can be seen in the Send textbox.

![Screenshot of the Send textbox](assets/send-command.png)

The command can be copied by pressing the button on the right.

### Review

- `S`

  The Start condition, required to initiate a transaction.

  {% contextualCallout severity="info" %}
  Unlike typical I2C transactions, the device address and read/write bit are automatically inserted into the Start condition.
  {% /contextualCallout %}

- `W0`, `W1`

  Positions the cursor, before you start writing.

- `W180`

  The byte to write.

- `P`

  The Stop condition, required to terminate a transaction.

## Reading from the memory chip

You can construct a request using the Profile Builder, or write one yourself and paste it into the Send box.

1. Place your cursor inside the Send box

   ![Screenshot of the Send textbox](assets/send-cursor.png)

2. Remove the contents

   Triple-click {% infoHover %}Click three times in under one second.{% /infoHover %}, then right-click and select Delete.

   ![Screenshot of the Send textbox](assets/send-invalid.png)

3. Copy the following request

   1. Place the mouse cursor at the beginning of the text

   2. Press and hold until the end of the text
   
   3. Let go
   
   4. Right-click
   
   5. Select Copy

   ```json
   ["S", "W0", "W1", "S", "R1", "P"]
   ```

   {% contextualCallout severity="info" %}
   Refer to [Reference &rarr; Hardware &rarr; Evaluation Board](https://documentation.fingoti.com/reference) for more information.
   {% /contextualCallout %}

4. Paste the request into the Send box

   1. Place the cursor inside the Send box
   2. Right-click
   3. Select "Paste"

   ![Screenshot of the Send textbox](assets/send-read.png)

5. Press Send

   ![Screenshot of the Send button](assets/send.png)

   You will see the value `180`, written earlier.

   ![Screenshot of the Receive textbox](assets/receive.png)

### Review

- `S`

- `W0`, `W1`

  Positions the cursor, before you start reading.

- `S`

  A repeated Start condition is required to flip the read/write bit.

- `R1`

  Read a single byte.

- `P`
