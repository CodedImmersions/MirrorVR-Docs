---
description: Coming from PhotonVR? Here's how to migrate everything over!
icon: circle-p
---

# PhotonVR to MirrorVR

Converting from Photon PUN 2 / PhotonVR can be a bit of a hassle, but it ends up working nicely.

There will be two sections to this page: The conversion steps and networking equivalents.\
Make sure you thoroughly read this!

## Conversion

{% stepper %}
{% step %}
Follow [getting-started](../getting-started/ "mention") and either [meta-quest-setup.md](../getting-started/meta-quest-setup.md "mention") or [steam-setup.md](../getting-started/steam-setup.md "mention") to start.
{% endstep %}

{% step %}
Keep Photon in your project for now, so you can switch stuff over correctly.\
Will finish later haha
{% endstep %}
{% endstepper %}

## Equivalents

Here's a list of equivalents between PUN 2 and MirrorVR.

| Photon PUN 2 Script                                                                                                                       | Equivalent Mirror Script                                                                                               |
| ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [PhotonNetwork](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_photon_network.html)                             | [NetworkManager](https://storage.googleapis.com/mirror-api-docs/html/d7/d5a/class_mirror_1_1_network_manager.html)     |
| [MonoBehaviourPun(Callbacks)](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_mono_behaviour_pun_callbacks.html) | [NetworkBehaviour](https://storage.googleapis.com/mirror-api-docs/html/db/d21/class_mirror_1_1_network_behaviour.html) |
| [Photon View](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_photon_view.html)                                  | [Network Identity](https://storage.googleapis.com/mirror-api-docs/html/d3/d88/class_mirror_1_1_network_identity.html)  |
| [Photon Transform View](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_photon_transform_view.html)              | [Network Transform](https://mirror-networking.gitbook.io/docs/manual/components/network-transform)                     |
| [Photon Rigidbody View](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_photon_rigidbody_view.html)              | [Network Rigidbody](https://mirror-networking.gitbook.io/docs/manual/components/network-rigidbody)                     |
| [Photon Animator View](https://doc-api.photonengine.com/en/pun/current/class_photon_1_1_pun_1_1_photon_animator_view.html)                | [Network Animator](https://mirror-networking.gitbook.io/docs/manual/components/network-animator)                       |
