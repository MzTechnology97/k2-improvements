<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# BED MESH

## Why

The K2 bed flexes quite a lot between ambient (cold) and heat soaked at the desired printing temperature.  So, it is best to take a bed mesh at your desired printing temperature.  However, the K2 also has both a large bed and a slow probe.  As a result taking a detailed bed mesh at your desired printing temperature can add a non trivial amount of time to your print, each time.

But doesn't the K2 already take a bed mesh?

Yes, but during calibration it creates a bed mesh, but this is done at ambient temps.  I highly doubt anyone is printing at ambient temperatures.  Additionaly, it only stores a single "default" bed mesh.

## Use
