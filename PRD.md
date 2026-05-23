# Signet — Product Requirements Document

## Overview

**Product Name:** Signet  
**Type:** Web Application  
**Version:** 1.0 MVP  
**Last Updated:** May 2026  

Signet is a lightweight web application that allows event organisers to generate branded digital event passes with scannable QR codes. It is designed for small and medium-sized events — meetups, weddings, workshops, conferences, and private gatherings — where organisers need professional-looking passes without advanced design or technical skills.

The name Signet is derived from the historical signet seal — a mark pressed to authenticate and validate. Every pass Signet generates is a seal of authenticity. Proof that someone is expected, that they belong, that their entry is real.

---

## The Problem

Small and medium event organisers in Nigeria and globally face a gap in the market:

- **Eventbrite** is too large, too corporate, and produces generic ugly tickets
- **Luma** handles RSVPs well but has no branded pass generation or door scanning
- **Canva** produces beautiful designs but has no QR generation or attendee management
- **PassKit** is a developer tool — not accessible to non-technical organisers

The result: organisers either send plain text confirmations, manually design passes one at a time in Canva, or use nothing at all. Their events look unfinished before they even begin.

---

## The Solution

Signet sits in the gap between all of them.

Design quality of Canva + simplicity of Luma + QR functionality of Eventbrite — in one lightweight tool built for organisers who want their event to feel real and considered.

**Core value proposition:**  
*Generate beautiful, branded, scannable event passes in minutes. No design skills required.*

---

## Target Users

**Primary:** Small and medium event organisers  
- Tech meetup hosts  
- Wedding planners and couples  
- Workshop and masterclass facilitators  
- Conference and summit organisers  
- Private party and gathering hosts  

**Geography:** Nigeria-first, globally applicable  

**Technical level:** Non-technical. The product must work without any learning curve.

---

## User Persona

**Temi** — Lagos-based community organiser  
Running a tech meetup for 80 people. Needs passes that look professional, carry each person's name and ticket type, include a scannable QR code, and can be sent out quickly. Has no design software. Has no developer on her team. Has a deadline.

---

## User Journey

```
Landing Page
    ↓
Sign Up / Sign In
    ↓
Dashboard (all events)
    ↓
Create New Event
    ↓
Set Event Branding (color + template + banner)
    ↓
Add Attendees (manual or CSV upload)
    ↓
Real-time Pass Preview
    ↓
Generate All Passes
    ↓
Download (PNG / PDF) or Email Passes
    ↓
Share Passes with Attendees
    ↓
Scan at Door (Verify Mode)
    ↓
Track Attendance in Dashboard
```

---

## Core Features

### 1. Authentication
- Sign up with name, email, and password
- Sign in with email and password
- Optional — a user can preview the pass generator without an account but must sign in to save events and manage attendees
- Session persistence — Temi can close the tab and return to her dashboard

### 2. Event Creation
Users provide:
- Event name
- Event date and time
- Venue / location
- Organiser name / organisation
- Optional event description

The event is saved as a record in the dashboard. It can be edited at any time.

### 3. Event Branding
Users customise:
- **Brand color** — one primary color applied across the pass (header, QR border, badge accents)
- **Pass template** — three layout options:
  - **Modern Card** — horizontal layout, event name prominent at top, QR code right-aligned
  - **Minimal Stripe** — bold color stripe header, clean white body, information stacked
  - **Bold Banner** — uploaded image fills the top half with dark overlay, white text on top
- **Optional banner/cover image** — uploaded by the organiser, used in the Bold Banner template or as a header element in others
- Real-time preview updates as the organiser makes changes

### 4. Attendee Management
Two methods of adding attendees:

**Manual Entry**
- Attendee name
- Attendee email (optional)
- Ticket / pass type (General / VIP / Speaker / Custom)
- Add one at a time

**CSV Bulk Upload**
- Organiser downloads a CSV template from the app
- Fills in: name, email, ticket type
- Uploads the file
- App reads all rows and generates one pass per attendee instantly

Each attendee record is saved and visible in the attendee list for that event.

### 5. Pass Generation
Each generated pass includes:
- Event name
- Event date, time, and venue
- Organiser details
- Attendee name
- Ticket / pass type with badge
- Unique QR code tied to that specific attendee
- Pass number / ID (e.g. #0042)
- Brand color applied across the pass
- Optional banner image

### 6. Pass Download and Sharing
- Download individual pass as **PNG**
- Download individual pass as **PDF**
- Download all passes as a ZIP file (bulk)
- Email pass directly to attendee's email address (if provided)
- Share link (optional)

### 7. QR Verification — Scanner Mode
A dedicated full-screen scanner view optimised for mobile. No physical scanner device is required. The door person uses their phone camera through the app to scan attendee passes.

**How it works:**
- Temi generates a unique scan-only link for her event — for example `signet.app/scan/event-abc123`
- She shares this link with whoever is managing the door via WhatsApp, text, or any channel
- The door person opens the link on their phone browser — no account, no login, no app download required
- The link opens directly into Scanner Mode — full screen camera view
- The door person points their phone at the attendee's pass (PNG or PDF on the attendee's phone screen)
- The app reads the QR code and shows the result instantly

