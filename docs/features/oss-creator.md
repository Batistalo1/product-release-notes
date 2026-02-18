# OSS Creator

Create OSS application data structure on virgin Desfire transponders.

---

## Overview

The OSS Creator feature allows the OSS Updater to be configured in "creator" mode, enabling the creation of the OSS application data structure on a virgin Desfire transponder. This eliminates the need for pre-provisioned transponders and enables on-site credential creation.

**Available since:** [Version 23.10](../versions/v23.10.md) (October 2023)

---

## How to Use

### Prerequisites

- OSS Updater device configured and coupled to the DOMBridge
- Virgin Desfire transponders
- API v23 or later

### Configuration Steps

1. **Enable Creator Mode**
   
   Set the OSS Updater to "creator" mode via the API:
   
   ```bash
   POST /api/oss/updater/{updater_id}/mode
   {
     "mode": "creator"
   }
   ```

2. **Present Virgin Transponder**
   
   Place the virgin Desfire transponder near the OSS Updater device.

3. **Create OSS Structure**
   
   The OSS Updater will automatically:
   - Detect the virgin transponder
   - Create the OSS application data structure
   - Write the credential information

4. **Verify Creation**
   
   Check the transponder status via:
   
   ```bash
   GET /api/oss/transponder/{transponder_id}/status
   ```

### API Reference

Refer to section **4.8.4.2 Creator function** in the Middleware API Specification v24.

---

## Updates

### [23.10](../versions/v23.10.md) — October 2023
**Initial Release**

- Introduced OSS Creator functionality
- OSS Updater can now be set as "creator" mode
- Enables creation of OSS application data structure on virgin Desfire transponders

### [24.04](../versions/v24.04.md) — April 2024
**EID Support**

- OSS Creator now supports EID (Electronic ID) with Firmware 5.9
- Extended compatibility with newer transponder types

### [24.01](../versions/v24.01.md) — January 2024
**Recovery Enhancement**

- If transponder was not correctly written the first time, it will now be recovered automatically
- Improved reliability of the creation process

---

<!-- ## Related Features

- [OSS Updater](../oss-updater/) — Base device for OSS transponder management
- [OSS Dynamic Validity](../oss-dynamic-validity/) — Configure validity periods for created credentials
- [Special Cards](../special-cards/) — Emergency and Master Key tags

---

## Known Limitations

- Requires physical proximity to the OSS Updater device
- Only compatible with Desfire transponders
- Firmware 5.9+ required for EID support -->
