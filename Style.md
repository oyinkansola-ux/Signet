# Signet — UI Style Direction

## Design Philosophy

Signet is a tool built for moments that matter. Weddings. Conferences. Meetups. Private gatherings. The people using it are not designers — but they want their event to feel designed.

The app's visual language reflects this. It is warm, confident, and considered. It does not shout. It does not perform. It creates the conditions for the pass — the actual product — to be the hero.

Every decision in this document serves one goal:
**The pass looks beautiful. The app gets out of the way.**

---

## Visual Mood

Clean. Warm. Purposeful.

Not startup-flashy. Not corporate-cold. Not vibe-coded generic.

Think of a well-designed invitation. The paper has weight. The type is considered. There is breathing room. Nothing is decorative for its own sake. Everything earns its place.

References: Stripe, Resend, Linear — but warmer. More human.

---

## Color System

Three colors. One role each. Nothing more.

---

### Dominant — Deep Slate
**Hex:** `#1C1C1E`

The foundation. Used for navigation, headings, key UI chrome, and anywhere the app needs to feel grounded and authoritative.

Not pure black. The warmth in this slate keeps it from feeling harsh.

**Used on:**
- Top navigation bar
- Primary headings (H1, H2)
- Footer
- Pass preview chrome / frame
- Icon strokes

---

### Accent — Warm Amber
**Hex:** `#E8A020`

One accent. Used sparingly and with intention. Every time amber appears, it means something — it is asking the user to act, or confirming something important.

Not orange. Not neon yellow. Warm, controlled, and purposeful. The color of candlelight. Of a wax seal. Of occasion.

**Used on:**
- Primary CTA buttons only (Create Event, Generate Passes, Download)
- Active navigation state indicator
- QR code border on the pass
- Ticket type badge background (VIP)
- Hover state on key interactive elements
- Pass number accent line

**Never used on:**
- Backgrounds
- Decorative elements
- More than one button per screen

---

### Neutral — Soft Stone
**Hex:** `#F5F4F0`

Warm off-white. The page breathes here. Not pure white — the warmth prevents the UI from feeling clinical.

**Used on:**
- Page background
- Form input backgrounds
- Secondary card surfaces
- Pass preview panel background
- Empty state backgrounds

---

### Supporting — Functional Colors Only
These are not brand colors. They exist only for system feedback states.

| Role | Hex | Used for |
|---|---|---|
| Success | `#2D7A4F` | Valid scan screen, success toast |
| Error | `#C0392B` | Invalid / already used scan screen, error states |
| Text primary | `#1C1C1E` | All primary body text |
| Text secondary | `#6B6B6B` | Labels, captions, helper text |
| Text tertiary | `#9A9A9A` | Placeholder text, disabled states |
| White | `#FFFFFF` | Card surfaces, pass body, modal backgrounds |
| Border | `#E4E3DF` | Input borders, card borders, dividers |

---

## Typography

Two typefaces. One for personality. One for function. Never uniform.

---

### Display & Hero — Instrument Serif
**Use:** Italic weight only for display moments

Used on:
- App logo / wordmark (Signet in italic serif)
- Landing page hero headline
- Large event name on the pass itself
- Empty state headline

Why: Adds warmth and personality without being decorative. Breaks the monotony of all-sans interfaces. Creates immediate hierarchy. Connects to the idea of a signet — something historical, considered, and weighted.

---

### UI & Body — Geist
**Use:** Regular (400) and Medium (500) weights only

Used on:
- All navigation items
- All button labels
- All form labels and inputs
- Body text and descriptions
- Dashboard data
- Attendee list
- Pass details (date, venue, ticket type, pass number)
- Captions and helper text

Why: Designed specifically for interfaces. Clean without being Inter-generic. Holds personality at small sizes. Works at every scale from 11px captions to 24px subheadings.

---

### Type Scale

| Role | Typeface | Size | Weight | Line Height |
|---|---|---|---|---|
| Hero headline | Instrument Serif Italic | 48px | Italic | 1.1 |
| H1 | Geist | 32px | 500 | 1.2 |
| H2 | Geist | 24px | 500 | 1.3 |
| H3 | Geist | 18px | 500 | 1.4 |
| Body | Geist | 15px | 400 | 1.6 |
| Label | Geist | 13px | 500 | 1.4 |
| Caption | Geist | 12px | 400 | 1.5 |
| Button | Geist | 14px | 500 | 1 |

---

## Spacing System

Base unit: **8px**

All spacing decisions are multiples of 8.

| Token | Value | Used for |
|---|---|---|
| xs | 4px | Tight internal gaps (icon to label) |
| sm | 8px | Component internal padding |
| md | 16px | Between related elements |
| lg | 24px | Between sections within a card |
| xl | 40px | Between major sections on a page |
| 2xl | 64px | Page-level breathing room |
| 3xl | 96px | Hero sections |

White space is not empty space. It creates grouping, hierarchy, and breathing room. Elements that belong together sit closer. Elements that are separate have room between them.

---

## Component Style

### Buttons

**Primary Button** (Amber)
- Background: `#E8A020`
- Text: `#1C1C1E` (dark on amber — never white)
- Border radius: 8px
- Padding: 12px 24px
- Font: Geist 14px 500
- Hover: `#D4911A` (slightly darker amber)
- One per screen maximum

