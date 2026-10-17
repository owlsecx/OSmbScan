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

SMB / NetBIOS exposure scanner — discover, negotiate, signing, null-session hints

---

## ✨ Features

- Host / CIDR discovery (threaded TCP connect on 139 / 445 with per-socket timeout, /24 guard)
- Pure-stdlib SMB1 negotiate probe — hand-built SMB_COM_NEGOTIATE packet, dialect-index parser, SMBv1-enabled detection (EternalBlue / MS17-010 hint only, no exploitation)
- Pure-stdlib SMB2 negotiate probe — struct-built NEGOTIATE request, response parser for dialect, security mode (signing required / enabled), server GUID, max SMB version, capabilities
- NetBIOS node-status query (UDP 137) — name list, workgroup / domain, unique vs group names, adapter MAC address parsing
- Anonymous / null-session hint — NEGOTIATE + SESSION_SETUP (anonymous) handshake, safe tree connect to IPC$ when trivially allowed, clearly labelled authorized-use-only, no brute force
- Vulnerability hints — SMBv1 enabled, signing not required (NTLM relay), guest / null session, each with severity + remediation
- Best-effort safe share enumeration note (IPC$ reachable vs auth required); no file download
- Per-host report — ports, dialects, signing, SMBv1, NetBIOS names, findings (severity + fix)
- Export TXT / CSV / JSON with save-location chooser and clipboard copy
- Interactive menu + full CLI (--target, --ports, --netbios, --null-session, --timeout, --threads, --json, -o, --fail-on, --version)
- Persistent settings in ~/OSmbScan/config.json

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSmbScan
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
