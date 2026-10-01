# K2 Pro Improvements — K2-OpenHost reference fork

This repository is kept as a **K2 Pro / K2-OpenHost reference fork** in the public `k2-improvements` lineage.

## Upstream lineage and credits

The original authorship chain is intentionally preserved:

1. **[jamincollins/k2-improvements](https://github.com/jamincollins/k2-improvements)** — original project and feature work;
2. **[Jacob10383/k2-improvements](https://github.com/Jacob10383/k2-improvements)** — Jacob's fork, K2 integration work and the direct parent of this repository;
3. **MzTechnology97/k2-improvements** — local K2 Pro/OpenHost reference fork.

The original authors and contributors retain credit for their code, scripts, documentation and reverse-engineering work. This fork does not claim authorship of upstream discoveries or features.

## Role in K2-OpenHost

This fork remains a technical source/reference while developing **[MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost)**. It is not the runtime CM5 repository.

Current OpenHost split:

- **[MzTechnology97/kalico-k2pro](https://github.com/MzTechnology97/kalico-k2pro)**, branch `k2-pro-openhost` — integrated external-host Kalico runtime;
- **[MzTechnology97/k2-pro-custom-firmware](https://github.com/MzTechnology97/k2-pro-custom-firmware)**, branch `k2-openhost` — versioned K2/Jacobean extra and compatibility history;
- **[MzTechnology97/cartographer3d-plugin-k2openhost](https://github.com/MzTechnology97/cartographer3d-plugin-k2openhost)** — Cartographer K2/OpenHost integration based on upstream Cartographer plus Jacob's K2 port;
- **this repository** — reference for printer-side K2 improvements, bootstrap patterns, Cartographer history, macros and service integration ideas.

## Current architecture

```text
K2 Pro T113
  -> display/touch + hardware bridge
  -> USB gadget transport
       |
       +-- ttyUSB0 -> Main MCU
       +-- ttyUSB1 -> Nozzle MCU
       `-- ttyUSB2 -> RS-485 / CFS / closed-loop

Raspberry Pi CM5 / external Linux host
  -> kalico-k2pro:k2-pro-openhost
  -> Moonraker
  -> Mainsail
  -> Cartographer direct USB
```

The project no longer targets Cartographer as a fourth multiplexed T113 gadget channel. The MUX/DEMUX experiment carried live Cartographer data but added avoidable reset/re-enumeration complexity. Direct USB on the CM5 is now the preferred topology.

## K2 Plus references in this repository

Many inherited feature READMEs, installer instructions and historical notes still say **K2 Plus**. Those references are intentionally retained where they describe the original upstream target or installation flow.

They should **not** be interpreted as a claim that every K2 Plus value or procedure applies unchanged to K2 Pro. OpenHost uses actual K2 Pro hardware validation and records untested assumptions explicitly.

For current K2 Pro/OpenHost procedures and test status, use the K2-OpenHost repository rather than the legacy printer-side install instructions in this fork.

## What remains useful here

This repository remains valuable for:

- Cartographer integration history and bootstrapping ideas;
- K2 printer-side improvement patterns;
- Moonraker/Fluidd integration references;
- macros and calibration approaches;
- stock-system observations;
- upstream feature history from jamincollins and Jacob10383.

The current Cartographer plugin itself is maintained separately in `cartographer3d-plugin-k2openhost` so newer upstream plugin behavior can be integrated without treating this historical bootstrap repository as the runtime package.

## Current OpenHost milestone — 2026-10-01

The real K2 Pro has now validated from the external CM5/Kalico stack:

- three dedicated T113 gadget serial channels;
- Main + Nozzle MCU simultaneous communication;
- RS-485 closed-loop motor control;
- normal CoreXY motion;
- X/Y sensorless/stall homing;
- correct Z direction;
- complete homing with the stock PRTouch path;
- bed/nozzle/chamber heaters and PID tuning;
- emergency heater shutdown;
- successful Klippain-ShakeTune resonance test;
- protected CFS observation mode;
- Cartographer plugin loading/streaming through the earlier experimental bridge, with final direct-USB validation still pending.

See [K2-OPENHOST.md](K2-OPENHOST.md) and the canonical K2-OpenHost repository for the detailed chronology.

## Original upstream documentation

The feature documentation under `features/`, `bed_leveling/`, and the existing scripts is preserved from the upstream lineage. For the most current original project documentation, consult:

- [Jacob10383/k2-improvements](https://github.com/Jacob10383/k2-improvements)
- [jamincollins/k2-improvements](https://github.com/jamincollins/k2-improvements)

## Additional upstream projects credited by the original work

The original project also builds on or integrates work from:

- **Guilouz**
- **stranula**
- **juliosueiras**
- **Moonraker / Arksine**
- **Klipper3d**
- **Fluidd**
- **Entware**
- **Obico**
- **SimplyPrint**
- **Cartographer3D** and contributors

Their original references remain present throughout the inherited feature documentation.

## Status

This fork is a reference component of an experimental project. It is not the canonical installation guide for K2-OpenHost and should not be treated as a drop-in CM5/OpenHost installer.