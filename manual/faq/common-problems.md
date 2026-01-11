---
description: A list of common problems and possible solutions people have with MirrorVR.
icon: triangle-exclamation
---

# Common Problems

## I don't log in at all?

There are a couple of scenarios that you could be having right now.

#### No logs from MirrorVR are appearing at all.

This is most likely because you did not follow either [meta-quest-setup.md](../getting-started/meta-quest-setup.md "mention") or [steam-setup.md](../getting-started/steam-setup.md "mention"). Please make sure you have done that.

#### I get a&#x20;

## I log in on the Editor but not on VR?

This most likely has to do with either configuration issues or user error.

1.  First of all, make sure that whoever is using the APK has the game in their library. If they don't, the player will fail the entitlement check and, therefore, not log in.


2. The APK does not have internet permission.&#x20;
   1. You can test this by making a simple HTTP request to either `8.8.8.8` (Google's DNS Server) or `1.1.1.1` (Cloudflare's DNS Server). If both fail, you must add `android.permission.INTERNET` to your Android Manifest file.

