# Proposal 0001: Modern Media and Communication Controls for Standard PC Keyboards

**Author:** Thanga Ganapathy

**Status:** Draft

**Version:** 2.0

**Supersedes:** Revision 1 (2026-06-01)

**Created:** 2026-06-01

---

## Notational Conventions

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, **MAY**, and **OPTIONAL** in this document are to be interpreted as described in RFC 2119. They denote conformance requirements for any keyboard, firmware, operating system, or application claiming to implement this standard.

---

## Executive Summary

The standard PC keyboard layout has remained stable for decades, and that stability is valuable. However, two keys in the upper-right utility cluster of full-size and tenkeyless keyboards — **Scroll Lock** and **Pause/Break** — are unused by the overwhelming majority of modern users, while two of the most frequent actions in modern computing (muting a microphone and pausing media) have no dedicated, application-independent hardware control.

This proposal repurposes those two low-use keys:

```
Scroll Lock    →    Mute  (microphone)
Pause/Break    →    Play/Pause  (media)
```

Print Screen is retained unchanged. No keys are added or removed; key size, spacing, and physical layout are unchanged.

Unlike Revision 1, this revision specifies behavior normatively. Its central design commitment is **predictability**: because the value of a standard is identical behavior across vendors, every behavior that Revision 1 left to "where possible" is here defined as a conformance requirement with an explicit fallback.

---

## Problem Statement

Modern computer use centers on activities the original layout never anticipated: video meetings, voice calls, online classes, remote-work tools, streaming media, browser media, and voice chat. Yet common actions in these contexts still depend on inconsistent, application-specific shortcuts:

| Application     | Mute / Playback Shortcut                          |
| --------------- | ------------------------------------------------- |
| YouTube         | `K` / `Space` play-pause, `M` mute                |
| Netflix         | `Space` / `Enter` play-pause                      |
| Microsoft Teams | `Ctrl + Space` or platform-specific              |
| Google Meet     | `Ctrl + D` / `Cmd + D` mic mute                   |
| Slack Huddles   | `Ctrl + Shift + Space` / `Cmd + Shift + Space`    |
| Discord         | `Ctrl + Shift + M` / `Cmd + Shift + M`            |
| Zoom            | `Alt + A` / `Cmd + Shift + A`                     |

This fragmentation is the problem a dedicated hardware control surface solves. Meanwhile, Scroll Lock and Pause/Break occupy prime fixed positions while serving almost no one.

---

## Scope

**In scope.** Redefining the default function of exactly two physical key positions:

```
Scroll Lock    →    Mute
Pause/Break    →    Play/Pause
```

**Out of scope.** This proposal does not modify alphabet keys, number keys, the function row, arrow keys, the navigation cluster, the numpad, Print Screen, Insert, Home, End, Page Up, Page Down, Num Lock, Caps Lock, or the Menu/Application key.

The proposal is intentionally narrow to maximize compatibility and adoption.

---

## Target Keyboard Layouts

| Layout    | Also Known As             | Target Status                                       |
| --------- | ------------------------- | --------------------------------------------------- |
| 100%      | Full-size                 | Primary. Retains all three utility-cluster keys.    |
| 96% / 98% | Compact full-size, 1800   | Secondary. Usually retains the cluster.             |
| 80%       | Tenkeyless (TKL)          | Primary. Commonly retains the top-right cluster.    |
| 75%       | Compact TKL               | Partial. Cluster may be relocated.                  |
| 65%       | Compact                   | Limited. Often lacks dedicated cluster keys.        |
| 60%       | Mini                      | Out of primary scope. Function lives on Fn layers.  |

Compact layouts that lack the physical cluster MAY implement the same behavior through firmware layers or programmable keys, but this standard does not require them to add physical keys.

---

## Layout Change

Current cluster:

```
Print Screen    Scroll Lock    Pause/Break
```

Standardized cluster:

```
Print Screen    Mute    Play/Pause
```

| Position | Current Label | Proposed Label | Default Function                |
| -------- | ------------- | -------------- | ------------------------------- |
| Left     | Print Screen  | Print Screen   | Screenshot / screen capture     |
| Middle   | Scroll Lock   | Mute           | Microphone (capture) mute       |
| Right    | Pause/Break   | Play/Pause     | Media play/pause                |

---

## The Mute Key — Normative Behavior

### Default action

A bare press of the **Mute** key **MUST** toggle **microphone capture mute**, not system audio output.

Rationale: muting one's microphone is the high-stakes, time-sensitive action (an unexpected noise during a live meeting). System audio mute is rarely urgent and is reachable via a modifier (below).

