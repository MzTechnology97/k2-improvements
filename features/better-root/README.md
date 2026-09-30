<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Better Root

## Why

The `root` home directory resides on a rather small filesystem (~220 meg).

Typical **Klipper** based printers have the various components installed/visible directly from the user's home directory.  For example:

```sh
$ ls -1
crowsnest
fluidd
fluidd-config
kiauh
kiauh-backups
klipper
klippy-env
moonraker
moonraker-env
printer_data
```

This replicates much of this by moving the `root` home directory to `/mnt/UDISK` and symlinking the various components in place:

```sh
# ls -1
fluidd
klipper
klippy-env
moonraker
moonraker-env
printer_data
```

This is also a prerequisite for almost every application addition or update in this repository.  They will be installed in the `root` users home directory, like normal **Klipper** based printers.

## What to expect

The `install.sh` will move any existing contents of the `root` home directory to the new location `/mnt/UDISK/root`, update the system with the new location, symlink the various components into their expected location, and log you out.  The log out is needed to ensure that the `root` user's home directory is fully updated for future sessions/commands.
