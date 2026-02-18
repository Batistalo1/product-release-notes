# Features

Catalogue of all DOMController features, with the versions in which they are available.

---

## Access & Credentials

| Feature | Description | Versions |
|---------|-------------|----------|
| Configurable credential size | Credential size can be specified to the system with automatic padding and trimming handling | [25.04](../versions/v25.04.md) |
| Hybrid card support | Select which technology must be used for hybrid cards (global configuration) | [25.01.00](../versions/v25.01.00.md) |
| OSS Creator | Create OSS application data structure on a virgin Desfire transponder | [23.10](../versions/v23.10.md) |
| OSS dynamic validity | Set OSS dynamic validity in weeks, months or years | [25.02](../versions/v25.02.md) |
| OSS custom key numbers | Assign different key numbers when configuring OSS (out of standard) | [25.02](../versions/v25.02.md) |
| Permissions per access group | Assign permissions to access groups, each with its own opening delay | [23.10](../versions/v23.10.md) |
| Special cards | Emergency and Master Key tags on special cards | [24.04](../versions/v24.04.md) |
| OSS Intervention mode | Create OSS credentials with Intervention mode | [24.04](../versions/v24.04.md) |
| OSS toggle mode (double tap) | Transponder must be shown twice to switch to permanently open | [23.10](../versions/v23.10.md) |

---

## Doors & Devices

| Feature | Description | Versions |
|---------|-------------|----------|
| Door abstraction | Create a door without a coupled device and preconfigure it | [25.03](../versions/v25.03.md) |
| Auto-coupling | Automatic coupling of devices upon discovery | [24.10](../versions/v24.10.md) |
| Factory reset | Reset a controller to factory settings | [24.07](../versions/v24.07.md) |
| Office function per permission | Office function can be assigned to individual permissions | [24.07](../versions/v24.07.md) |
| PackId global config | PackId configuration defined globally at site level (override per door still available) | [25.02](../versions/v25.02.md) |
| Multi-OSS door config | New endpoint to configure several OSS doors at once | [25.04](../versions/v25.04.md) |
| Multi-device config | New endpoint to configure several device configurations at once | [25.04](../versions/v25.04.md) |
| Per-device schedules | Week/day schedules configurable per device instead of system-wide | [25.02](../versions/v25.02.md) |
| OSS transponder read/write timeout | Configurable read/write timeout for transponders via OSS Updater | [25.02](../versions/v25.02.md) |
| Feature list per device | List all available features per device with enabled/disabled flag | [25.01.00](../versions/v25.01.00.md) · [25.03](../versions/v25.03.md) |
| DOM Online Mesh support | Official support for DOM Online Mesh products | [25.02](../versions/v25.02.md) |

---

## API & Connectivity

| Feature | Description | Versions |
|---------|-------------|----------|
| Global multi-device orders | Global route to send orders to several devices at once | [25.01.00](../versions/v25.01.00.md) |
| OSS transponder last update time | Last updated time of an OSS transponder available via API | [25.04](../versions/v25.04.md) · [25.03](../versions/v25.03.md) |
| API-based DOMController update | Update DOMController via API instead of SSH (fallback mode) | [25.02](../versions/v25.02.md) |
| WebSocket connection limit | Limited to 10 simultaneous WebSocket connections, error 429 beyond | [25.02](../versions/v25.02.md) |
| OSS events WebSocket | Dedicated OSS event route and WebSocket | [23.07](../versions/v23.07.md) |
| Certificate chain support | Support for certificates with full authority certification chain | [25.03](../versions/v25.03.md) |
| OS & packages version via API | List OS version and main package versions through the API | [25.01.00](../versions/v25.01.00.md) |

---

## Synchronization & Schedules

| Feature | Description | Versions |
|---------|-------------|----------|
| Fast Online Synchronization | Reduce sync time from 15 min to 10 sec | [23.03](../versions/v23.03.md) |
| Schedule isolation | Changes only impact devices referring to the modified schedule | [23.03](../versions/v23.03.md) · [23.07](../versions/v23.07.md) |
| DOMService device filter | Filter synchronized devices in DOM Service app | [24.01](../versions/v24.01.md) |
| Wireless+ | Report a transponder to the Access Control Server for access decision | [23.10](../versions/v23.10.md) |

---

## Backup & System

| Feature | Description | Versions |
|---------|-------------|----------|
| Customizable log file size | Log files' size configurable by duration and volume | [25.04](../versions/v25.04.md) |
| Backup with permissions & OSS | Optional permissions and OSS doors included in backups | [24.10](../versions/v24.10.md) |
| Redis in backup | Redis file included in backup (offline devices preserved after restore) | [24.07](../versions/v24.07.md) |
| Device recovery system | Recovery system to retrieve previously coupled lost devices | [25.01.00](../versions/v25.01.00.md) |
| PHP 8 migration | Migration from PHP 7 to PHP 8 | [24.10](../versions/v24.10.md) |
| DOMService OSS config & coupling | Configure OSS and coupling directly from the DOMService App | [24.01](../versions/v24.01.md) |
| OSS dynamic validity groups | Dynamic validity groups in OSS Updater | [23.03](../versions/v23.03.md) |
| OSS Updater | New device for updating OSS transponders, managed by DOMBridge | [22.12](../versions/v22.12.md) |
