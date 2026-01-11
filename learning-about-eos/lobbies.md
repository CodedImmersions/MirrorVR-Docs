---
icon: users-between-lines
---

# Lobbies

Lobbies provide easy matchmaking in MirrorVR.

{% hint style="info" %}
Note that lobbies do NOT send data; they are only for matchmaking players.\
If you would like to know how the actual data is sent, go to [nat-p2p.md](nat-p2p.md "mention")instead.
{% endhint %}

## Creating/joining a lobby

In MirrorVR, there are many ways to join lobbies.

#### JoinOrCreateLobby

Creating/joining a lobby works in this order:

1. Using the `lobbycode` (string) provided, it searches in the EOS system for an existing lobby with the same name.
2. If one is found, it auto-joins that lobby.
3. If one is not found, it auto-creates a lobby using the parameters provided and connects you to it.

Here is a code example showing you how to use JoinOrCreateLobby():

{% code lineNumbers="true" %}
```csharp
using UnityEngine;
using Mirror.VR;

public class JoinOrCreateLobbyExample : MonoBehaviour
{
    public string lobbyCode = "MirrorVRLobby";
    public int maxPlayers = 10;

    private void Start()
    {
        JoinOrCreate();
    }

    public void JoinOrCreate()
    {
        MirrorVRManager.JoinOrCreateLobby(lobbyCode, maxPlayers);
    }
}
```
{% endcode %}

#### CreateLobby

This function is self-explanatory. It allows you to manually create a lobby using the provided parameters.

Code Example:

{% code lineNumbers="true" %}
```csharp
using UnityEngine;
using Mirror.VR;

public class CreateLobbyExample : MonoBehaviour
{
    public string lobbyCode = "MirrorVRLobby";
    public int maxPlayers = 10;

    private void Start()
    {
        Create();
    }

    public void Create()
    {
        MirrorVRManager.CreateLobby(lobbyCode, maxPlayers);
    }
}
```
{% endcode %}

#### JoinLobby

JoinLobby is also pretty self-explanatory. It allows you to manually join a lobby using the code provided.

Code Example:

{% code lineNumbers="true" %}
```csharp
using UnityEngine;
using Mirror.VR;

public class JoinLobbyExample : MonoBehaviour
{
    public string lobbyCode = "MirrorVRLobby";

    private void Start()
    {
        Join();
    }

    public void Join()
    {
        MirrorVRManager.JoinLobby(lobbyCode);
    }
}
```
{% endcode %}

#### JoinRandomLobby

JoinRandomLobby allows you to join a "public" lobby. Public lobbies are lobbies that don't really require a lobby code to join.

The generated lobby codes can range from 10000 to 99999, so effectively 5 digits.

Public lobbies are filled in an "available player slots" order, meaning you will always join the public lobby with the fewest player slots available.

Example: Player 1 wants to join a random.\
There are currently two public lobbies open: 12345 and 54321.\
12345 has 2/10 slots filled, while 54321 has 7/10 slots filled.\
\
As per the code logic, Player 1 will always join public 54321, due to it having the least non-zero slots filled.

If all slots in all open lobbies are filled, Player 1 will simply create a new public lobby for other players to join.

Code Example:

{% code lineNumbers="true" %}
```csharp
using UnityEngine;
using Mirror.VR;

public class JoinRandomLobbyExample : MonoBehaviour
{
    //Only used IF we are creating a lobby from this method.
    public int maxPlayers = 10;

    private void Start()
    {
        JoinRandom();
    }

    public void JoinRandom()
    {
        MirrorVRManager.JoinRandomLobby(maxPlayers);
    }
}
```
{% endcode %}

## Kicking a player

There are four ways to kick a player from the lobby.\
ALL of them, you have to be a lobby host to do.

#### MirrorVRManager.KickPlayer

#### MirrorVRPlayer.KickPlayer

#### LobbyInterface.KickMember

#### NetworkConnectionToClient.Disconnect

## Extracting lobby data

## Lobby attributes
