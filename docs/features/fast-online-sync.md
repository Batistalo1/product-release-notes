# Fast Online Synchronization

Dramatically reduce synchronization time of online devices from 15 minutes to 10 seconds.

---

## Overview

Fast Online Synchronization is a performance optimization feature that reduces the synchronization time of online devices from the traditional 15 minutes to just 10 seconds. This enables near-instant propagation of configuration changes and access rights updates to connected devices.

**Available since:** [Version 23.03](../versions/v23.03.md) (March 2023)

---

## How to Use

### Prerequisites

- DOMController with API v23 or later
- Online devices (RFNM, ACM with network connectivity)
- Optimized Access Control Software implementation recommended

### Configuration Steps

1. **Enable Fast Online Synchronization**
   
   Configure the global parameter via API:
   
   ```bash
   POST /api/global-conf
   {
     "fast_online_sync": true
   }
   ```

2. **Verify Configuration**
   
   Check the current sync interval:
   
   ```bash
   GET /api/global-conf
   
   Response:
   {
     "fast_online_sync": true,
     "sync_interval_seconds": 10  // Changed from 900
   }
   ```

3. **Monitor Synchronization**
   
   Track sync events via logs or API:
   
   ```bash
   GET /api/devices/{device_id}/last-sync
   
   Response:
   {
     "last_sync_timestamp": "2025-02-18T10:30:05Z",
     "sync_duration_ms": 340,
     "items_synchronized": 15
   }
   ```

---

## Updates

### [23.03](../versions/v23.03.md) — March 2023
**Initial Release**

- Introduced Fast Online Synchronization parameter in global configuration
- Sync time reduced from 15 minutes to 10 seconds
- Configurable per system

### [24.01](../versions/v24.01.md) — January 2024
**Smart Synchronization**

- Devices will no longer be synchronized if no value changes during an API call
- Better battery management with intelligent sync detection
- Reduces unnecessary network traffic

### [24.10](../versions/v24.10.md) — October 2024
**Auto-Coupling Integration**

- Fast sync applies to auto-coupled devices
- Improved parent selection logic with 5-minute delay for low BLE quality
- Enhanced sync stability during auto-coupling process

---

<!-- ## Performance Tuning

### Recommended Settings

For **small deployments** (< 50 devices):
```json
{
  "fast_online_sync": true,
  "sync_interval_seconds": 10
}
```

For **medium deployments** (50-200 devices):
```json
{
  "fast_online_sync": true,
  "sync_interval_seconds": 15
}
```

For **large deployments** (> 200 devices):
```json
{
  "fast_online_sync": true,
  "sync_interval_seconds": 30
}
```

### Monitoring Battery Impact

Track device battery levels over time:

```bash
GET /api/devices/battery-status

Response:
{
  "devices": [
    {
      "device_id": "device_123",
      "battery_level": 87,
      "estimated_lifetime_days": 245,
      "fast_sync_enabled": true
    }
  ]
}
```

---

## Related Features

- [Schedule Isolation](../schedule-isolation/) — Optimize sync by only updating affected devices
- [Auto-Coupling](../auto-coupling/) — Automatic device discovery with fast sync
- [Per-Device Schedules](../per-device-schedules/) — Granular sync control per device

---

## Troubleshooting

**Devices not syncing faster?**
- Verify `fast_online_sync` is enabled in global config
- Check device firmware version (must support fast sync)
- Review network connectivity

**Battery draining faster than expected?**
- Consider increasing sync interval (15-30 seconds)
- Implement smart sync logic in Access Control Software
- Monitor battery levels regularly

**High server load?**
- Stagger sync requests across devices
- Optimize database queries in Access Control Software
- Consider load balancing for large deployments -->