### Capture mute MUST be device-independent

A machine commonly has several active capture devices at once (built-in mic, USB headset, webcam mic, Bluetooth headset, audio interface, virtual devices). Muting a single device is unsafe: the active communication application may be capturing from a different device, leaving the user transmitting while believing they are muted.

Therefore:

1. Where the operating system provides a **global / privacy-layer microphone capture mute** (a single control that suppresses all microphone capture regardless of device or application), the Mute key **MUST** bind to it.
2. Where no global capture mute exists, the Mute key **MUST** fall back to muting the **default communication input device**, and the implementation **MUST** document that, in this mode, the guarantee is device-scoped rather than global.

### State indicator is REQUIRED

Because an unmuted microphone is not perceptible to the user, a keyboard implementing the Mute key **MUST** provide a visible mute-state indicator (for example, an LED on or near the key, analogous to Caps Lock). The indicator **MUST** reflect the current capture-mute state. Implementations **SHOULD** also surface state changes through the operating system where supported (for example, an on-screen indicator).

### Labeling

The key **SHOULD** be labeled **Mute** and **SHOULD** carry a **microphone** glyph rather than a speaker glyph, because the default action is microphone mute. A speaker glyph **MUST NOT** be used as the sole label, as it implies output mute.

### System audio (output) mute

`Ctrl + Mute` (Windows/Linux) and `Cmd + Mute` (macOS) **MUST** toggle **system audio output mute**, bound to the operating system's standard output-mute control.

Because audio output is single-sink by default, no global privacy-layer mechanism is required; the standard system output mute is already device-independent from the user's perspective. A state indicator for output mute is **OPTIONAL**, since output mute is self-evident to the user. Setups that intentionally route audio to multiple simultaneous sinks are a known limitation and are out of scope.

### Configurable modes (OPTIONAL)

Implementations MAY offer user-selectable modes:

| Mode         | Behavior                                       |
| ------------ | ---------------------------------------------- |
| Mic Mute     | Default. Bare press toggles capture mute.      |
| Audio Mute   | Bare press toggles system output mute.         |
| Programmable | User-defined action.                           |

The default **MUST** be Mic Mute.

---

## The Play/Pause Key — Normative Behavior

A bare press of the **Play/Pause** key **MUST** emit the standard media play/pause event for the platform, controlling the active or most-recent media session through the operating system's existing media-session handling.

The key **SHOULD** be labeled **Play/Pause** or carry the standard media glyph `▶⏸`.

This control is especially valuable because media frequently plays in a background tab, window, or application, where focus-dependent shortcuts fail.

---

## Modifier Chords — Firmware Resolution (REQUIRED)

The Mute and Play/Pause keys emit **Consumer Control** HID usages (Usage Page 0x0C), while modifier keys (Ctrl, Cmd, Alt) live on the standard keyboard usage page (0x07). These are reported in separate streams, and the association of a held modifier with a consumer-control event is **not defined** by HID and is unreliable across operating systems.

Therefore, all modifier chords defined by this standard (`Ctrl/Cmd + Mute`, and the legacy chords below) **MUST** be resolved **inside the keyboard firmware**. When a modifier is held and one of these keys is pressed, the firmware **MUST** emit the appropriate event directly (a different consumer-control usage, or a standard keyboard scancode) rather than relying on the operating system to associate a modifier with a consumer-control event.

Implementations **MUST NOT** depend on OS-level modifier association for these chords.

---

## Legacy Functions

The default cluster does not provide Scroll Lock, Pause, or Break. This standard does **not** require that a conforming keyboard be incapable of producing these codes; doing so would break genuine current workflows (Excel arrow-key scroll, KVM-switch hotkeys, `Ctrl + Break` Java thread dumps) without benefit.

Legacy access is **OPTIONAL**. Where provided, it **MUST** use one of the following, firmware-resolved per the section above:

| Legacy Function | Recommended Chord            |
| --------------- | ---------------------------- |
| Scroll Lock     | `Alt + Mute`                 |
| Pause           | `Alt + Play/Pause`           |
| Break           | `Ctrl + Alt + Play/Pause`    |

The `Fn` key **MUST NOT** be relied upon for legacy access, because Fn is handled below OS visibility, is vendor-defined and unspecifiable, and is absent on most desktop full-size and TKL keyboards — the primary targets of this standard.

### Internationalization

On many non-US layouts, the right Alt key functions as **AltGr** (a character-composition modifier) rather than a plain Alt. To avoid divergent behavior across layouts, legacy chords **MUST** be triggered by **left Alt**. Firmware **MAY** additionally accept AltGr where doing so does not interfere with character composition, but **MUST NOT** require it.

