---
description: A list of common problems and possible solutions people have with MirrorVR.
icon: triangle-exclamation
---

# Common Problems

## I don't log in at all?

There are a couple of scenarios that you could be having right now.

#### No logs from MirrorVR are appearing at all.

This is most likely because you did not follow either [meta-quest-setup.md](../getting-started/meta-quest-setup.md "mention") or [steam-setup.md](../getting-started/steam-setup.md "mention"). Please make sure you have done that.

#### 'Failed to load assembly: EOSSDK-`x`.`y`'

Double-check that you have Visual C++ v14 installed. EOS will not run without it.\
You can get it [here](https://visualstudio.microsoft.com/downloads/#microsoft-visual-c-v14-redistributable). Make sure to restart your computer after installing.

#### 'DllNotFoundException: LibOVRPlatformImpl64\_1'

You most likely don't have the Meta Horizon Link app installed on your computer.\
Download it [here](https://oculus.com/download_app/?id=1582076955407037), then restart your computer after installing.

#### 'Result.ConnectExternalTokenValidationFailed' from EOS

There are multiple reasons for this, but the most common is that you entered the wrong App ID in the EOS Identity Provider Settings. Double-check your Meta Quest EOS configuration to ensure the settings are correct.

#### 'Result.ConnectExternalServiceConfigurationFailure' from EOS

This is most likely due to not linking your Oculus Identity Provider in the live Deployment settings in EOS. Please ensure you do this.

## I log in on the Editor but not on VR?

This most likely has to do with either configuration issues or user error.

1.  First of all, make sure that whoever is using the APK has the game in their library. If they don't, the player will fail the entitlement check and, therefore, not log in.


2. The APK does not have internet permission.&#x20;
   1. You can test this by making a simple HTTP request to either `8.8.8.8` (Google's DNS Server) or `1.1.1.1` (Cloudflare's DNS Server). If both fail, you must add `android.permission.INTERNET` to your Android Manifest file.

