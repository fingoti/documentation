---
title: Crash course in number bases
---

In computing, there are three commonly used number bases.

Decimal - Base-10

Binary - Base-2

Hexadecimal - Base-16

The same value is presented differently depending on the base. For example, the number twelve:

| Decimal | Binary    | Hexadecimal |
| ------- | --------- | ----------- |
| `12`    | `0b 1100` | `0x0C`      |


{% contextualCallout severity="info" %}
The prefix `0x` is used to denote that the number is base-16, not base-10 or base-2.

Whereas, the prefix `0b` is used to denote that the number is base-2, not base-10 or base-16.
{% /contextualCallout %}

## Decimal

Decimal is the number system taught in schools, and is used everywhere from accountancy, to keeping score in sports. A single digit can contain a value between 0 and 9.

When read from right to left, the power of ten {% infoHover %}Also known as exponents and indices.{% /infoHover %} for each position {% infoHover %}You can think of positions as columns.{% /infoHover %} increases. For example, the number `610` is calculated as:

| `10^2` | `10^1` | `10^0` |
| ------ | ------ | ------ |
| `6`    | `1`    | `0`    |

Therefore, the value is the sum of:

```
(6 * (10^2)) + (1 * (10^1)) + (0 * (10^0))
```

Or simply:

```
600 + 10 + 0
```

{% contextualCallout severity="info" %}
Any number (except zero) to the power of zero is equal to one.
{% /contextualCallout %}

## Binary

A binary number can contain a value of 0 or 1. Binary numbers are expressed as bits and bytes.

Bit - A binary digit

Byte - Contains eight bits

For each position (or column), the power of 2 increases.

| `2^7` | `2^6` | `2^5` | `2^4` | `2^3` | `2^2` | `2^1` | `2^0` |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| `128` | `64`  | `32`  | `16`  | `8`   | `4`   | `2`   | `1`   |

The leftmost bit is equal to `128`, and the rightmost bit is equal to `1`.

{% contextualCallout severity="warning" %}
This is an example of an unsigned byte.

With a signed byte, the leftmost bit becomes the sign bit, which determines if the value is positive or negative.

i.e., From -127, to 0, to 127.
{% /contextualCallout %}

You can view bits as being flipped on or off, like a light switch. When they are flipped, the value can be added or subtracted from the total.

Take the following byte:

```
0b 0000 0001
```

Only the rightmost bit is turned on, therefore the total is `1`.

```
0b 0000 0101
```

Another bit has been turned on, with a value of `4`. The total is now `5`.

```
0b 0001 0100
```

The rightmost bit has been turned off, subtracting the value of `1`. Another bit has been turned on, with a value of `16`. The total is now `20`.

Try it for yourself, using the table above.

```
0b 1010 1010
0b 1100 0011
0b 1001 0111
0b 0010 1110
```

## Hexadecimal

A single digit can contain a value between 0 and 15. Values between `0` and `9` are expressed as numbers; values between `10` and `15` are expressed using the letters `A`, `B`, `C`, `D`, `E`, and `F`.

Hexadecimal numbers are expressed as a pair of nibbles, which form a byte.

Nibble - Contains four bits

| Decimal | Binary         | Hexadecimal |
| ------- | -------------- | ----------- |
| `17`    | `0b 0001 0001` | `0x11`      |
| `44`    | `0b 0010 1100` | `0x2C`      |

Hexadecimal is effectively shorthand for binary.

Try it for yourself, converting to binary and decimal.

```
0x05
0x83
0x4F
0x8B
```
