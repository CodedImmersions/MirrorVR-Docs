---
description: MirrorVR PlayFab Setup Guide
icon: play
---

# PlayFab with MirrorVR

{% hint style="danger" %}
It is strongly recommended not to use PlayFab with MirrorVR, as it compromises the primary purpose of MirrorVR: security.
{% endhint %}

## Introduction

PlayFab, owned by Microsoft Azure, is one of the most popular player management backends for Unity.

## Setup

Here's how to set up PlayFab with MirrorVR!\
This guide will be from scratch and shown in a new project.

{% stepper %}
{% step %}
Ensure you've fully set up MirrorVR, using [getting-started](../getting-started/ "mention"), and either [meta-quest-setup.md](../getting-started/meta-quest-setup.md "mention") and/or [steam-setup.md](../getting-started/steam-setup.md "mention").
{% endstep %}

{% step %}
Download the latest PlayFab Unity SDK [here](https://raw.githubusercontent.com/PlayFab/UnitySDK/master/Packages/UnitySDK.unitypackage), and import it into your project.\
Also, download MirrorVR PlayFab in the latest release [here](https://github.com/CodedImmersions/MirrorVR/releases/latest).
{% endstep %}

{% step %}
Now, go to `Assets/MirrorVR/Extensions/PlayFab/Prefabs` and drag the `MirrorVR PlayFab` prefab into the scene somewhere.

{% hint style="warning" %}
At this time, MirrorVR PlayFab does not log in for you; you need to log in yourself via another script.
{% endhint %}
{% endstep %}

{% step %}
Select the prefab in your scene, then hit the Shared Settings button in the inspector of the script to set up your PlayFab.
{% endstep %}

{% step %}
Once you have opened PlayFab Shared Settings, fill out the Title ID.

{% hint style="danger" %}
Do NOT fill out the developer secret key, as it allows bad actors to do ANYTHING in the Admin or Server API, such as editing cloudscript, giving players items, deleting or banning/unbanning all player accounts, or even deleting the entire title itself.
{% endhint %}
{% endstep %}

{% step %}
Now, go to the Network Manager, go to the MirrorVR Manager inspector, and change your inventory service from `EOS Player Data Storage` to `PlayFab`.
{% endstep %}

{% step %}
And you're all set to use PlayFab in your MirrorVR game!
{% endstep %}
{% endstepper %}
