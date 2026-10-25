# 🦉 OSmbScan

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OReconnaissance-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSmbScan** — SMB / NetBIOS Exposure Scanner

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSmbScan is an SMB/NetBIOS exposure scanner that discovers Windows file-sharing services and reports their security posture using pure-stdlib probes. It performs host/CIDR discovery on 139/445, hand-built SMB1 and SMB2 negotiate probes, NetBIOS node-status queries and safe anonymous/null-session hints — with no brute force and no exploitation. Each host gets a report of dialects, signing, SMBv1 status and findings, exportable as TXT, CSV or JSON.

---

## ✨ Features


- Threaded host / CIDR discovery on TCP 139 and 445 with per-socket timeouts and a /24 guard
- Pure-stdlib SMB1 and SMB2 negotiate probes (dialects, signing mode, server GUID, capabilities, SMBv1/EternalBlue hint)
- NetBIOS node-status query over UDP 137 (names, workgroup/domain, adapter MAC)
- Safe anonymous / null-session hint with IPC$ reachability check — no brute force
- Vulnerability hints (SMBv1 enabled, signing not required, guest/null session) with severity and remediation
- Full CLI (--target, --ports, --netbios, --null-session, --timeout, --threads) and TXT/CSV/JSON export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSmbScan --target 192.168.1.0/24 --netbios
./OSmbScan -t 10.0.0.5 --null-session --format json -o smb.json
./OSmbScan --target 10.0.0.0/24 --threads 100 --fail-on high
./OSmbScan --selftest
./OSmbScan --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
