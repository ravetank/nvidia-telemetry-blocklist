# nvidia-telemetry-blocklist

**Hardened blocklist for NVIDIA telemetry, login, OTA, and analytics domains.**  
Optimized for use with [SimpleWall](https://www.henrypp.org/product/simplewall), hosts file blocking, and DNS-based blackholes (Unbound, Pi-hole, AdGuard, etc).  
May **break** functionality in NVIDIA apps such as **login/authentication, OTA, or account management**.

---

## 🧠 Purpose

This repo provides a pre-built set of rules to silence NVIDIA's telemetry, update, and analytics infrastructure — both IPv4 and IPv6 — across network stacks.

## ⚠️ Warning

Blocking domains like `accounts.nvgs.nvidia.com` may prevent:

- Logging into GeForce Experience or NVIDIA App
- Access to NVIDIA accounts via official apps

Use only if you are aware of the consequences.

---

## 📁 Contents

| File | Description |
|------|-------------|
| `NVIDIA_Telemetry_Blocklist.csv` | Full list of IPs and domains with notes |
| `NVIDIA_Telemetry_Blocklist_Domains.csv` | Extracted domains only |
| `Parsed_NVIDIA_Telemetry_Block_Rules.csv` | SimpleWall-compatible structure |
| `nvidia_telemetry_blocklist.hosts` | Hosts file for blocking at OS level |
| `nvidia_telemetry_blocklist.unbound.conf` | Unbound DNS config |
| `nvidia_telemetry_blocklist.dnsmasq.conf` | DNSMasq config for routers |
| `nvidia_telemetry_blocklist_reference.md` | Easy to read reference document |
| `README.md` | You are here |
| `LICENSE` | MIT License - do whatever you want |

---

## 🛠️ Installation

### ✅ SimpleWall

1. Open SimpleWall  
2. Import rules via: `Parsed_NVIDIA_Telemetry_Block_Rules.csv`  
3. Enable and apply them

### ✅ Hosts File

Copy the contents of `nvidia_telemetry_blocklist.hosts` into your system’s `hosts` file (`C:\Windows\System32\drivers\etc\hosts` on Windows). Requires admin privileges.

### ✅ DNS Blocking

Use one of:

- `nvidia_telemetry_blocklist.unbound.conf` — for [Unbound](https://nlnetlabs.nl/projects/unbound/about/)
- `nvidia_telemetry_blocklist.dnsmasq.conf` — for [dnsmasq](https://thekelleys.org.uk/dnsmasq/doc.html)

Or manually import `NVIDIA_Telemetry_Blocklist_Domains.csv` into your Pi-hole or AdGuard setup.

---

## 💬 Use Cases

- Kill GeForce Experience background services
- Block NVIDIA OTA updates and device tracking
- Prevent silent display/audio driver installs
- Harden low-latency systems (music production, gaming rigs)

---

 ** MAY BREAK NVIDA APPS **

login.nvgs.nvidia.cn
118.193.97.200 ; 118.193.97.209 ; 118.193.97.211 ; 118.193.97.221 ;

accounts.nvgs.nvidia.cn
44.213.48.29 ; 52.205.95.17 ; 52.7.55.151 ; 71.131.239.187 ; 140.179.137.34

accounts.nvgs.nvidia.com
2400:7fc0:8e92:13ca:4625:ecf7:33a:1ad0
2400:7fc0:8e92:13cb:2c12:ea80:7940:504c
2600:1f18:1a58:e202:204b:43c2:3c4e:4f34
2600:1f18:1a58:e203:4b65:ae82:ba57:bb95
2600:1f18:1a58:e204:5f31:b4bd:524e:d239

login.nvgs.nvidia.com
3.161.213.54
3.161.213.7
3.161.213.76
3.161.213.97

 **PURE TELEMETRY **

gfwsl.geforce.com
2001:4c0:1:2006::8eb0:d0b0
2001:4c0:1:2006::8eb0:d09b
142.176.208.155
142.176.208.176

nvidia.telemetry.internet.microsoft.com
gfe.nvidia.com
72.25.64.38
72.25.64.8

gfe.geforce.com
nvidia.com.edgesuite.net
telemetry.nvidia.com

telemetry.gfe.nvidia.com
72.25.64.16
72.25.64.46

services.gfe.nvidia.com
142.176.208.162
142.176.208.144

events.gfe.nvidia.com
72.25.64.32

img.nvidiagrid.net
2600:140a:a000::172b:a121
2600:140a:a000::172b:a118
23.53.4.17
23.53.4.32

images.nvidiagrid.net
2600:140a:a000::172b:a118
2600:140a:a000::172b:a121
23.53.4.32
23.53.4.17

images.nvidia.com
23.53.4.11
23.53.4.17

ls.dtrace.nvidia.com
ota.nvidia.com

ota-downloads.nvidia.com
142.176.208.178
142.176.208.137

rds-assets.nvidia.com
2600:140a:a000::172b:a120
2600:140a:a000::172b:a10a
23.53.4.17
23.53.4.11

assets.nvidiagrid.net
2600:140a:a000::172b:a121
2600:140a:a000::172b:a118
23.53.4.17
23.53.4.32

nvidia.tt.omtrdc.net
63.140.39.123
63.140.38.77
63.140.38.248
63.140.39.78
63.140.39.68
63.140.39.244
63.140.38.107
63.140.38.204
63.140.39.210
63.140.38.130

api.commune.ly
52.26.80.135
44.239.29.13
34.216.188.13

---

## 👑 Maintainer

**https://github.com/ravetank**

---

## 📜 License

MIT — *do what you want, no warranty*.
