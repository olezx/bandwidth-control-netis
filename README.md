📡 Internet Bandwidth Control System
### QoS Configuration Guide — Netis Routers

> A step-by-step documentation for controlling and limiting internet bandwidth per device using the built-in QoS features of **Netis** routers.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Supported Devices](#supported-devices)
- [How QoS Works](#how-qos-works)
- [QoS Setup Guide](docs/netis-qos-guide.md)
- [Troubleshooting](docs/troubleshooting.md)
- [FAQ](#faq)

---

## Overview

This project documents how to configure **Quality of Service (QoS)** on Netis routers to:

- Limit download/upload speed per device
- Prioritize specific devices (e.g. work PC over phones)
- Prevent one user from consuming all the bandwidth

No software installation needed — everything is done through the **router's web admin panel**.

---

## Supported Devices

| Model | Admin Panel URL |
|-------|----------------|
| Netis WF2409E | `http://192.168.1.1` |
| Netis WF2780 | `http://192.168.1.1` |
| Netis N6 | `http://192.168.1.1` |

> Other Netis models work similarly — check the label on your router for the exact admin URL.

---

## How QoS Works

```
Your ISP
   │
   ▼
[Netis Router]  ◄── You set rules here (max speed per device)
   │
   ├── 💻 PC          → Max 20 Mbps
   ├── 📱 Phone 1     → Max 5 Mbps
   ├── 📱 Phone 2     → Max 5 Mbps
   └── 📺 Smart TV    → Max 10 Mbps
```

QoS works by identifying each device via its **MAC address** or **IP address**, then applying upload/download limits to it.

---

## FAQ

**Q: Will this slow down my whole network?**  
A: No. QoS only limits individual devices — the total bandwidth stays the same.

**Q: What if a device reconnects and gets a new IP?**  
A: Assign a static IP via DHCP Reservation so the device always keeps the same IP.

**Q: Do I need to restart the router after applying rules?**  
A: Usually no — rules apply instantly. A restart may be required on older firmware.

---

## 📂 Documentation Files

| File | Description |
|------|-------------|
| [docs/netis-qos-guide.md](docs/netis-qos-guide.md) | Full Netis QoS setup walkthrough |
| [docs/troubleshooting.md](docs/troubleshooting.md) | Common issues and fixes |

---

## 🤝 Contributing

Found an issue or want to add support for another Netis model? Feel free to open a Pull Request or create an Issue.

---

## 📄 License

MIT License — free to use and share.
