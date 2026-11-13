# My diagram style guide (v1)

Use this for every diagram from Day 18 onwards. **Rule:** colour must *mean* something. If it doesn't, use grey.

## 1. Colour: only 3
| Colour | Means | Border / fill |
|---|---|---|
| **Blue** | **Ours**: things we build and run | `#0969da` / `#ddf4ff` |
| **Orange** | **External**: things we don't control (cloud APIs, third-party servers) | `#bc4c00` / `#fff1e5` |
| **Red** | **Errors only**: failures, error paths | `#cf222e` / `#ffebe9` |

**Neutrals** (don't count as colours):

| Role | Hex |
|---|---|
| Ink (text) | `#1f2328` |
| Grey (secondary) | `#57606a` |
| Mute (lifelines) | `#8c959f` |
| Line (borders) | `#d0d7de` |
| Background (neutral fill) | `#f6f8fa` |

People, notes and anything without a meaning stay neutral.

## 2. Type: one font
Helvetica only, in 4 sizes and 2 weights:

| Size | Weight | Use |
|---|---|---|
| 22 | bold | Diagram title (one per page) |
| 13 | bold | Participant / box names |
| 12 | regular | Arrow labels |
| 11 | regular | Notes, legend, sub-labels |

## 3. Lines
| Thing | Style |
|---|---|
| Shape border | 1 px solid |
| Lifeline | 1 px dashed `4 4`, mute grey |
| Request (sender waits) | 1.5 px solid ink, **filled** head |
| Response | 1.5 px **dashed** grey, open head |
| Async (no reply) | 1.5 px solid ink, **open** head |
| Architecture link | 1.5 px **elbow** (orthogonal) only |

The **kind** of message is shown by **line style**, not colour.

## 4. Space
- Spacing scale: **8 · 16 · 24 · 36 · 40 · 240** px. Never place things by eye.
- Margin 40 · message row 36 · participant column 240 · box 160 × 46.
- Fixed places:
  - title: top-left
  - version: top-right
  - notes rail: right side
  - legend strip: bottom, always in the order colours → arrows → notes

## 5. Draw.io settings
- Font: *Format → Text → Font* = Helvetica.
- Save each style once: style a shape → *Edit Style* → copy the style text into this file or a scratch page.
- Copy a style onto other shapes: `Ctrl/Cmd + Shift + C`, then `Ctrl/Cmd + Shift + V`.

**Check:** cover the legend. If a colour still needs explaining, it's decoration. Remove it.
