# Tt Theme (`Tt Light` & `Tt Dark`) for Windows Terminal

Day/night twin color schemes for Windows Terminal synthesizing **Atom One (Light & Dark)** syntax hues with the **Guizang Design System** ([op7418/dsh-guizang-design](https://github.com/op7418/dsh-guizang-design)) — Swiss International neutrals (`#FAFAF8` / `#141413`), Klein Blue anchors (`#002FA7` / `#5B7BFF`), `midnight-ink` warm gold accents (`#E0AB56`), and OKLCH + APCA/WCAG dual-threshold calibration.

## Twin Philosophy & Anti-Invisibility Design

| Feature | `Tt Light` (Day) | `Tt Dark` (Night) |
|---|---|---|
| **Canvas (`background`)** | `#FAFAF8` (Guizang Swiss `--paper`) | `#141413` (Warm-neutral Obsidian, mirror of `#FAFAF8`) |
| **Primary Ink (`foreground`)** | `#24262B` (`14.49:1` / APCA `99.0`) | `#E8E6E1` (`14.78:1` / APCA `91.0`) |
| **Klein Anchor (`cursorColor`)** | `#002FA7` (Swiss IKB `--accent`) | `#5B7BFF` (Swiss IKB `--accent-bright`) |
| **Selection (`selectionBackground`)** | `#E2ECFF` | `#223052` |
| **Invisibility Fix** | Solid `inkRole` neutral slots fix `\x1b[37m` (`#4B5263`) & `\x1b[97m` (`#383A42`) white-on-white | Lifted `black` (`#73716A`, `30m`) & `brightBlack` (`#ABA8A0`, `90m`) fix black-on-black |

---

## Palette Reference

### 1. `Tt Light` (vs `#FAFAF8`)

| Slot | Hex | Role / Origin | WCAG 2.1 | APCA Lc |
|---|---|---|---|---|
| `background` | `#FAFAF8` | Guizang Swiss `--paper` | — | — |
| `foreground` | `#24262B` | Primary ink | `14.49:1` | `99.0` |
| `cursorColor` | `#002FA7` | Guizang Swiss IKB anchor | `10.23:1` | `90.4` |
| `selectionBackground` | `#E2ECFF` | Derived light selection | — | — |
| `black` | `#181A1F` | Deep ink (`30m`) | `16.66:1` | `101.2` |
| `brightWhite` | `#383A42` | Atom One Light `mono-1` (`97m`) | `10.85:1` | `93.1` |
| `white` | `#4B5263` | Slate ink (`37m`, anti-invisible fix) | `7.48:1` | `84.1` |
| `brightBlack` | `#696C77` | Atom One Light `mono-2` (`90m`) | `5.01:1` | `72.9` |
| `red` / `brightRed` | `#CA1243` / `#E45649` | Atom One Light `red-2` / `red-1` | `5.46` / `3.51` | `73.3` / `60.3` |
| `green` / `brightGreen` | `#348133` / `#50A14F` | Calibrated ink / Atom One Light green | `4.64` / `3.07` | `70.2` / `55.9` |
| `yellow` / `brightYellow` | `#986801` / `#C18401` | Atom One Light `orange-1` / `orange-2` | `4.66` / `3.06` | `70.4` / `55.8` |
| `blue` / `brightBlue` | `#265CE0` / `#4078F2` | Calibrated ink / Atom One Light blue | `5.45` / `3.87` | `74.7` / `64.2` |
| `purple` / `brightPurple` | `#A626A4` / `#C03DC2` | Atom One Light purple / bright orchid | `5.85` / `4.29` | `76.1` / `67.0` |
| `cyan` / `brightCyan` | `#0177AB` / `#0184BC` | Calibrated ink / Atom One Light cyan | `4.75` / `4.00` | `70.7` / `65.1` |

### 2. `Tt Dark` (vs `#141413`)

| Slot | Hex | Role / Origin | WCAG 2.1 | APCA Lc |
|---|---|---|---|---|
| `background` | `#141413` | Obsidian mirror of `#FAFAF8` | — | — |
| `foreground` | `#E8E6E1` | Warm paper ink | `14.78:1` | `91.0` |
| `cursorColor` | `#5B7BFF` | Guizang Swiss IKB `--accent-bright` | `5.02:1` | `37.0` |
| `selectionBackground` | `#223052` | Dark Klein selection | — | — |
| `black` | `#73716A` | Lifted muted ink (`30m`, anti-invisible fix) | `3.77:1` | `27.1` |
| `brightBlack` | `#ABA8A0` | Agent thoughts & prediction (`90m`) | `7.76:1` | `54.5` |
| `white` | `#D5D2CA` | Guizang `midnight-ink --text-body` (`37m`) | `12.20:1` | `78.6` |
| `brightWhite` | `#FAFAF8` | `Tt Light` paper white (`97m`) | `17.64:1` | `103.7` |
| `red` / `brightRed` | `#F2747D` / `#FF9399` | OKLCH lifted Atom One Dark red | `6.64` / `8.68` | `48.2` / `60.2` |
| `green` / `brightGreen` | `#98C379` / `#B5DE8A` | Atom One Dark `hue-4` / bright green | `9.14` / `12.10` | `62.6` / `78.1` |
| `yellow` / `brightYellow` | `#E0AB56` / `#F5CF6B` | Guizang `midnight-ink --accent-ink` / bright gold | `8.89` / `12.31` | `61.2` / `79.2` |
| `blue` / `brightBlue` | `#61AFEF` / `#96B0FF` | Atom One Dark `hue-2` / Swiss `--accent-ink-inverse` | `7.80` / `8.73` | `54.9` / `60.3` |
| `purple` / `brightPurple` | `#CF82E6` / `#E394FB` | OKLCH lifted Atom One Dark purple | `7.01` / `8.69` | `50.2` / `60.1` |
| `cyan` / `brightCyan` | `#56B6C2` / `#7AD8E4` | Atom One Dark `hue-1` / bright cyan | `7.78` / `11.21` | `54.8` / `73.7` |

---

## Install & Auto Day/Night Switching

1. Open Windows Terminal `settings.json` (`Ctrl+Shift+,`, or `%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json`).
2. Add both [`tt-light.json`](tt-light.json) and [`tt-dark.json`](tt-dark.json) to your `"schemes"` array.
3. Configure automatic OS light/dark switching in `settings.json`:

```json
{
  "theme": "system",
  "profiles": {
    "defaults": {
      "adjustIndistinguishableColors": "indexed",
      "colorScheme": {
        "dark": "Tt Dark",
        "light": "Tt Light"
      }
    }
  }
}
```
