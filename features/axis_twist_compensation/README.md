<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# Axis Twist Compensation

## Why?

This will sound strange (since I've included it as an option), but I don't recommend using this feature.  Does it improve prints?  Yes.  Then why don't I recommend it?  IMO this simply masks the K2 issue.  Specifically it makes the K2 bed _look_ flat.

## Calibration

```raw
G28
Z_TILT_ADJUST
AXIS_TWIST_COMPENSATION_CALIBRATE AUTO=TRUE SAMPLE_COUNT=10
SAVE_CONFIG
```
