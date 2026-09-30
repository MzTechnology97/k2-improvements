<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Abort Homing

Stop a homing move without triggering a full emergency stop.

![Abort Homing Button](image.png)

## What it does

Implements the backend webhook for the "Force Stop Homing" button included in the custom Fluidd build. Can be used when you spot reverse homing occuring without the need for an emergency shutdown.


## Installation

```bash
./install.sh
```
