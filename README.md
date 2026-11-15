# Tt Light for Windows Terminal

A bright, high-readability light color scheme for Windows Terminal that synthesizes **Atom One Light** syntax hues with the **Guizang Design System** ([op7418/dsh-guizang-design](https://github.com/op7418/dsh-guizang-design)) Swiss International paper neutrals (`#FAFAF8`), Klein Blue (`#002FA7`) anchor, and OKLCH + APCA/WCAG dual-threshold contrast verification.

## Design Highlights

1. **White-on-White (`\x1b[37m` / `\x1b[97m`) Fix via `inkRole` Solid Ink Hierarchy**
   Conventional light terminal themes leave `white` and `brightWhite` near `#FFFFFF`, causing CLI tools, AI agents, and PowerShell outputs that emit `\x1b[37m` or `\x1b[1;97m` to disappear against a light background. **Tt Light** maps all monochrome slots onto a solid ink hierarchy (`#181A1F` -> `#24262B` -> `#383A42` -> `#4B5263` -> `#696C77`), guaranteeing `APCA |Lc| >= 72.9` (`WCAG >= 5.01:1`) for every neutral text slot.
2. **Swiss Paper Canvas + Klein Blue Anchor**
   Uses Guizang Swiss neutral paper `#FAFAF8` (warm-neutral off-white without harsh `#FFFFFF` glare or muddy sepia), Klein Blue `#002FA7` cursor, and derived selection `#E2ECFF`.
3. **Dual-Track Chromatic Mapping (`--accent-ink` vs `--accent-display`)**
   - **Normal ANSI (`31m–36m`)**: Contrast-calibrated `--accent-ink` shades (`WCAG 4.64–5.85:1`, `APCA 70.2–76.1`) for sharp small text, diffs, and error logs.
   - **Bright ANSI (`91m–96m`)**: Vivid **Atom One Light** `--accent-display` highlights (`APCA 55.8–67.0`) so prompts, badges, and Agent UI stay lively and luminous.

## Palette Reference (vs `#FAFAF8`)

| Slot | Hex | Role / Origin | WCAG 2.1 | APCA Lc |
|---|---|---|---|---|
| `background` | `#FAFAF8` | Guizang Swiss `--paper` | — | — |
| `foreground` | `#24262B` | Primary ink | `14.49:1` | `99.0` |
| `cursorColor` | `#002FA7` | Guizang Swiss IKB anchor | `10.23:1` | `90.4` |
| `selectionBackground` | `#E2ECFF` | Derived tint (`bg/sel` highlight) | — | — |
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

## Install

1. Open Windows Terminal settings JSON (`Ctrl+Shift+,`, or `%LOCALAPPDATA%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json`).
2. Add the object from [`tt-light.json`](tt-light.json) to the `"schemes"` array.
3. Set it as your profile default:

```json
"profiles": {
  "defaults": {
    "colorScheme": "Tt Light",
    "adjustIndistinguishableColors": "indexed"
  }
}
```
