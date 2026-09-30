<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Cartographer Firmware

A flashing script has been included that can flash your cartographer device on the K2. This can be run with or without k2-improvements installed. Without bootstrap, manually copy the `firmware/` folder to the K2 and run `flash.py`. Otherwise, bootstrap will have cloned the repo, so you can run:
```bash
python3 /mnt/UDISK/root/k2-improvements/features/cartographer/firmware/flash.py
```

Connect the Cartographer via USB, then follow the prompts.

The script supports cartographer v3 and v4.

Otherwise, you can follow the official guide to flash the cartographer on another device:  
https://docs.cartographer3d.com/cartographer-probe/firmware/updating-firmware