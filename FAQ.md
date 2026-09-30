# FAQ

> **Fork context:** this FAQ originates from the `k2-improvements` upstream lineage (`jamincollins` / `Jacob10383`) and mainly describes the classic printer-side K2 improvements environment. It is preserved for attribution and reference. For the current K2 Pro external-host architecture, use [K2-OPENHOST.md](K2-OPENHOST.md) and [MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost).

## Can I still use the auto calibrate features?

A: Unfortunately, at this time they are not supported. No.

## I've installed the Fluidd update, but the camera doesn't show up

A: Have you tried using Firefox? As far as we can tell this is due to an odd interaction between Creality's WebRTC implementation and Chrome based browsers.

## My bed crashes into the bottom! What did you do?

A: This has nothing to do with the K2 improvements. Sadly, many of us have seen this with the stock 1.1.2.x series firmware.

## Why is the printer homing to the back and erroring? What did you do?

A: See above, this is a bug with the 1.1.2.x firmware.

## My touch screen doesn't show temperatures until I home my printer! What did you do?

A: See above, this is a bug with the 1.1.2.x firmware.

## When I print from the side spool, the printer still acts like I'm using the CFS

A: This is an issue with the k2-improvements. We suspect it has something to do with the moonraker update and are investigating.

For now a workaround is to remove this line from your machine start g-code when using the side spool:

```raw
T[initial_no_support_extruder]
```

## Fluidd seems to hang at 99% even though the print appears to have finished

A: It appears that this is an issue with Creality Print not placing a newline at the end of the sliced gcode.

## Does this FAQ describe K2-OpenHost?

No. K2-OpenHost moves Kalico/Moonraker to an external host and uses the K2 Pro T113 primarily as a display/peripheral bridge. The canonical status and test documentation is maintained in `MzTechnology97/K2-OpenHost`.