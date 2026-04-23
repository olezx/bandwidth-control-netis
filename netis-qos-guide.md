# 🌐 Netis Router — QoS Bandwidth Control Guide

## Step 1 — Access the Admin Panel

1. Connect to your Netis router (via Wi-Fi or cable)
2. Open your browser and go to: **`http://192.168.1.1`**
3. Login with your credentials
   - Default username: `admin`
   - Default password: `admin` *(check the label on your router)*

---

## Step 2 — Find the QoS Section

Navigate to:
```
Advanced Settings → Bandwidth Control → QoS
```

> On some Netis models it may appear under **"Traffic Control"** instead.

---

## Step 3 — Enable QoS

1. Check the box **"Enable Bandwidth Control"**
2. Enter your actual internet speed:
   - **Egress Bandwidth (Upload):** e.g. `10 Mbps`
   - **Ingress Bandwidth (Download):** e.g. `100 Mbps`

> ⚠️ Use your real speeds from your ISP plan — not higher. Wrong values make QoS ineffective.

---

## Step 4 — Find the Device's IP or MAC Address

You need to identify the device you want to limit.

**Option A — From the router's connected devices list:**
```
Status → Client List (or DHCP List)
```
Note the **IP Address** and **MAC Address** of each device.

**Option B — From Windows:**
```
Win + R → cmd → ipconfig /all
```
Look for "Physical Address" (that's the MAC address).

**Option B — From Android/iPhone:**
```
Settings → Wi-Fi → tap your network → Details
```

---

## Step 5 — Add a Bandwidth Rule

In the QoS section, click **"Add"** and fill in:

| Field | What to enter |
|-------|---------------|
| IP Address | Device IP, e.g. `192.168.1.105` |
| Upload Limit | Max upload speed for this device, e.g. `2048` (KB/s) |
| Download Limit | Max download speed, e.g. `5120` (KB/s) |
| Enable | ✅ Checked |

> **Unit conversion:** 1 Mbps = 1024 KB/s
> - 5 Mbps = 5120 KB/s
> - 10 Mbps = 10240 KB/s

Click **Save**.

---

## Step 6 — Verify the Rule is Applied

Go back to the QoS rules list — your new rule should appear as **Active**.

Test it by running a speed test on the limited device at [fast.com](https://fast.com) or [speedtest.net](https://speedtest.net).

---

## Tips for Netis Routers

- 📌 **Assign static IPs** to devices you want to limit (under DHCP → Address Reservation), so their IP never changes.
- 🔄 **Rules reset on reboot** on some older Netis firmware — update to the latest firmware if this happens.
- 📋 **Label your rules** using the Description field (e.g. "Phone - Ahmed", "Smart TV").

---

## Example Setup

| Device | IP | Download Limit | Upload Limit |
|--------|----|---------------|--------------|
| Work PC | 192.168.1.100 | Unlimited | Unlimited |
| Phone 1 | 192.168.1.101 | 5 Mbps (5120 KB/s) | 2 Mbps (2048 KB/s) |
| Phone 2 | 192.168.1.102 | 5 Mbps (5120 KB/s) | 2 Mbps (2048 KB/s) |
| Smart TV | 192.168.1.103 | 10 Mbps (10240 KB/s) | 3 Mbps (3072 KB/s) |
