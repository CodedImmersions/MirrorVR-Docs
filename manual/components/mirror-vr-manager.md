---
description: Main Manager for MirrorVR
---

# Mirror VR Manager

## Introduction

Mirror VR Manager is the core of MirrorVR. It is the main networking script. It has NetworkManager as its base class, meaning it also doubles as your Mirror Network Manager.

## Inspector Variables

All public inspector values of Mirror VR Manager. For the Network Manager fields, see the [Network Manager Docs](https://mirror-networking.gitbook.io/docs/manual/components/network-manager).

### Player Transforms

* Head (UnityEngine.Transform)
  * The GameObject that the player's head follows. Most of the time, this is the Main Camera.
* Left Hand (UnityEngine.Transform)
  * The GameObject that the player's left hand follows. Most of the time, this is the Left-Hand Controller.
* Right Hand (UnityEngine.Transform)
  * The GameObject that the player's right hand follows. Most of the time, this is the Right-Hand Controller.

### API Keys

* Product Name (string)
  * The name of your EOS Product. Usually, this is just your game's name.
* Product ID (string)
  * The ID of your EOS Product.
* Sandbox ID (string)
  * The ID of your EOS Product's live sandbox.
* Deployment ID (string)
  * The ID of your EOS Product's live deployment.
* Client ID (string)
  * The ID of the client you created in your EOS Product.
* Client Secret (string)
  * The secret key of the client you created in your EOS Product.
* Encryption Key (string)
  * A 64-character (32 hexadecimal byte) string, used to encrypt all [title-storage.md](../../learning-about-eos/title-storage.md "mention") and [player-data-storage.md](../../learning-about-eos/player-data-storage.md "mention") values.

### Settings

* Logger Level (Mirror.VR.LogLevel)
  * The log level MirrorVR logs to the console.
    * **Info** - Logs all messages
    * **Warn** - Logs Warnings and Errors
    * **Error** - Logs Errors
    * **None** - Logs nothing
* Connection Type (Mirror.VR.MirrorVRConnectionType)
  * Sets the connection type MirrorVR uses.
    * **P2P** - Uses the EOS Relay; players host servers.
    * **P2P with Encryption** - P2P option, but with the [Encryption Transport](https://mirror-networking.gitbook.io/docs/manual/transports/encryption-transport) added.
    * **Dedicated Server** - Uses a Dedicated Server to host the rooms, using the MirrorVR Dedicated Server Software.
    * **Dedicated Server with Encryption** - Dedicated Server option, but with the [Encryption Transport](https://mirror-networking.gitbook.io/docs/manual/transports/encryption-transport) added.
* P2P Settings (Mirror.VR.P2PSettings)
  * Settings for the P2P Connection Type. It's best not to mess with these settings if you don't know what you're doing.
    * **Channels** (Epic.OnlineServices.P2P.PacketReliability\[]) - The allowed channels that packets can go through.
    * **Timeout** (int) - Timeout for connecting to another player in seconds. The default is 25 seconds.
    * **Max Fragments** (int) - The max fragments used in fragmentation before throwing an error. The default is 55 fragments.
    * **Relay Control** (Epic.OnlineServices.P2P.RelayControl) - Setting for controlling whether relay servers are used. Default is Allow Relays.
* Dedicated Server Settings (Mirror.VR.DedicatedServerSettings)
  * Settings for the Dedicated Server Connection Type.
    * **Server Address** (string) - The IP Address or URL of the Dedicated Server.
    * **Main Port** (ushort) - The Main Port of the Dedicated Server, to send room requests. The default is 7777.
    * **Auth Key** (string) - The key the client sends to the main server to authenticate.
    * **Transport** (Mirror.VR.DedicatedServerTransport) - The transport to use for Dedicated Server Support. The default is KCP.
* Automatically Join Room (bool)
  * If the user should connect to a room on start. Default is false.
* Room Limit (int)
  * The default limit of users in a room. The max you can do using EOS Lobbies is 64. The default is 10.
* Random Username Prefix (string)
  * If using `Mirror.VR.MirrorVRAuthType.DeviceId`, the prefix for the default username. The default is "Player". For example, "Player1234".
* Default Color (UnityEngine.Color)
  * The default color of the user. The default is `UnityEngine.Color.black`.
* Multi Cos In Slot (bool)
  * If you would like to allow your players to be able to equip multiple cosmetics in the same slot at the same time.&#x20;

### Authentication Types

#### Editor

* Windows Editor (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for Windows in the Unity Editor. The default is `Mirror.VR.MirrorVRAuthType.Oculus`.
* Mac OS Editor (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for macOS in the Unity Editor. The default is `Mirror.VR.MirrorVRAuthType.EpicPortal`.
* Linux Editor (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for Linux in the Unity Editor. The default is `Mirror.VR.MirrorVRAuthType.EpicPortal`.

#### Runtime

* Android (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for Android/Meta Quest. The default is `Mirror.VR.MirrorVRAuthType.Oculus`.
* Windows Runtime (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for Windows at Runtime. The default is `Mirror.VR.MirrorVRAuthType.DeviceId`.
* Mac OS Runtime (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for macOS at Runtime. The default is `Mirror.VR.MirrorVRAuthType.DeviceId`.
* Linux Runtime (Mirror.VR.MirrorVRAuthType)
  * The default authentication method for Linux at Runtime. The default is `Mirror.VR.MirrorVRAuthType.DeviceId`.

### Beta Features

Features that are currently still in Beta. Expect bugs.

#### Host Migration

* Host Migration (bool)
  * Used to toggle Host Migration on or off. The default is true.
* Player Selection (Mirror.VR.HostMigrationPlayerSelection)
  * The method used to select the next player for host migration.
    * **Player Order** - Always selects the 2nd person down in the player list.
    * **Round Trip Time** - Selects the next player based on who has the lowest [RTT](https://mirror-networking.gitbook.io/docs/manual/general/round-trip-time-rtt).

## Static Methods

* `JoinOrCreateLobby(string lobbycode, int maxPlayers)`
  * A combination of `JoinLobby(string)` and `CreateLobby(string, int)` that will first check if that room exists already, and if it does, join it, but if it doesn't, create a new room.
    * `lobbycode` - The lobby code entered.
    * `maxPlayers` - The maximum number of players that can join this room. Set in-code as -1, but it is actually `MirrorVRManager.instance.roomLimit`.



* `JoinLobby(string lobbycode)`
  * Joins a lobby using the provided room code. Though it is strongly recommended to use `JoinOrCreateLobby(string, int)` instead.
    * `lobbycode` - The room code entered.



* `CreateLobby(string lobbycode, int maxPlayers)`
  * Creates a new room. Though it is strongly recommended to use `JoinOrCreateLobby(string, int)` instead.
    * `lobbycode` - The lobby code entered.
    * `maxPlayers` - The maximum number of players that can join this room. Set in-code as -1, but it is actually `MirrorVRManager.instance.roomLimit`.



* `JoinRandomLobby(int maxPlayers)`
  * Joins a random lobby.
    * `maxPlayers` - The maximum number of players that can join this room. Set in-code as -1, but it is actually `MirrorVRManager.instance.roomLimit`.



* `Disconnect()`
  * Disconnects from the current lobby.
* `string GetLobbyCode()`
  * Gets the code of the current lobby we are in.
* `Epic.OnlineServices.ProductUserId GetLobbyHost()`
  * Gets the current owner of the lobby.
* `int GetMemberCount()`
  * Get the number of members associated with this lobby.
* `Epic.OnlineServices.ProductUserId GetMemberByIndex(int index)`
  * Used to immediately retrieve individual members registered with a lobby.
    * `index` - the EOS player index, NOT the Connection ID.



* `SetUsername(string username)`
  * Sets the player username based on the provided string.
    * `username` - The new player username.
* `string GetUsername()`
  * Returns the local player's username.
* `SetColor(UnityEngine.Color color)`
  * Sets the player color based on the color provided.
    * `color` - The new color to set the player to.
* `SetCosmetic(string category, string cosmeticName)`
  * Equips the specified cosmetic.
    * `category` - The cosmetic type.
    * `cosmeticName` - The name of the cosmetic.
* `ChangeScene(string sceneName, UnityEngine.SceneManagement.SceneOperation operation)`
  * Changes the current network scene. Server-only method.
    * `sceneName` - The name of the scene.
    * `operation` - The operation to perform.

## Static Variables

Todo still. (Taking a break, I spent 7 HOURS on this page ALONE 😭)