**Secondary Button** (Outlined)
- Background: transparent
- Border: 1.5px solid `#1C1C1E`
- Text: `#1C1C1E`
- Border radius: 8px
- Padding: 12px 24px
- Hover: background `#F5F4F0`

**Ghost Button** (Text only)
- No background, no border
- Text: `#6B6B6B`
- Hover: text `#1C1C1E`
- Used for: cancel actions, secondary navigation

**Destructive Button** (for delete/invalidate actions)
- Background: transparent
- Border: 1.5px solid `#C0392B`
- Text: `#C0392B`
- Hover: background `#FDF2F2`

---

### Cards
- Background: `#FFFFFF`
- Border: 1px solid `#E4E3DF`
- Border radius: 12px
- Padding: 24px
- No drop shadows — border only
- Hover state (on clickable cards): border color `#1C1C1E`

---

### Form Inputs
- Background: `#FFFFFF`
- Border: 1.5px solid `#E4E3DF`
- Border radius: 8px
- Padding: 12px 16px
- Font: Geist 15px 400
- Placeholder: `#9A9A9A`
- Focus border: `#1C1C1E` (1.5px)
- Error border: `#C0392B`
- Label above input: Geist 13px 500 `#1C1C1E`
- Helper text below: Geist 12px 400 `#6B6B6B`

---

### Badges / Ticket Type Pills
- Border radius: 100px (fully rounded pill)
- Padding: 4px 12px
- Font: Geist 12px 500

| Type | Background | Text |
|---|---|---|
| General | `#F5F4F0` | `#1C1C1E` |
| VIP | `#E8A020` | `#1C1C1E` |
| Speaker | `#1C1C1E` | `#FFFFFF` |
| Custom | `#E4E3DF` | `#6B6B6B` |

---

### Navigation
- Background: `#1C1C1E`
- Logo: Instrument Serif Italic, white
- Nav links: Geist 14px 400, `#9A9A9A`
- Active nav link: Geist 14px 500, `#FFFFFF` with amber left indicator dot
- Height: 60px
- No bottom border — the contrast with the page bg is enough

---

### Pass Preview Panel
- Background: `#F5F4F0`
- The pass card sits centered in this panel
- Pass card: `#FFFFFF` background, 12px border radius
- Subtle border: 1px `#E4E3DF`
- No shadow on the pass card — let the border and background contrast do the work
- The pass scales down proportionally on smaller screens

---

### Scanner / Verify Mode Screens

**Valid scan:**
- Full screen background: `#2D7A4F`
- Text: white
- Attendee name: Geist 32px 500
- Ticket type: Geist 16px 400
- Status label: "Checked In" — Geist 14px 500

**Already used:**
- Full screen background: `#C0392B`
- Text: white
- Message: "Already Checked In"
- Original scan timestamp shown below

**Invalid:**
- Full screen background: `#C0392B`
- Text: white
- Message: "Invalid Pass"

All three screens have a "Scan Next" button at the bottom to return to camera view immediately.

---

## What We Are Deliberately Avoiding

| Avoid | Reason |
|---|---|
| Neon or high saturation colors | Looks cheap, hard to read, dates quickly |
| Blue to purple gradients | Every vibe-coded app has this — instant tell |
| Glowing text or glowing backgrounds | Decorative, not functional |
| Emojis in the UI | Unprofessional in a tool context |
| Inter as the sole typeface | Zero personality, blends into every other app |
| Uniform type sizing | Destroys hierarchy — everything looks the same weight |
| Pure white `#FFFFFF` as page background | Too flat, no depth, clinical |
| Drop shadows on cards | Overused — border contrast achieves the same result cleanly |
| Decorative illustrations | Not what this product is — it should feel like a tool |
| Multiple accent colors | One accent, one meaning, maximum impact |

---

## Dark Mode

Dark mode ships after light mode is complete and stable.

When dark mode is implemented:

| Light | Dark |
|---|---|
| Page background `#F5F4F0` | `#111110` |
| Card background `#FFFFFF` | `#1C1C1E` |
| Navigation `#1C1C1E` | `#0D0D0C` |
| Primary text `#1C1C1E` | `#F0EFEB` |
| Secondary text `#6B6B6B` | `#8A8A8A` |
| Border `#E4E3DF` | `#2C2C2A` |
| Accent amber `#E8A020` | `#E8A020` (unchanged) |
| Input background `#FFFFFF` | `#252524` |

The amber accent remains identical in both modes — it is the one constant.

---

## Layout Principles

**Proximity creates grouping.**
Elements that belong together sit close. Elements that are separate have room. Never use borders or dividers when spacing alone can create the separation.

**Hierarchy through scale and weight.**
Not through color. The eye should move naturally from the most important thing to the least important — driven by size and weight difference, not by making things bright or loud.

**White space is a design element.**
Generous padding inside cards. Generous margins between sections. The UI should feel like it has room to breathe. A crowded interface signals a product that has not thought about what matters.

**The pass is always visible.**
On the event branding screen, the pass preview is always on screen. The organiser is never working blind. What they build is what they get.

**Mobile first.**
Every screen is designed for 390px width first. Desktop is an expansion of mobile — not the other way around. The scanner screen in particular must be perfect on mobile.
