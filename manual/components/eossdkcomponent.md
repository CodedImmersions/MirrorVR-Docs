---
hidden: true
---

# EOSSDKComponent

## Introduction

EOSSDKComponent is the core of Epic Online Services in MirrorVR. It's the link to the login provider you set and Epic Online Services.

The file has gone through many editing phases, so it may look all out of whack.\
\
First, FakeByte, the original maintainer of EOSTransport, made the file and did a lot of the work.\
Next, Ludogram, the next maintainer of EOSTransport, added a few things to make EOSTransport work smoothly.\
After that, Katone took over as maintainer and made a lot of changes to fix bugs and improve performance.\
Finally, the MirrorVR team modified it to add things required for MirrorVR, such as Meta Quest login.<br>

## Static Methods

* `Initialize()`
  * Used to initialize Epic Online Services. MirrorVR handles this for you, so please don't touch this.
* `Get[X]Interface()`
  * Used to get a certain interface. This is broad in the docs, since there are tons of them.\
    Example: `EOSSDKComponent.GetConnectInterface();`

## Static Variables

* `DisplayName` (string)
  * Stores the user's display name.
* `LocalUserAccountId` (Epic.OnlineServices.EpicAccountId)
  * Returns the Epic Account ID of the current user. \
    Don't use this; use LocalUserProductId instead. Null if not using the Auth Interface.
* `LocalUserAccountIdString` (string)
  * Returns LocalUserAccountId in string form. Alternatively, you can use LocalUserAccountId.ToString() to get the same result.\
    Don't use this; use LocalUserProductId instead. Null if not using the Auth Interface.
* `LocalUserProductId` (Epic.OnlineServices.ProductUserId)
  * Returns the Product User ID of the current user. This is what you can use to identify players and ban them.
* `LocalUserProductIdString` (string)
  * Returns LocalUserProductId in string form. Alternatively, you can use LocalUserProductId.ToString() to get the same result.
* `Initialized` (bool)
  * Returns true if the current user is logged into Epic Online Services; Otherwise false.
* `IsConnecting` (bool)
  * Returns true if the current user is in the process of initializing, but has not initialized yet. If the current user is initialized or is not initializing yet, this will return false.
* `Instance` (EpicTransport.EOSSDKComponent)
  * Returns the one and only EOSSDKComponent instance.

