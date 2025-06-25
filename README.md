# nvidia-telemetry-blocklist
Hardened blocklist for NVIDIA telemetry, login, OTA, and analytics domains. Optimized for use with SimpleWall, hosts files, and DNS sinkholes. May break functionality in NVIDIA apps - use at your own risk.

# NVIDIA Telemetry Blocklist

This repo provides a hardened list of domains and IPs used by NVIDIA for telemetry, login/auth, content delivery, and OTA updates. It is designed for power users who prefer a fully controlled and silent system environment.

## ⚠️ Warning
Blocking certain login domains (e.g., `accounts.nvgs.nvidia.com`) will prevent authentication in NVIDIA software like GeForce Experience or the new NVIDIA App.

## 🧱 Contents

- `simplewall/`: Importable rule set for SimpleWall
- `hosts/`: Hosts file for system-level blocking
- `dns/`: Plaintext domain list for use with Unbound, AdGuard, Pi-hole, etc.

## ✅ Use Cases

- Harden Windows against telemetry leaks
- Disable GeForce Experience background tracking
- Prevent silent driver updates via OTA
- Optimize real-time performance (esp. for audio/production)

## 📥 Installation

### SimpleWall:
1. Open SimpleWall
2. Import `simplewall/nvidia_telemetry_block.ruleset`
3. Apply rules and restart networking

### Hosts:
Copy contents of `hosts/nvidia_telemetry_blocklist.hosts` into your system hosts file.

### DNS (e.g., Unbound):
Use `dns/nvidia_telemetry_blocklist.domains` in your local block list zone.

## 🛠 Maintained by
https://github.com/ravetank

## 🆓 License
MIT – do what you want, no warranty.
