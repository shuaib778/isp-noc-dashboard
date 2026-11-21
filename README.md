# 📊 ISP NOC Dashboard — Rx Power Reports & Reseller Portal

> 🟢 **Production System** | Drik ICT Ltd. — Multi-site ISP Operations

A full-stack ISP operations dashboard supporting NOC engineers, resellers, and management with automated optical power reporting and customer management across multiple POP sites.

---

## ✨ Features

### 📶 Automated ONU Rx Power Reporting
- Connects to MikroTik gateway via **API-SSL (encrypted, Port 8729)**
- Polls BDCOM OLTs via Telnet/SSH to collect per-ONU Rx Power readings
- Generates **color-coded Excel reports** with Low/Critical Rx Power classification
- Covers multi-site POP locations: **Magura · Shewrapara · Gaibandha · Kishoreganj**

### 👥 Reseller Management Portal
- Secure login with role-based access per reseller account
- Customer list, service status, bandwidth package tracking
- Invoice generation and CSV/Excel export

### ⚙️ Admin Control Panel
- OLT device management and registration
- User provisioning and permission management
- MikroTik PPPoE session cross-reference with OLT subscriber data
- Full service log and audit trail

---

## 📶 Rx Power Reference Guide

| Signal Level (dBm) | Meaning | Action |
|---|---|---|
| -8 to -24 dBm | ✅ Normal — good signal | No action needed |
| -24 to -27 dBm | ⚠️ Weak — monitor closely | Schedule inspection |
| Below -27 dBm | ❌ Critical — internet at risk | Immediate field response |

---

## 🏗️ Architecture

```
MikroTik Gateway (API-SSL Port 8729)
        ↓
Python Script
        ↓ Telnet/SSH
BDCOM OLT Device → Raw Rx Power Data
        ↓
Excel Report (color-coded, threshold-based)
        ↓
Web Dashboard (Flask) — Reseller & Admin Portal
        ↓
SQLite Database
```

**Stack:** Python · Flask · Netmiko · MikroTik RouterOS API · openpyxl · SQLite · HTML/JS

---

## 💼 Business Impact

- Eliminated daily manual CLI Rx Power checks for NOC engineers
- Automated threshold-based reporting helps field teams prioritize site visits
- Reseller portal reduced direct support calls to NOC by centralizing customer data

---

*Built and deployed by Mohammad Shuaib Hassan — Network Support Engineer, Drik ICT Ltd.*
