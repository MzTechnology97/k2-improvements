# k2-improvements in the K2-OpenHost project

## Why this fork is retained

`k2-improvements` contains a large amount of public K2 work that remains useful as a technical reference while K2-OpenHost is developed. The current OpenHost architecture does not simply install the original improvement stack unchanged; instead, relevant ideas and validated components are reused while the main Kalico workload moves to a CM5/external host.

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

Fork of `Jacob10383/kalico`. Branch `k2-pro-openhost` is the current integrated CM5 Kalico target.

### MzTechnology97/k2-pro-custom-firmware

Fork of `Jacob10383/k2-plus-custom-firmware`. Branch `k2-openhost` keeps the Jacobean K2 extras and the hardware-validated K2 Pro/OpenHost compatibility patches.

### This repository

Reference source for printer-side K2 improvements, Cartographer integration history, macros, UI/service ideas and other upstream K2 work.

## K2 Plus vs K2 Pro

The upstream project history contains K2 Plus-specific wording and assumptions. Those references are retained where they describe original upstream behavior. K2-OpenHost does not assume that K2 Plus dimensions, pin mapping, service coordinates or protocol behavior automatically apply to K2 Pro.

The K2 Pro project uses actual hardware validation and, later, the known-good `.cfg` files from the working K2 Pro.

## Current validated OpenHost milestone

The project has already validated:

- three USB gadget serial channels through the T113;
- simultaneous Main + Nozzle MCU Kalico sessions from the external host;
- RS-485/closed-loop traffic;
- CFS discovery/address/read traffic;
- real Jacobean `Box()` operation in protected observation mode;
- 35 TX / 35 RX with zero transport errors and a deliberate mutation blocked before TX.

See `MzTechnology97/K2-OpenHost` for the detailed chronology and current roadmap.