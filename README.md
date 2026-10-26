<div align="center">

<a href="https://1sc.dev"><img src=".github/assets/1sc-logo.svg" alt="1sc" width="96" height="96"></a>

# 1sc-5gcore

**A 5G Standalone core written in Rust. Open source, fast, and small enough to run on a laptop.**

The open-source version of the core that runs on [**1sc.dev**](https://1sc.dev).

[![License: AGPL-3.0](https://img.shields.io/badge/license-AGPL--3.0-6e5b93?style=flat-square)](LICENSE)
[![Built with Rust](https://img.shields.io/badge/built%20with-Rust-050505?style=flat-square&logo=rust)](https://www.rust-lang.org)
[![5G SA](https://img.shields.io/badge/3GPP-5G%20SA-00e599?style=flat-square)](#whats-inside)
[![Status: open beta](https://img.shields.io/badge/status-open%20beta-f5c451?style=flat-square)](#contributing)
[![CLA](https://img.shields.io/badge/contributions-CLA%20required-493d62?style=flat-square)](CONTRIBUTING.md)

[**Deploy in one click →**](https://1sc.dev) &nbsp;·&nbsp; [Docs](https://1sc.dev) &nbsp;·&nbsp; [Contributing](CONTRIBUTING.md)

</div>

---

## Why 1sc

Most open-source 5G cores are written in C, need MongoDB, and take a config file for every network function before you see a single attach. 1sc is built from scratch in memory-safe Rust and comes up with **one command**.

<table>
<tr>
<td width="33%" valign="top">

### ⚡ Fast
Up to **1.8×** the TCP downlink throughput of Open5GS on the same hardware.

</td>
<td width="33%" valign="top">

### 🪶 Light
About **33 MB** of memory for the whole core, roughly **13× less** than Open5GS.

</td>
<td width="33%" valign="top">

### 🦀 Safe
Pure Rust. No memory-safety bugs in the code that handles every packet.

</td>
</tr>
</table>

### Benchmarks

Measured 2026-10-11 with [UERANSIM](https://github.com/aligungr/UERANSIM) on the same host. The test harness runs on [1sc.dev](https://1sc.dev).

| CPUs | 1sc downlink | Open5GS downlink | Core memory (1sc / Open5GS) | p99 RTT (1sc / Open5GS) |
|:---:|---:|---:|:---:|:---:|
| 1 | **2,239 Mbps** | 1,692 Mbps | **33 MB** / 444 MB | **3.3** / 4.1 ms |
| 2 | **3,017 Mbps** | 1,739 Mbps | **33 MB** / 444 MB | **3.3** / 3.7 ms |
| 8 | **3,200 Mbps** | 1,733 Mbps | **34 MB** / 445 MB | **3.3** / 3.6 ms |

## What's inside

Standard 3GPP network functions, each one a separate module you can swap or reconfigure.

| Area | Network functions |
|---|---|
| Access & mobility | **AMF** |
| Sessions & user plane | **SMF** · **UPF** |
| Identity & auth | **AUSF** · **UDM** · **UDR** |
| Policy & slicing | **PCF** · **NSSF** · **BSF** |
| Service layer | **NRF** · **SCP** · **SEPP** |

<!-- TODO: add the one-command quickstart here when the first code drop lands. -->

---

<div align="center">

## Want it running in production? Skip the setup.

**[1sc.dev](https://1sc.dev)** gives you a dedicated 5G core on AWS in minutes, with one API call or one click.

</div>

| | **1sc-5gcore** (this repo) | **[1sc.dev](https://1sc.dev)** |
|---|:---:|:---:|
| Rust 5G SA core | ✅ | ✅ |
| Runs on your own hardware | ✅ | — |
| Dedicated core on AWS, deployed for you | — | ✅ |
| N2/N3 endpoints + hosted attach verification | — | ✅ |
| **CoreCI**: a real UE attach test on every commit | — | ✅ |
| Live monitoring: throughput, latency, packet loss, alerts | — | ✅ |
| Load testing with up to 512 simulated devices | — | ✅ |
| Billing, location, and other operator NFs (CHF, LMF, GMLC, 5G-EIR…) | — | ✅ |
| Run Open5GS or free5GC from the same dashboard | — | ✅ |
| API, CLI, and an MCP server for AI agents | — | ✅ |

<div align="center">

[**Deploy a 5G core in one click →**](https://1sc.dev)

</div>

---

## Contributing

PRs are welcome. Before we can merge your first one, you need to sign a CLA, either the [individual](legal/cla/1sc-icla.pdf) or the [corporate](legal/cla/1sc-cla-corporate.pdf) version. It takes about two minutes. See **[CONTRIBUTING.md](CONTRIBUTING.md)**.

## License

[AGPL-3.0](LICENSE). Need to ship 1sc in a product without AGPL obligations? Commercial licenses are available. Email [js@l9.fyi](mailto:js@l9.fyi).

<div align="center">
<sub>Built by <a href="https://l9.fyi">L9 Technologies</a> · <a href="https://1sc.dev">1sc.dev</a></sub>
</div>
