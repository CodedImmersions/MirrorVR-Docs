---
hidden: true
---

# Host Migration Controller

## Introduction

The MirrorVR Host Migration Controller does exactly what it says: Controls Host Migration. It controls backing up data and migrating to the next host. There isn't much to say about host migration; it's just an act of transferring server ownership when the original host leaves.

## Inspector Variables

* Backup Refresh Interval (float)
  * The interval at which backup data refreshes. The default is 0.2.
* Local Backup (List, Read-Only)
  * Shows the backup data in the inspector as read-only.
