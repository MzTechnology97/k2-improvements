<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Better Init

## Why

The existing init scripts on the K2 feel like a bit of an after thought.

They don't create traditional tracking mechanisms for whether a process is running or not, such as a PID file.

The lack of these tracking mechanisms mean they don't allow integration with Moonraker and thereby Fluidd.

## Updated Init Scripts

This replaces some of the key init scripts with improved versions that do provide the process tracking.

Additionally, wrapper scripts are provided to allow integration with Moonraker and Fluidd.  This allows for service management of these processes from Fluidd's UI.