Alternatively, implementations **MAY** omit in-layout legacy chords entirely and expose Scroll Lock / Pause / Break only through vendor configuration software.

---

## Combined Modifier Table

For clarity, the complete default behavior of the two repurposed keys:

| Input                       | Action                                  |
| --------------------------- | --------------------------------------- |
| `Mute`                      | Microphone (capture) mute toggle        |
| `Ctrl` / `Cmd` + `Mute`     | System audio output mute toggle         |
| `Alt` + `Mute`              | Scroll Lock (legacy, optional)          |
| `Play/Pause`                | Media play/pause                        |
| `Alt` + `Play/Pause`        | Pause (legacy, optional)                |
| `Ctrl` + `Alt` + `Play/Pause` | Break (legacy, optional)              |

All chorded rows are firmware-resolved.

---

## Operating System Requirements

A conforming operating system:

- **MUST** expose, or define, a media play/pause event the Play/Pause key can drive against the active/background media session.
- **SHOULD** provide a global microphone capture (privacy-layer) mute that the Mute key can bind to; where absent, the keyboard falls back to default-device capture mute.
- **MUST** route `Ctrl/Cmd + Mute` to the system output mute control.
- **SHOULD** surface capture-mute state to the user (on-screen indicator) in addition to the hardware LED.

---

## Application Requirements

- Media applications **MUST** respond to the standard play/pause media event.
- Communication applications **SHOULD** integrate with the operating system's global capture-mute state where the platform provides it, so that the hardware Mute key and in-app mute remain consistent. Applications **MUST NOT** be required to expose proprietary mute APIs for the standard to function; the OS-level capture mute is the canonical mechanism.

---

## Accessibility

Dedicated, application-independent Mute and Play/Pause keys reduce reliance on mouse movement, visual targeting of small on-screen controls, and memorization of per-application shortcuts. This benefits keyboard-only users, users with limited motor precision or dexterity, low-vision users, users of assistive input devices, and users for whom per-app shortcut variance is a cognitive burden.

The REQUIRED mute-state indicator is itself an accessibility feature: it gives non-auditory confirmation of microphone state, which is otherwise imperceptible.

---

## Benefits

- **Usability:** direct access to two of the most frequent modern actions.
- **Meeting control:** fast, reliable, device-independent microphone mute with visible confirmation.
- **Media control:** consistent play/pause regardless of window focus.
- **Reduced fragmentation:** one hardware control surface replaces a dozen app-specific shortcuts.
- **Accessibility:** fewer fine-motor and visual-targeting demands; non-auditory mute confirmation.
- **Minimal manufacturing impact:** no new keys, no size, spacing, or section changes — only relabeling and firmware behavior for two existing keys, plus one indicator LED.

---

## Conformance

An implementation conforms to this standard if it satisfies all **MUST** / **MUST NOT** requirements applicable to its category (keyboard, firmware, operating system, or application). The defining requirements are:

1. Bare Mute toggles device-independent microphone capture mute (global where available; default-device fallback otherwise).
2. A visible mute-state indicator is present and accurate.
3. `Ctrl/Cmd + Mute` toggles system output mute.
4. Play/Pause emits the standard media event.
5. All modifier chords are firmware-resolved, not OS-modifier-associated.
6. No reliance on the Fn key for any defined behavior.
7. Legacy chords, if present, use left Alt and are firmware-resolved.

---

## Adoption Note

No formal body governs the PC keyboard layout; it is an emergent convention sustained by HID usage tables and manufacturer practice. Adoption therefore proceeds by manufacturers shipping this behavior as a default, not by ratification. The relevant HID usages (Mute 0xE2, Play/Pause 0xCD) already exist, so the implementation cost is firmware and labeling, not new hardware. The precision of this document is itself the adoption argument: a vendor should be able to implement it without a single judgment call.

---

## Conclusion

Scroll Lock and Pause/Break are the right two keys to modernize: low-use, fixed in prime positions, and replaceable without disturbing anything else. Revision 1 identified this correctly. This revision makes the idea implementable by replacing every "where possible" with a conformance requirement and an explicit fallback — defining mute as a device-independent capture mute with a mandatory indicator, resolving modifier chords in firmware rather than via fragile HID association, dropping the unspecifiable Fn dependency, and handling internationalization explicitly.

The change preserves the layout's stability while making two of computing's most frequent actions directly, predictably, and accessibly available — which is exactly what a keyboard standard should do.