**What the attendee needs:**
- Just their pass image — PNG or PDF received via WhatsApp or email
- No app. No account. Just open the image and show the screen.

**The scan-only link is scoped to one event only.** The door person cannot see Temi's dashboard, other events, or any organiser data. They can only scan passes for that specific event.

**Verification states:**
- **Valid** — Full green screen. Attendee name and ticket type shown clearly. Confirmed first-time scan.
- **Already Used** — Full red screen. "This pass has already been scanned." Timestamp of original scan shown.
- **Invalid** — Full red screen. "This QR code is not recognised."
- **VIP** — Full green screen with VIP badge highlighted prominently at the top. Door person knows immediately to treat this attendee differently.

Each scan result is logged automatically and reflected in real time on Temi's Attendance Dashboard.

### 8. Attendance Dashboard
After passes are scanned, the organiser sees:
- Total attendees
- Total checked in
- Total not yet arrived
- Per-attendee status: name, ticket type, checked in / not arrived, timestamp if checked in

### 9. Pass Regeneration and Editing
- Organiser can regenerate a pass for any attendee (if they lost it)
- Organiser can edit attendee details and regenerate
- Regenerating a pass invalidates the old QR code and issues a new one

### 10. Dark / Light Mode
- Default: Light mode
- Toggle available in navigation
- Full UI adapts — dashboard, forms, pass preview panel
- Pass preview remains accurate in both modes

---

## Pass Templates — Detail

### Template 1: Modern Card
- Horizontal layout
- Left side: event name (large), date, venue, organiser
- Right side: QR code (prominent), attendee name, ticket type badge
- Brand color applied to header bar and QR border
- Clean white body

### Template 2: Minimal Stripe
- Vertical layout
- Bold color stripe at top using brand color
- Event name in white on the stripe
- White body below: attendee name, ticket type, date, venue, QR code at bottom
- Minimal, structured, easy to scan

### Template 3: Bold Banner
- Vertical layout
- Uploaded image fills top 40% with dark overlay
- Event name and organiser in white over the image
- White body: attendee name, ticket type badge, date, venue
- QR code at bottom with brand color border

---

## Technical Requirements

### Frontend
- React (via Lovable)
- Mobile-first responsive design
- Real-time pass preview on event branding screen
- QR code generation client-side (qrcode.js or equivalent)
- PNG export (html2canvas or equivalent)
- PDF export (jsPDF or equivalent)

### Backend / Database
- Supabase for authentication and data storage
- Tables: users, events, attendees, passes, scan_logs

### Data Model (simplified)

**Events**
- id, user_id, name, date, time, venue, organiser, description, brand_color, template, banner_url, scan_token (unique public token for scan-only link), created_at

**Attendees**
- id, event_id, name, email, ticket_type, pass_number, qr_code, status (unused/used), scanned_at, created_at

**Scan Logs**
- id, attendee_id, event_id, scanned_at, result (valid/already_used/invalid)

---

## Screen List

1. Landing Page
2. Sign Up
3. Sign In
4. Dashboard (all events)
5. Create Event (step 1 — event details)
6. Event Branding (step 2 — color, template, banner)
7. Add Attendees (step 3 — manual + CSV)
8. Pass Preview and Generate (step 4)
9. Attendee List (per event)
10. Pass Detail (individual pass view)
11. Scanner / Verify Mode (mobile-optimised, no login required — opens via scan-only link)
11b. Scan Result Screen (full screen green / red feedback)
12. Attendance Dashboard (per event)
13. Settings (profile, dark/light mode toggle)

---

## Non-Functional Requirements

- Mobile-first. The scanner screen must work perfectly on any phone.
- No emojis in the UI.
- No decorative gradients, glow effects, or neon colors.
- The pass is the hero. The app frames it — not competes with it.
- Load time under 3 seconds on a standard Nigerian mobile connection.
- All user data scoped to authenticated user only.

---

## Out of Scope for MVP

- Apple Wallet / Google Wallet integration
- Payment / ticketing (paid events)
- Custom domain for event pages
- Multi-organiser teams
- Analytics beyond attendance tracking
- Recurring events

---

## Success Metrics

- Organiser can create an event and generate passes in under 5 minutes
- Pass looks professional enough to screenshot and share
- QR scan gives a result in under 2 seconds
- Zero confusion on the attendee management screen

---

## Deliverables

- [ ] Live link to the application
- [ ] GitHub repository link
- [ ] PRD.md (this document)
- [ ] styles.md
- [ ] Demo credentials for testing
- [ ] Social media post showcasing the live product

---

## Demo Credentials

**Test organiser account:**  
Email: `temi@signet.app`  
Password: `Signet2026`

**Test event:** Lagos Tech Meetup Vol. 3  
**Attendees pre-loaded:** 5 (mix of General, VIP, Speaker)
