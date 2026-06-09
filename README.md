# 🌐 Interesting & Awesome Operating Systems  
*A comprehensive, structured, deeply‑researched guide to the most fascinating open‑source operating systems — including the experimental **MyOS2026**.*

---

## 📑 Table of Contents
- [Introduction](#introduction)  
- [Why This List Exists](#why-this-list-exists)  
- [Categories of Interesting Operating Systems](#categories-of-interesting-operating-systems)  
- [Master Comparison Table](#master-comparison-table)  
- [Detailed Category Breakdowns](#detailed-category-breakdowns)  
  - [1. Research & Experimental OSes](#1-research--experimental-oses)  
  - [2. Security & Privacy OSes](#2-security--privacy-oses)  
  - [3. Microkernel & Modular OSes](#3-microkernel--modular-oses)  
  - [4. Retro & Hobbyist OSes](#4-retro--hobbyist-oses)  
  - [5. Unique Linux Distributions](#5-unique-linux-distributions)  
  - [6. Cloud & Immutable OSes](#6-cloud--immutable-oses)  
  - [7. Mobile & Embedded OSes](#7-mobile--embedded-oses)  
- [How to run locally](#how-to-run-locally)  
- [Contributing](#contributing)  
- [License](#license)

---

## Introduction
Operating systems are among the most complex and creative artifacts humans build. Beyond mainstream OSes lies a vast universe of experimental, retro, academic, security‑focused, and hobbyist systems — each with its own philosophy and architecture.

This document is a **comprehensive, structured, human‑readable guide** to the most interesting open‑source OSes, including the custom experimental OS **MyOS2026**.

---

## Why This List Exists
This repository aims to:

- Help OS enthusiasts explore unconventional systems  
- Provide OS‑dev learners with inspiration and reference material  
- Preserve knowledge of rare and historical OSes  
- Compare architectures, kernel models, and design philosophies  
- Serve researchers, educators, and hobbyists with a single curated resource

---

## Categories of Interesting Operating Systems
This README covers OSes across these categories:

1. **Research & Experimental OSes**  
2. **Security & Privacy OSes**  
3. **Microkernel & Modular OSes**  
4. **Retro & Hobbyist OSes**  
5. **Unique Linux Distributions**  
6. **Cloud & Immutable OSes**  
7. **Mobile & Embedded OSes**

---

## Master Comparison Table

Below is a consolidated, README‑ready table comparing notable open‑source OSes by architecture, kernel type, purpose, uniqueness, and a short **hint** for getting started. Each OS name links to its official site or canonical repo/docs for quick access.

| **OS Name** | **Arch / Language** | **Kernel Type** | **Purpose & Uniqueness** | **Hint** |
|-------------|---------------------|-----------------|--------------------------|----------|
| **[MyOS2026](#myos2026)** | x86_64 / Rust, C | Modular Monolithic | Experimental OS‑dev; SPEC‑kit driven; RustyBox userland | **Hint:** Clone repo; `cargo build` + `make`; run in QEMU |
| **[Plan 9](https://9p.io/plan9/)** | x86, ARM / C | Microkernel‑like | Research; everything‑is‑a‑file, distributed primitives | **Hint:** Build with `mk` toolchain; run in emulator or on hardware |
| **[Inferno](http://www.vitanuova.com/inferno/)** | x86, ARM, MIPS / Limbo, C | Dis VM | Distributed systems; Limbo + Styx protocol | **Hint:** Use Dis VM packages; build Limbo apps; run hosted Inferno |
| **[Redox OS](https://www.redox-os.org/)** | x86_64, ARM / Rust | Microkernel | Secure modern OS; memory safety, RedoxFS | **Hint:** `cargo build` workspace; boot via QEMU or write image to USB |
| **[SerenityOS](https://github.com/SerenityOS/serenity)** | x86_64 / C++ | Monolithic | Desktop hobbyist; retro UI with modern tooling | **Hint:** Follow `Meta/makeall.sh`; run via `./run` |
| **[ToaruOS](https://github.com/klange/toaruos)** | x86 / C | Monolithic | Hobbyist from‑scratch OS with simple GUI | **Hint:** `make` in repo; test in QEMU |
| **[Fuchsia](https://fuchsia.dev/)** | ARM, x86 / C, C++, Rust | Microkernel (Zircon) | Research/platform; capability‑based Zircon kernel | **Hint:** Use `fx` toolchain per upstream docs; `fx qemu` |
| **[Genode](https://genode.org/)** | x86, ARM / C++ | Microkernel framework | Componentized OS framework for secure systems | **Hint:** Use Genode build system; pick a base microkernel and build image |
| **[TempleOS](https://templeos.org/)** | x86_64 / HolyC | Monolithic | Hobbyist; single‑dev OS in ring‑0 using HolyC | **Hint:** Download image; run in emulator (Bochs/QEMU) |
| **[Visopsys](https://visopsys.org/)** | x86 / C | Monolithic | From‑scratch hobbyist OS with simple GUI | **Hint:** `make` from source; boot image in QEMU or on USB |
| **[Qubes OS](https://www.qubes-os.org/)** | x86_64 / C, Python | Xen‑based (VM) | Security; strong compartmentalization using isolated VMs | **Hint:** Use official installer ISO; check HCL before install |
| **[Tails](https://tails.boum.org/)** | x86_64 / C, Shell | Linux distro | Privacy; amnesic live system routed through Tor | **Hint:** Download live ISO; verify signature; boot from USB |
| **[Whonix](https://www.whonix.org/)** | x86_64 / Shell, Python | Linux + VMs | Privacy; Gateway + Workstation split for Tor isolation | **Hint:** Install via VM images (VirtualBox/QEMU) following docs |
| **[Subgraph OS](https://subgraph.com/)** | x86_64 / C, Python | Hardened Linux | Security‑focused distro with sandboxed apps | **Hint:** Use live image or VM image; follow hardening docs |
| **[Ironclad](https://ironclad-os.org/)** | x86_64, RISC‑V / SPARK, Ada | Monolithic (formally verified) | Security; formally verified kernel in SPARK/Ada for high‑assurance systems | **Hint:** Clone repo; install GNAT/Alire toolchain; `alr build`; boot image in QEMU |
| **[OpenBSD](https://www.openbsd.org/)** | x86, ARM, others / C | Monolithic | Security and correctness focus; proactive hardening | **Hint:** Build from source with `build.sh` or use install media |
| **[Minix 3](https://www.minix3.org/)** | x86 / C | Microkernel | Reliability/education; self‑healing microkernel | **Hint:** Clone repo; `make` and run in QEMU or on x86 hardware |
| **[GNU Hurd](https://www.gnu.org/software/hurd/)** | x86 / C | Multiserver (Mach) | Research Unix‑like on Mach microkernel | **Hint:** Use Debian Hurd images or build Hurd from source; run in QEMU |
| **[seL4](https://sel4.systems/)** | ARM, x86 / C | Microkernel | Formally verified microkernel for high assurance systems | **Hint:** Use seL4 build system; run proofs/examples in QEMU |
| **[L4 Family](https://l4re.org/)** | ARM, x86 / C | Microkernel | High‑performance microkernels for embedded systems | **Hint:** Choose L4 variant (Fiasco.OC, seL4); follow variant docs |
| **[Haiku](https://www.haiku-os.org/)** | x86_64, x86 / C, C++ | Hybrid | BeOS successor focused on responsiveness and multimedia | **Hint:** Download nightly image or build with `jam`; run in VM or on hardware |
| **[ReactOS](https://reactos.org/)** | x86, x86_64 / C, C++ | Hybrid | Open‑source Windows NT reimplementation | **Hint:** Build with ReactOS build environment; test in QEMU/VM |
| **[KolibriOS](https://www.kolibrios.org/)** | x86 / Assembly | Monolithic | Extremely small OS written mostly in assembly | **Hint:** Download floppy/ISO image; boot in QEMU or on legacy x86 |
| **[MenuetOS](https://menuetos.net/)** | x86_64 / Assembly | Monolithic | 100% assembly OS with GUI and tiny footprint | **Hint:** Download binary image; run in emulator or on bare metal |
| **[AmigaOS](https://www.amigaos.net/)** | 68k, PPC / C, Assembly | Microkernel‑like | Classic multitasking desktop OS with multimedia heritage | **Hint:** Use emulators (WinUAE) or FPGA/retro hardware images |
| **[AROS](https://aros.sourceforge.io/)** | x86, ARM / C | Microkernel‑like | Open‑source AmigaOS API compatibility implementation | **Hint:** Build with AROS scripts or use prebuilt images in emulator |
| **[RISC OS](https://www.riscos.org/)** | ARM / C, Assembly | Cooperative | ARM‑native desktop OS with long heritage | **Hint:** Use Raspberry Pi images or build from source for ARM boards |
| **[NixOS](https://nixos.org/)** | x86_64, ARM / Nix, C | Monolithic (Linux) | Declarative, reproducible system configuration | **Hint:** Install via ISO; manage system with `nixos-rebuild` and Nix expressions |
| **[Guix System](https://guix.gnu.org/)** | x86_64 / Guile Scheme, C | Monolithic (Linux) | Functional package management; FSF‑aligned distro | **Hint:** Install via installer image; manage with `guix system` commands |
| **[Alpine Linux](https://alpinelinux.org/)** | x86_64, ARM / C, Shell | Monolithic (Linux) | Minimal, security‑oriented distro using musl + BusyBox | **Hint:** Use minimal ISO or Docker image; `apk` package manager |
| **[Void Linux](https://voidlinux.org/)** | x86_64, ARM / C, Shell | Monolithic (Linux) | Lightweight distro with runit init and musl/glibc options | **Hint:** Install via image; choose musl or glibc; use `xbps` |
| **[Tiny Core](http://tinycorelinux.net/)** | x86 / C, Shell | Monolithic (Linux) | Extremely small live distro (~11 MB core) | **Hint:** Download Core ISO; boot live and extend with extensions |
| **[Flatcar Container Linux](https://www.flatcar.org/)** | x86_64 / Go, C | Monolithic (Linux) | Immutable OS for container workloads in cloud | **Hint:** Use cloud images or ISO; configure via Ignition or cloud provider |
| **[RancherOS (archived)](https://github.com/rancher/os)** | x86_64 / Go, C | Monolithic (Linux) | Container‑centric OS with Docker as primary userland | **Hint:** Use minimal image; run containers as system services |
| **[SmartOS](https://smartos.org/)** | x86_64 / C, JavaScript | Hybrid (Illumos) | Cloud virtualization with ZFS and Zones | **Hint:** Boot SmartOS image; manage zones and KVM via `imgadm`/`vmadm` |
| **[postmarketOS](https://postmarketos.org/)** | ARM / C, Shell | Monolithic (Linux) | Mobile Linux distro focused on long lifecycle for phones | **Hint:** Use `pmbootstrap` to build and flash images for supported devices |
| **[Sailfish OS](https://sailfishos.org/)** | ARM / C, C++ | Linux based | Mobile OS with gesture UI and community ports | **Hint:** Use SDK and image builder; flash to supported devices or run in emulator |
| **[Zephyr Project](https://zephyrproject.org/)** | ARM, RISC‑V, x86 / C | RTOS (microkernel style) | Small footprint RTOS for constrained embedded devices | **Hint:** Use Zephyr SDK and `west` to build and flash to dev boards |
| **[FreeRTOS](https://www.freertos.org/)** | ARM, AVR, others / C | RTOS | Widely used real‑time kernel for embedded systems | **Hint:** Use vendor SDKs or FreeRTOS kernel sources; build with toolchain for target MCU |

---

## Detailed Category Breakdowns

---

### 1. Research & Experimental OSes

#### MyOS2026
A modern experimental OS built using **SPEC‑kit**, designed for modularity, reproducibility, and OS‑dev experimentation.

**Key Characteristics**
- **Architecture:** x86_64  
- **Kernel Type:** Modular monolithic  
- **Shell:** Minimal shell with essential commands  
- **Networking:** Fully functional TCP/IP stack  
- **Userland:** RustyBox (BusyBox‑Rust)  
- **Build System:** Declarative `/speckit.specify`  
- **Boot Status:** Boots successfully with working drivers

**Uniqueness**
- SPEC‑driven OS evolution  
- Rust‑based userland components  
- Clean modular architecture for learning and experimentation

#### Other research/experimental entries
- **[Plan 9](https://9p.io/plan9/)** — distributed, everything‑is‑a‑file model  
- **[Inferno](http://www.vitanuova.com/inferno/)** — Limbo language and Styx protocol for networked resources  
- **[Redox](https://www.redox-os.org/)** — Rust microkernel research with modern tooling  
- **[Fuchsia](https://fuchsia.dev/)** — Zircon microkernel and capability model  
- **[Genode](https://genode.org/)** — framework for building componentized OSes

---

### 2. Security & Privacy OSes
- **[Ironclad](https://ironclad-os.org/)** — formally verified kernel in SPARK/Ada; correctness proven at the language and proof level  
- **[Qubes OS](https://www.qubes-os.org/)** — VM‑based isolation  
- **[Tails](https://tails.boum.org/)** — amnesic, Tor‑routed  
- **[Whonix](https://www.whonix.org/)** — gateway + workstation  
- **[Subgraph OS](https://subgraph.com/)** — sandboxed apps on a hardened Linux base  
- **[OpenBSD](https://www.openbsd.org/)** — proactive security hardening

---

### 3. Microkernel & Modular OSes
- **[Minix 3](https://www.minix3.org/)** — self‑healing microkernel for reliability  
- **[GNU Hurd](https://www.gnu.org/software/hurd/)** — multiserver architecture on Mach  
- **[seL4](https://sel4.systems/)** — formally verified microkernel for high assurance  
- **[L4 Family](https://l4re.org/)** — high‑performance microkernels for embedded systems  
- **[Fuchsia](https://fuchsia.dev/)** and **[Genode](https://genode.org/)** — modern microkernel and component frameworks

---

### 4. Retro & Hobbyist OSes
- **[Haiku](https://www.haiku-os.org/)** — BeOS successor with multimedia focus  
- **[SerenityOS](https://github.com/SerenityOS/serenity)** — retro UI with modern C++ codebase  
- **[ToaruOS](https://github.com/klange/toaruos)**, **[Visopsys](https://visopsys.org/)**, **[KolibriOS](https://www.kolibrios.org/)**, **[MenuetOS](https://menuetos.net/)**, **[TempleOS](https://templeos.org/)** — from‑scratch hobbyist systems  
- **[ReactOS](https://reactos.org/)**, **[AROS](https://aros.sourceforge.io/)**, **[AmigaOS](https://www.amigaos.net/)**, **[RISC OS](https://www.riscos.org/)** — compatibility and legacy ecosystems

---

### 5. Unique Linux Distributions
- **[NixOS](https://nixos.org/)** — declarative, reproducible system configuration  
- **[Guix System](https://guix.gnu.org/)** — functional package management and FSF alignment  
- **[Alpine Linux](https://alpinelinux.org/)** — minimal, musl + BusyBox for small images  
- **[Void Linux](https://voidlinux.org/)** — runit init, musl/glibc options  
- **[Tiny Core](http://tinycorelinux.net/)** — extremely small live distro

---

### 6. Cloud & Immutable OSes
- **[Flatcar Container Linux](https://www.flatcar.org/)** — immutable OS for container workloads  
- **[RancherOS (archived)](https://github.com/rancher/os)** — container‑centric OS with Docker userland  
- **[SmartOS](https://smartos.org/)** — Illumos‑based with ZFS and Zones for cloud virtualization

---

### 7. Mobile & Embedded OSes
- **[postmarketOS](https://postmarketos.org/)** — long lifecycle mobile Linux for phones  
- **[Sailfish OS](https://sailfishos.org/)** — gesture UI and community ports  
- **[Zephyr Project](https://zephyrproject.org/)**, **[FreeRTOS](https://www.freertos.org/)** — RTOSes for constrained devices

---

## How to run locally

Below are **concise, copy‑pasteable instructions** to build and run the OSes from the table locally. Start with the **Prerequisites**, then use the **Generic QEMU workflow**, and finally follow the **per‑OS quick run** snippets for common projects. Each snippet shows the minimal commands to build or obtain an image and boot it in QEMU or a VM.

### Prerequisites
- **Host OS**: Linux (Ubuntu/Debian recommended) or macOS; Windows via WSL2 for many builds.  
- **Common packages**: `git`, `build-essential`, `gcc`, `clang`, `nasm`, `qemu-system-x86`, `qemu-system-aarch64`, `ninja`, `cmake`, `python3`, `pkg-config`.  
- **Rust toolchain**: `rustup`, `cargo` for Rust projects.  
- **Cross toolchains**: `gcc-multilib`, `binutils-multiarch`, `aarch64-linux-gnu-gcc` when building ARM targets.  
- **Virtualization**: VirtualBox or libvirt/virt-manager for VM images; enable virtualization in BIOS.  
- **USB flashing**: `dd` or `balenaEtcher`.  
- **Embedded toolchains**: vendor SDKs, `west` and Zephyr SDK for Zephyr; MCU toolchains for FreeRTOS.

### Generic QEMU workflow
```bash
git clone <repo-url>
cd <repo-dir>

# build (examples)
cargo build --release          # Rust workspace
make -j$(nproc)                # Makefile projects
mkdir build && cd build
cmake -G Ninja .. && ninja     # CMake + Ninja

# boot image in QEMU (x86_64)
qemu-system-x86_64 -m 1024 -drive file=path/to/image.img,format=raw -serial mon:stdio -net nic -net user
```

### Per OS quick run snippets (examples)
- **MyOS2026**
```bash
git clone https://example.org/MyOS2026.git
cd MyOS2026
cargo build --workspace --release
make image
qemu-system-x86_64 -m 1024 -drive file=out/myos2026.img,format=raw -serial mon:stdio
```
- **Redox**
```bash
git clone https://github.com/redox-os/redox.git
cd redox
make all
qemu-system-x86_64 -m 2048 -drive file=target/qemu/redox.img,format=raw -serial mon:stdio
```
- **SerenityOS**
```bash
git clone https://github.com/SerenityOS/serenity.git
cd serenity/Meta
./makeall.sh
./run
```
- **Fuchsia**
Follow upstream docs; example:
```bash
git clone https://fuchsia.googlesource.com/fuchsia
# use fx toolchain per docs
fx set workstation.x64
fx build
fx qemu
```
- **Qubes / Tails / Whonix**
Download official ISO or VM images, verify signatures, and boot in a VM or on hardware.

---

## Contributing
Contributions are welcome. Please submit:

- New OS entries or corrections  
- Architecture, kernel, or language updates  
- Build/run hints, screenshots, or diagrams  
- Additional categories or historical notes

When adding entries, keep rows concise and include a short **Hint** showing how to build or run (example: `make` + QEMU command or official ISO instructions).

---

## License
This document is released under the **MIT License**. You are free to copy, modify, and distribute it.

---
