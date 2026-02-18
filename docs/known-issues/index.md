# Known Issues

Tracking of known problems, workarounds and fix status across versions.

---

## Active Issues

No known active issues on the latest version (25.04).

---

## Resolved Issues

| Issue | Affected Versions | Fixed in | Workaround |
|-------|------------------|----------|------------|
| DOMService synchronization sometimes stuck | [24.07](../versions/v24.07.md) | [24.10](../versions/v24.10.md) | In DOMPloy 12.0: click the **Offline** tab |
| Online coupling stuck in "coupling" state | [22.12](../versions/v22.12.md) | [23.03](../versions/v23.03.md) | Open RFNM settings → "route devices" tab → submit again |
| Battery replacement not always detected | [23.07](../versions/v23.07.md) | [23.10](../versions/v23.10.md) | No workaround available |

---

## Issue Details

---

### DOMService synchronization sometimes stuck
<span class="badge badge-fixed">FIXED</span>

**Affected versions:** [24.07](../versions/v24.07.md)  
**Fixed in:** [24.10](../versions/v24.10.md)

**Description:** Synchronization with the DOMService application could randomly get stuck.

**Workaround:** A workaround is available in **DOMPloy 12.0** by clicking on the **"Offline"** tab.

---

### Online coupling stuck in "coupling" state
<span class="badge badge-fixed">FIXED</span>

**Affected versions:** [22.12](../versions/v22.12.md)  
**Fixed in:** [23.03](../versions/v23.03.md)

**Description:** Online coupling could sometimes get stuck indefinitely with the device remaining in "coupling" state.

**Workaround:** Open RFNM settings → go to the **"route devices"** tab → submit the configuration again.

---

### Battery replacement not always detected
<span class="badge badge-fixed">FIXED</span>

**Affected versions:** [23.07](../versions/v23.07.md)  
**Fixed in:** [23.10](../versions/v23.10.md)

**Description:** Battery replacement was not always correctly detected and stored.

**Workaround:** No workaround available. Upgrading to version 23.10 is recommended.
