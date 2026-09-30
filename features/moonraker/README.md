<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Moonraker

## Why

The version of Moonraker on the K2 is old (how old?) and missing features like:

* log rotation.
* Home Assistant integration

The updated Moonraker version also brings with it access to other integrations such as:

* [SimplyPrint](https://simplyprint.io/)

## Log Rotation

Being able to rotate your `klippy.log` and `moonraker.log` files helps in reducing the size of the files when asking for help or reporting an issue.

## Home Assistant

While not a core feature of Moonraker, there's something the Home Assistant integration is looking for that is missing from the Moonraker version on the K2.  Just another added benefit of updating.
