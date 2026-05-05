# 🌐 Interesting & Awesome Operating Systems  
*A comprehensive, structured, deeply‑researched guide to the most fascinating operating systems ever created — including the experimental **MyOS2026**.*

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
- [Contributing](#contributing)
- [License](#license)

---

# 🧭 Introduction
Operating systems are among the most complex and creative artifacts humans build. Beyond mainstream OSes like Windows, Linux, and macOS lies a vast universe of experimental, retro, academic, security‑focused, and hobbyist systems — each with its own philosophy and architecture.

This document is a **comprehensive, structured, human‑readable guide** to the most interesting OSes ever created, including the custom experimental OS **MyOS2026**.

---

# 🎯 Why This List Exists
This repository aims to:

- Help OS enthusiasts explore unconventional systems  
- Provide OS‑dev learners with inspiration  
- Preserve knowledge of rare and historical OSes  
- Compare architectures, kernel models, and design philosophies  
- Serve as a reference for researchers, educators, and hobbyists  

---

# 🧩 Categories of Interesting Operating Systems
This README covers OSes across these categories:

1. **Research & Experimental OSes**  
2. **Security & Privacy OSes**  
3. **Microkernel & Modular OSes**  
4. **Retro & Hobbyist OSes**  
5. **Unique Linux Distributions**  
6. **Cloud & Immutable OSes**  
7. **Mobile & Embedded OSes**

---

# 🏆 Master Comparison Table

Below is a consolidated table comparing the most interesting OSes by:

- Architecture  
- Kernel Type  
- Primary Purpose  
- Uniqueness  

---

## 📊 Comparison Table (Includes MyOS2026)

| OS Name | Architecture | Kernel Type | Purpose | Uniqueness |
|--------|--------------|-------------|---------|------------|
| **MyOS2026** | x86_64 | Modular Monolithic | Experimental OS‑dev | SPEC‑kit driven, RustyBox userland, minimal shell, TCP/IP stack |
| **Plan 9** | x86, ARM | Microkernel‑like | Research | Everything‑is‑a‑file, distributed |
| **Inferno** | x86, ARM, MIPS | Dis VM | Distributed systems | Limbo language, Styx protocol |
| **Redox OS** | x86_64 | Microkernel | Secure modern OS | Rust‑based safety |
| **SerenityOS** | x86_64 | Monolithic | Desktop OS | Retro UI + modern C++ |
| **ToaruOS** | x86 | Monolithic | Hobbyist | Entire OS from scratch |
| **Fuchsia** | ARM, x86 | Microkernel (Zircon) | Google future OS | Capability‑based |
| **Genode** | x86, ARM | Microkernel framework | Security | Componentized OS design |
| **TempleOS** | x86_64 | Monolithic | Hobbyist | HolyC language, ring‑0 |
| **Visopsys** | x86 | Monolithic | Hobbyist | Clean from‑scratch OS |
| **Qubes OS** | x86_64 | Xen hypervisor | Security | VM‑based compartmentalization |
| **Tails** | x86_64 | Linux | Privacy | Amnesic + Tor‑routed |
| **Whonix** | x86_64 | Linux + VMs | Privacy | Gateway + Workstation |
| **Subgraph OS** | x86_64 | Hardened Linux | Security | Sandboxed apps |
| **OpenBSD** | x86, ARM | Monolithic | Security | Proactive hardening |
| **Minix 3** | x86 | Microkernel | Reliability | Self‑healing OS |
| **GNU Hurd** | x86 | Microkernel (Mach) | Research | Server‑based OS |
| **seL4** | ARM, x86 | Microkernel | High assurance | Formally verified |
| **L4 Family** | ARM, x86 | Microkernel | Embedded | High performance |
| **Haiku OS** | x86_64 | Hybrid | Desktop | BeOS successor |
| **ReactOS** | x86, ARM | Hybrid | Windows clone | NT‑compatible |
| **KolibriOS** | x86 | Monolithic | Hobbyist | Written in assembly |
| **MenuetOS** | x86_64 | Monolithic | Hobbyist | 100% assembly |
| **AmigaOS** | 68k, PPC | Microkernel‑like | Desktop | Legendary multitasking |
| **AROS** | x86, ARM | Microkernel‑like | Desktop | Open‑source Amiga |
| **RISC OS** | ARM | Cooperative | Desktop | ARM‑native OS |
| **NixOS** | x86_64, ARM | Monolithic | Reproducibility | Declarative system |
| **Guix System** | x86_64 | Monolithic | FSF‑aligned | Functional package mgmt |
| **Alpine Linux** | x86_64, ARM | Monolithic | Security | musl + busybox |
| **Void Linux** | x86_64, ARM | Monolithic | Lightweight | runit init |
| **Tiny Core** | x86 | Monolithic | Minimal | 11MB distro |
| **CoreOS/Flatcar** | x86_64 | Monolithic | Cloud | Immutable OS |
| **RancherOS** | x86_64 | Monolithic | Cloud | Docker‑native |
| **SmartOS** | x86_64 | Hybrid | Cloud | ZFS + Zones |
| **postmarketOS** | ARM | Monolithic | Mobile Linux | 10‑year lifecycle |
| **Sailfish OS** | ARM | Linux | Mobile | Gesture UI |
| **Zephyr RTOS** | ARM, RISC‑V | Microkernel | Embedded | Tiny RTOS |
| **FreeRTOS** | ARM, AVR | Microkernel | Embedded | Industry standard |

---

# 🧠 Detailed Category Breakdowns

---

## 1. Research & Experimental OSes

### ⭐ MyOS2026
A modern experimental OS built using **SPEC‑kit**, designed for modularity, reproducibility, and OS‑dev experimentation.

**Key Characteristics**
- **Architecture:** x86_64  
- **Kernel Type:** Modular monolithic  
- **Shell:** Minimal shell with essential commands  
- **Networking:** Fully functional TCP/IP stack  
- **Init System:** initrd/initramfs not yet implemented  
- **Userland:** RustyBox (BusyBox‑Rust)  
- **Build System:** Declarative `/speckit.specify`  
- **Boot Status:** Boots successfully with working drivers  

**Uniqueness**
- SPEC‑driven OS evolution  
- Rust‑based userland components  
- Clean modular architecture  
- Designed for OS‑dev learning and experimentation  

---

## 2. Security & Privacy OSes
- **Qubes OS** — VM‑based isolation  
- **Tails** — amnesic, Tor‑routed  
- **Whonix** — gateway + workstation  
- **Subgraph OS** — hardened Linux  
- **OpenBSD** — proactive security  

---

## 3. Microkernel & Modular OSes
- **Minix 3**  
- **GNU Hurd**  
- **seL4**  
- **L4 Family**  
- **Fuchsia (Zircon)**  
- **Genode**  

---

## 4. Retro & Hobbyist OSes
- **KolibriOS**  
- **MenuetOS**  
- **Haiku OS**  
- **ReactOS**  
- **AmigaOS / AROS**  
- **RISC OS**  

---

## 5. Unique Linux Distributions
- **NixOS**  
- **Guix System**  
- **Alpine Linux**  
- **Void Linux**  
- **Tiny Core Linux**  

---

## 6. Cloud & Immutable OSes
- **CoreOS / Flatcar**  
- **RancherOS**  
- **SmartOS**  
- **Photon OS**  

---

## 7. Mobile & Embedded OSes
- **postmarketOS**  
- **Sailfish OS**  
- **KaiOS**  
- **Zephyr RTOS**  
- **FreeRTOS**  

---

# 🤝 Contributing
Contributions are welcome.  
Feel free to submit:

- New OS entries  
- Corrections  
- Architecture details  
- Kernel insights  
- Screenshots or diagrams  
- Additional categories  

---

# 📄 License
This document is released under the **MIT License**.  
You are free to copy, modify, and distribute it.

