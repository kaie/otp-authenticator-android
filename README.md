otp-authenticator-android
=========================
This is the source code for the OTP Authenticator app for Android.
https://github.com/kaie/otp-authenticator-android

The OTP Authenticator project includes implementations of one-time 
passcode generators for the Android platform. One-time passcodes 
are generated using open standards developed by the Initiative for 
Open Authentication (OATH) (which is unrelated to OAuth).

This implementation supports the HMAC-Based One-time Password
(HOTP) algorithm specified in RFC 4226 and the Time-based One-time 
Password (TOTP) algorithm specified in RFC 6238.

The app supports:
* Multiple accounts
* Support for 30-second TOTP codes
* Support for counter-based HOTP codes
* Key provisioning via scanning a QR code
* Manual key entry of RFC 3548 base32 key strings 

Minimal hints for building:
- install an Android bundle (ADT)
- get jdk 6
- set JAVA_HOME
- add adt/.../sdk/tools and jdk/bin directories to PATH
- install support for API versions 7 and 14
- follow instructions to create a key store, e.g.
  keytool -genkey -v -keystore kaiengert-release-key.keystore \
    -alias kaiengert -keyalg RSA -keysize 2048 -validity 10000
- update build files:
  android update project --path .
- add keystore information to file local.properties, e.g.:
  key.store=/home/username/kaiengert-release-key.keystore
  key.alias=kaiengert
- build:
  ant release

Disclaimer:
This is a fork of Google Authenticator, based on version 2.21, the
last version that was available as open source, which has been
obtained from https://code.google.com/p/google-authenticator/
