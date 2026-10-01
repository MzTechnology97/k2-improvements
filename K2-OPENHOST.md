# k2-improvements in the K2-OpenHost project

Updated: **2026-10-01**.

## Why this fork is retained

`k2-improvements` contains public K2 work that remains useful as a technical reference while K2-OpenHost is developed. The current OpenHost architecture does not install the original improvement stack unchanged; instead, relevant ideas and validated components are reused while the main Kalico workload runs on a CM5/external host.

## Upstream authorship

This fork preserves the upstream chain:

```text
jamincollins/k2-improvements
        |
        v
Jacob10383/k2-improvements
        |
        v
MzTechnology97/k2-improvements
```

The original feature code, installers and documentation remain credited to those upstream projects and their contributors.

## Current OpenHost repository split

### MzTechnology97/K2-OpenHost

Canonical architecture, hardware-test evidence, safety boundaries and roadmap.

### MzTechnology97/kalico-k2pro

Fork of `Jacob10383/kalico`. Branch `k2-pro-openhost` is the current integrated CM5 Kalico runtime.

### MzTechnology97/k2-pro-custom-firmware

Fork of `Jacob10383/k2-plus-custom-firmware`. Branch `k2-openhost` keeps the Jacobean K2 extra history and hardware-validated K2 Pro/OpenHost compatibility patches.

### MzTechnology97/cartographer3d-plugin-k2openhost

Current Cartographer plugin integration. It combines upstream Cartographer behavior with Jacob's K2 port and OpenHost/Kalico compatibility. It is the runtime Cartographer package used for ongoing CM5 work.

### This repository

Reference source for printer-side K2 improvements, Cartographer bootstrap/integration history, macros, UI/service ideas and other upstream K2 work.

## Current target transport

```text
T113 ttyS2 -> ttyGS0 -> CM5 /dev/ttyUSB0  (Main MCU)
T113 ttyS3 -> ttyGS1 -> CM5 /dev/ttyUSB1  (Nozzle MCU)
T113 ttyS5 -> ttyGS2 -> CM5 /dev/ttyUSB2  (RS-485/CFS/closed-loop)
Cartographer USB -------------------------> CM5 USB host directly
```

An experimental Cartographer T113 MUX/DEMUX path successfully moved live Cartographer MCU traffic, but it is not retained as the final design because direct USB handles Cartographer reset/re-enumeration more naturally and keeps the RS-485 channel dedicated.

## K2 Plus vs K2 Pro

The upstream project history contains K2 Plus-specific wording and assumptions. Those references are retained where they describe original upstream behavior. K2-OpenHost does not assume that K2 Plus dimensions, pin mapping, service coordinates or protocol behavior automatically apply to K2 Pro.

The K2 Pro project uses real hardware validation and known-good K2 Pro configuration values.

## Current validated OpenHost milestone

The project has now validated on the real K2 Pro:

- three USB gadget serial channels through the T113;
- simultaneous Main + Nozzle MCU Kalico sessions from the external host;
- native AArch64 Kalico host runtime;
- RS-485/closed-loop traffic;
- normal CoreXY motion;
- X/Y sensorless/stall homing;
- correct Z direction;
- complete homing with the stock PRTouch implementation;
- bed/nozzle/chamber heater control and PID tuning;
- emergency shutdown of active heater loads;
- Klippain-ShakeTune resonance measurement;
- CFS discovery/address/read traffic;
- real Jacobean `Box()` operation in protected observation mode;
- K2 Pro 4-byte `BOX_STATE` compatibility and mutation guard;
- Cartographer plugin import/streaming through the earlier experimental bridge.

The next Cartographer milestone is direct USB on the CM5, followed by controlled standalone probing/mesh and only then optional mixed PRTouch + Cartographer validation.

## What should be reused from this fork

Reuse upstream material selectively and keep its attribution. For current runtime components, prefer the dedicated repositories listed above rather than copying historical bootstrap files blindly into the CM5 environment.

In particular, the current Cartographer plugin and `register_as_probe` behavior belong in `cartographer3d-plugin-k2openhost`; the integrated Kalico runtime belongs in `kalico-k2pro:k2-pro-openhost`.

See `MzTechnology97/K2-OpenHost` for the detailed chronology and current roadmap.