---
title: Enabling multi-factor authentication on a Fingoti account
---

# Enabling multi-factor authentication on a Fingoti account

{% prereqList %}

{% prereqLink link="/creating-a-fingoti-cloud-account" %}
{% /prereqLink %}

{% prereqText %}
An authenticator app
{% /prereqText %}

{% /prereqList %}

{% contextualCallout severity="info" %}
Popular options for an authenticator app include Google Authenticator and Microsoft Authenticator.
{% /contextualCallout %}

1. [Go to the Security page](https://account.fingoti.com/user/security)

   ![Screenshot of the Security page](common/security.png)

2. Press Enabled

   ![Screenshot of the Enabled/Disabled toggle](enabling-multi-factor-authentication-on-a-fingoti-account/disabled.png)

<!-- NOTE: The process shown is duplicated in documentation form for completeness. -->

3. Open the authenticator app and scan the QR code (or enter the code manually)

   ![Screenshot of the Enable MFA page](enabling-multi-factor-authentication-on-a-fingoti-account/enable-mfa.png)

4. Enter the code shown in the authenticator app

   ![Screenshot of the Enable MFA page with the one-time passcode filled in](enabling-multi-factor-authentication-on-a-fingoti-account/enable-mfa-otp.png)

5. Press Verify

6. Save your recovery codes to a safe place

{% contextualCallout severity="warn" %}
If you lose access to your authenticator app or recovery codes, you will no longer be able to log in to your account.
{% /contextualCallout %}

![Screenshot of recovery codes](enabling-multi-factor-authentication-on-a-fingoti-account/recovery-codes.png)

## Viewing recovery codes

Copy recovery codes to the clipboard, download them to a `fingoti-recovery-codes.txt` file, or regenerate recovery codes.

![Screenshot of recovery codes](enabling-multi-factor-authentication-on-a-fingoti-account/recovery-codes-regenerate.png)

1. [Go to the Security page](https://account.fingoti.com/user/security)

2. Press View Recovery Codes

   ![Screenshot of the Enabled/Disabled toggle](enabling-multi-factor-authentication-on-a-fingoti-account/enabled.png)

### Regenerate codes

1. Press Regenerate Codes

2. Enter your password

   ![Screenshot of the password entry box](enabling-multi-factor-authentication-on-a-fingoti-account/regenerate-recovery-codes.png)

3. Press Regenerate

You now have a new set of codes. Any codes you saved previously will no longer function.

# Disabling multi-factor authentication

{% contextualCallout severity="warn" %}
You should only disable multi-factor authentication if you have lost your device, or authenticator vault.
{% /contextualCallout %}

1. [Go to the Security page](https://account.fingoti.com/user/security)

2. Press Enabled

   ![Screenshot of the Enabled/Disabled toggle](enabling-multi-factor-authentication-on-a-fingoti-account/enabled.png)

3. Enter your password

   ![Screenshot of the Disable MFA page](enabling-multi-factor-authentication-on-a-fingoti-account/disable-mfa-no-password.png)

4. Press Disable

   ![Screenshot of the Disable MFA page with the password filled in](enabling-multi-factor-authentication-on-a-fingoti-account/disable-mfa.png)

Multi-factor authentication is now disabled. You can safely remove Fingoti from your authenticator app, and dispose of recovery codes.

![Screenshot of the Disable MFA page with the password filled in](enabling-multi-factor-authentication-on-a-fingoti-account/mfa-disabled-toast.png)
