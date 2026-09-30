<!-- K2-OPENHOST-UPSTREAM-CONTEXT -->
> **Upstream reference:** this document is inherited from the public `k2-improvements` lineage (**jamincollins → Jacob10383**) and remains credited to its original authors/contributors. It may describe the original printer-side/K2 Plus environment. For the current **K2 Pro / K2-OpenHost** architecture and validated procedures, use [`K2-OPENHOST.md`](../../K2-OPENHOST.md) where applicable and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost). K2 Plus values are not assumed to apply unchanged to K2 Pro.

# START_PRINT

## Why

Creality's stock **START_PRINT** does not:

* handle (or wait for) chamber temperature
* handle the different offset needs of different filament types
* ensure the bed is _still_ level after rising from the bottom || it's frequently not ||

## Setup

Install this feature and update your slicer's start gcode to send the **CHAMBER_TEMP** and **MATERIAL** as parameters.

Here is an example for Creality Print:

```raw
START_PRINT EXTRUDER_TEMP=[nozzle_temperature_initial_layer] BED_TEMP=[bed_temperature_initial_layer_single] CHAMBER_TEMP=[overall_chamber_temperature] MATERIAL={filament_type[initial_tool]}
```
