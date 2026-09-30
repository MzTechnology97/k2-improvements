# K2 Pro Improvements — K2-OpenHost reference fork

This repository is kept as a **K2 Pro / K2-OpenHost reference fork** in the public `k2-improvements` lineage.

## Upstream lineage and credits

The original authorship chain is intentionally preserved:

1. **[jamincollins/k2-improvements](https://github.com/jamincollins/k2-improvements)** — original project and feature work;
2. **[Jacob10383/k2-improvements](https://github.com/Jacob10383/k2-improvements)** — Jacob's fork, K2 integration work and the direct parent of this repository;
3. **MzTechnology97/k2-improvements** — local K2 Pro/OpenHost reference fork.

The original authors and contributors retain credit for their code, scripts, documentation and reverse-engineering work. This fork does not claim authorship of upstream discoveries or features.

## Role in K2-OpenHost

This fork is used as a source/reference while developing **[MzTechnology97/K2-OpenHost](https://github.com/MzTechnology97/K2-OpenHost)**.

K2-OpenHost has a different target architecture from the classic printer-side improvement stack:

```text
K2 Pro T113
  -> display/touch + hardware bridge
  -> USB gadget transport
       |
       v
Raspberry Pi CM5 / external Linux host
  -> Kalico
  -> Moonraker
  -> K2-specific extras
```

The current integrated Kalico tree is:

- **[MzTechnology97/kalico-k2pro](https://github.com/MzTechnology97/kalico-k2pro)**, branch `k2-pro-openhost`.

The versioned Jacobean K2 extra/patch source is:

- **[MzTechnology97/k2-pro-custom-firmware](https://github.com/MzTechnology97/k2-pro-custom-firmware)**, branch `k2-openhost`.

## About K2 Plus references in this repository

Many feature READMEs, installer instructions and historical notes in this fork come directly from the upstream projects and may still say **K2 Plus**. Those references are intentionally retained where they describe the original upstream target or installation flow.

They should **not** be interpreted as a claim that every K2 Plus value or procedure applies unchanged to K2 Pro. In the OpenHost project, K2 Pro behavior is either:

- verified on the real K2 Pro hardware;
- explicitly derived from public source/configuration;
- or marked as not yet tested.

For current K2 Pro/OpenHost procedures and test status, use the K2-OpenHost repository rather than the legacy printer-side install instructions in this fork.

## What remains useful here

This repository is still valuable for:

- Cartographer integration history and tooling;
- K2 printer-side improvement patterns;
- Moonraker/Fluidd integration references;
- macros and calibration approaches;
- bootstrapping and stock-system observations;
- upstream feature history from jamincollins and Jacob10383.

See [K2-OPENHOST.md](K2-OPENHOST.md) for how this repository fits into the current project.

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