# Wireless+

Allow devices to report transponders to the Access Control Server for real-time access decisions.

---

## Overview

Wireless+ is a revolutionary feature that enables devices to report a transponder presentation to the Access Control Server, which then makes the access decision in real-time. This provides centralized control and enables dynamic access policies that can change based on external factors.

**Available since:** [Version 23.10](../versions/v23.10.md) (October 2023)

---

## How to Use

### Prerequisites

- DOMController with API v23 or later
- Compatible devices with Wireless+ support
- Stable network connectivity between devices and Access Control Server

### Configuration Steps

1. **Enable Wireless+ on the System**
   
   Configure the global Wireless+ parameter:
   
   ```bash
   POST /api/global-conf
   {
     "wireless_plus_enabled": true,
     "wireless_plus_timeout": 5000  // milliseconds
   }
   ```

2. **Configure Device for Wireless+**
   
   Enable Wireless+ mode on specific devices:
   
   ```bash
   POST /api/devices/{device_id}/wireless-plus
   {
     "enabled": true,
     "fallback_mode": "deny"  // or "allow" if server unreachable
   }
   ```

3. **Implement Server-Side Decision Logic**
   
   Your Access Control Server must implement the decision endpoint:
   
   ```bash
   POST /api/wireless-plus/decision
   {
     "device_id": "device_123",
     "transponder_id": "transponder_456",
     "timestamp": "2025-02-18T10:30:00Z"
   }
   
   Response:
   {
     "access_granted": true,
     "reason": "Valid user during business hours"
   }
   ```

4. **Monitor Wireless+ Events**
   
   Subscribe to Wireless+ events via WebSocket:
   
   ```javascript
   ws://domcontroller/api/wireless-plus/events
   ```

### Use Cases

- **Time-based policies**: Grant access only during specific hours, even if credentials are valid
- **Temporary access**: Revoke access instantly without reprogramming devices
- **Occupancy limits**: Deny access when a zone is at capacity
- **Emergency lockdown**: Override all access instantly from a central server

## Updates

### [23.10](../versions/v23.10.md) — October 2023
**Initial Release**

- Introduced Wireless+ feature
- Devices can report transponder to Access Control Server
- Server can grant or deny access in real-time
- Configurable timeout and fallback behavior

---

<!-- ## Performance Considerations

**Network Dependency**: Wireless+ requires stable network connectivity. Configure appropriate fallback modes for offline scenarios.

**Latency**: Access decisions typically take 100-500ms depending on network conditions. Configure timeout values accordingly.

**Battery Impact**: Online devices using Wireless+ may experience slightly reduced battery life due to increased communication.

---

## Related Features

- [WebSocket Connection Limit](../websocket-limit/) — Manage WebSocket connections for Wireless+ events
- [Fast Online Synchronization](../fast-online-sync/) — Optimize network communication
- [Certificate Chain Support](../certificate-chain-support/) — Secure server communication

---

## Troubleshooting

**Access denied despite valid credential?**
- Check server-side decision logic
- Verify network connectivity
- Review WebSocket event logs

**High latency on access decisions?**
- Increase `wireless_plus_timeout` value
- Optimize server-side decision endpoint
- Check network bandwidth

**Devices falling back to offline mode?**
- Verify Access Control Server availability
- Check firewall rules for WebSocket connections
- Review fallback mode configuration -->
