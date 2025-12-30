---
description: MirrorVR Frequently Asked Questions
icon: circle-question
coverY: 0
---

# FAQ

## Supported Unity Versions

<table><thead><tr><th width="152.46875">Version</th><th width="344">Support Status</th><th>Supported by Unity</th><th data-hidden>Supported Until</th></tr></thead><tbody><tr><td>6000.5 Alpha</td><td><mark style="color:green;">Supported</mark></td><td><mark style="color:green;">Yes</mark></td><td></td></tr><tr><td>6000.4 Beta</td><td><mark style="color:green;">Supported</mark></td><td><mark style="color:green;">Yes</mark></td><td>N/A</td></tr><tr><td>6000.3 LTS</td><td><mark style="color:green;">Supported</mark></td><td><mark style="color:green;">Yes, until 12/2027</mark></td><td>N/A</td></tr><tr><td>6000.2</td><td><mark style="color:green;">Supported</mark></td><td><mark style="color:red;">No</mark></td><td>N/A</td></tr><tr><td>6000.1</td><td><mark style="color:green;">Supported</mark></td><td><mark style="color:red;">No</mark></td><td>Aug 13, 2025</td></tr><tr><td>6000.0 LTS</td><td><mark style="color:$success;">Supported with 6000.0.38f1+</mark></td><td><mark style="color:green;">Yes, until 10/2026</mark></td><td>Oct 2026?</td></tr><tr><td>2023</td><td><mark style="color:orange;">Supported up to EOSSDK 1.17.1.3</mark></td><td><mark style="color:red;">No</mark></td><td>Apr 25, 2024</td></tr><tr><td>2022</td><td><mark style="color:orange;">Supported up to EOSSDK 1.17.1.3</mark></td><td><mark style="color:red;">No</mark></td><td>May 7, 2025</td></tr><tr><td>2021 and below</td><td><mark style="color:red;">Unsupported</mark></td><td><mark style="color:red;">No</mark></td><td>Oct 16, 2024</td></tr></tbody></table>

### Why are X, Y, and Z versions not supported with the latest SDK?

Your version is not supported with the latest SDK because Epic raised the NDK version requirement to r27c in 1.18.0.4. At this time, only 6000.0.38f1 and later support r27c; the rest are below the required level (r23b/r21d).\
\
Learn more here:

* [EOS SDK Release Notes](https://dev.epicgames.com/docs/epic-online-services/whats-new)
* [EOS SDK 1.18.0.4 Release Notes](https://dev.epicgames.com/docs/epic-online-services/whats-new#eos-11804---cl45343210---2025-sept-16)

SDK/NDK/JDK Dependencies:

* [For 6000.1-6000.4](https://docs.unity3d.com/6000.3/Documentation/Manual/android-supported-dependency-versions.html)
* [For 2023-6000.0](https://docs.unity3d.com/6000.0/Documentation/Manual/android-supported-dependency-versions.html)
* [For 2022](https://docs.unity3d.com/2022.3/Documentation/Manual/android-supported-dependency-versions.html)
* [For 2021](https://docs.unity3d.com/2021.3/Documentation/Manual/android-supported-dependency-versions.html)

### How do I upgrade my NDK?

You can upgrade your NDK by visiting the [NDK r27c GitHub Release](https://github.com/android/ndk/releases/tag/r27c) and downloading the NDK version compatible with your OS. You download it by finding the table toward the top of the release.

After you have downloaded it, extract it to a location you'll remember for later. For example, I saved it in `C:/Users/THeTechWiz/NDK-r27c`.

Now, open your Unity project, and go to `Edit > Preferences > External Tools > Android` (or `Unity > Settings > External Tools > Android` if you're on macOS). Uncheck "Android NDK Installed with Unity (recommended)" and put in your new NDK path.

## Is Host Migration implemented?

Also known as when the host disconnects, everyone disconnects.

YES! We have implemented host migration. It is a part of EOSTransport, not MirrorVR directly.
