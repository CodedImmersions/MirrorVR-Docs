---
description: How to setup and use Dissonance with MirrorVR.
icon: microphone-lines
---

# Dissonance with MirrorVR

Dissonance is one of the most popular voice chat systems for Unity.



## Prerequisites

To begin, you must have already bought [Dissonance](https://assetstore.unity.com/packages/tools/audio/dissonance-voice-chat-70078) on the Unity Asset Store and have put it in your project. It's $100, so please only get it if you can afford it. If you can't, don't go onto the dark web to try to get it. You'll most likely get malware, not the Unity package you were thinking of. MetaVoiceChat comes pre-installed, which works really well right off the bat.<br>

You also need to have [Dissonance for Mirror](https://assetstore.unity.com/packages/tools/integration/dissonance-for-mirror-networking-143290) imported into your project. It's a free add-on to Dissonance that allows the proper Mirror setup.



## Guide

Here's the guide on how to set up and use Dissonance with MirrorVR!

### 1. MetaVoiceChat Removal

{% stepper %}
{% step %}
Go to Assets/MirrorVR, and open the Player prefab.

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Under Player/Head, delete the Voice Chat and VoiceChatOutput GameObjects.

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
Go to Assets/MirrorVR/Third-Party, and delete the Metater folder.
{% endstep %}
{% endstepper %}

### 2. Addition of Dissonance

{% stepper %}
{% step %}

{% endstep %}

{% step %}

{% endstep %}
{% endstepper %}

