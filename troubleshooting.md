# 🔧 Troubleshooting — Netis QoS Issues

---

## QoS rules are not working / speed is not limited

**Possible causes:**

1. **Wrong total bandwidth entered**  
   The total bandwidth must match your actual ISP speed. If you entered `1000 Mbps` but your plan is `100 Mbps`, the router has nothing to limit against.  
   → Fix: Re-enter your actual ISP speed in the QoS settings.

2. **Device got a new IP address**  
   If you made IP-based rules, the device may have reconnected with a different IP.  
   → Fix: Use DHCP Reservation to assign a fixed IP to the device:  
   `Advanced → DHCP → Address Reservation`

3. **QoS is not enabled globally**  
   Individual rules won't work if the main QoS toggle is OFF.  
   → Fix: Make sure "Enable Bandwidth Control" is checked at the top of the QoS page.

4. **Testing on the same network**  
   Speed tests between devices on the same LAN won't reflect the limit.  
   → Fix: Test with an external site like [fast.com](https://fast.com) or [speedtest.net](https://speedtest.net).

---

## Can't access the Netis admin panel

| Symptom | Fix |
|---------|-----|
| `192.168.1.1` not loading | Make sure you're connected to the Netis Wi-Fi or via cable |
| Page loads but login fails | Try default credentials: `admin` / `admin` |
| Forgot custom password | Hold the reset button on the router for 10 seconds to factory reset |

---

## Rules reset after router reboot

This is a known firmware bug on some older Netis models.  
→ Fix: Update to the latest firmware:  
`Advanced → System → Firmware Update`

---

## Speed is lower than the set limit

If you set `10 Mbps` but the device gets only `3 Mbps`:

- Other devices may be consuming bandwidth simultaneously
- Two conflicting rules might be applied to the same device
- Try disconnecting other devices temporarily to confirm the rule is correct

---

## Still not working?

1. Take a screenshot of your QoS settings page
2. Open an Issue in this repository
3. Include: Netis model, firmware version, and the exact rule you created
