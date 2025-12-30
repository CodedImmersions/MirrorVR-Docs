---
description: A list of common problems and possible solutions people have with MirrorVR.
icon: triangle-exclamation
---

# Common Problems

## I log in on the Editor but not on VR?

This most likely has to do with either configuration issues or user error.

1.  First of all, make sure that whoever is using the APK has the game in their library. If they don't, the player will fail the entitlement check and, therefore, not log in.


2. The APK does not have internet permission.&#x20;
   1. You can test this by making a simple HTTP request to either `8.8.8.8` (Google's DNS Server) or `1.1.1.1` (Cloudflare's DNS Server). If both fail, you must add `android.permission.INTERNET` to your Android Manifest file.

