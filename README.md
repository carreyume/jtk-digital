# Portal Digital JTK — Jabatan Tenaga Kerja Semenanjung Malaysia

A front-end prototype for the digital labour services portal of Jabatan Tenaga Kerja Semenanjung Malaysia (JTK), built in accordance with the [Malaysia Government Design System (MYDS)](https://design.digital.gov.my/en).

**Live demo:** `https://yourusername.github.io/jtk-digital/`

---

## Overview

This prototype covers three interconnected pages representing a proposed centralised online labour services hub for JTK. The goal is to move complaint submission and labour court proceedings — currently handled largely offline or across fragmented channels — into a single, accessible, mobile-friendly digital platform.

---

## Pages

### `index.html` — Landing Page
The main entry point. A clean hub page that directs users to the appropriate service.

- Official GOV banner following MYDS standards
- Two service cards linking to e-Aduan and e-Mahkamah Buruh
- Contextual help note explaining which portal to use
- Fully responsive down to 375px

### `jtk-eaduan-portal.html` — e-Aduan JTK
Online complaint portal modelled after KPDN's e-Aduan system, purpose-built for JTK's mandate under the Employment Act 1955 and related legislation.

Key features:
- Complaint categories covering gig/platform workers, unpaid wages, OSH, discrimination, foreign workers, and contract disputes
- 4-step complaint wizard (Borang 8A equivalent) with file upload support
- Status tracking table with reference numbers and priority indicators
- FAQ accordion covering eligibility, process, and confidentiality
- Dedicated gig worker category reflecting the Employment (Amendment) Act 2022

### `jtk-emahkamah-buruh.html` — e-Mahkamah Buruh
Online Labour Court system replacing the current largely offline proceedings under Section 69 of the Employment Act 1955.

Key features:
- Authenticated dashboard with case summary and upcoming hearing alerts
- 5-step claim filing wizard (Form MB-8A) with RM 100,000 cap enforcement and fee calculator
- Virtual hearing room — simulated video-conference interface with live participant status and automated proceeding notes
- Case timeline from filing through service of notice, mediation, hearing, to award
- Online mediation module with settlement offer form and integrated hearing calendar
- Document management with verification status and deadline alerts
- Award display with itemised breakdown and PDF download

---

## Design System

All pages follow the [Malaysia Government Design System (MYDS)](https://design.digital.gov.my/en) published by Jabatan Digital Negara (JDN):

| Token | Value |
|---|---|
| Font | Plus Jakarta Sans |
| Blue 900 | `#042C53` |
| Blue 600 | `#185FA5` |
| Blue 50 | `#E6F1FB` |
| Gray 900 | `#2C2C2A` |
| Border radius (md) | `8px` |
| Border radius (lg) | `12px` |

Components used: GOV banner, phase banner, sticky header, cards, form wizard, status badges, task timeline, data table, FAQ accordion, alert callouts.

---

## File Structure

```
jtk-digital/
├── index.html                  # Landing page (portal hub)
├── jtk-eaduan-portal.html      # e-Aduan complaint portal
├── jtk-emahkamah-buruh.html    # e-Mahkamah Buruh (Labour Court)
└── README.md
```

---

## Deployment (GitHub Pages)

1. Push all files to a public GitHub repository
2. Go to **Settings → Pages**
3. Set source to **Deploy from branch → main → / (root)**
4. Save — the site will be live at `https://yourusername.github.io/repo-name/` within a minute

The landing page must be named `index.html` for GitHub Pages to serve it as the root URL. The other filenames can remain as-is since all internal links use relative paths.

---

## Scope & Limitations

This is a **front-end prototype only**. It does not include:

- Backend API or database integration
- Real authentication (MyDigitalID / Singpass-equivalent)
- Actual file upload processing
- Live video-conferencing (WebRTC)
- Payment gateway (FPX)
- Email/SMS notification system

These would need to be integrated by JTK's technology partner against JTK's existing Oracle or MyGovUC infrastructure, or a new stack procured through the standard government ICT procurement process.

---

## Relevant Legislation

| Act | Relevance |
|---|---|
| Employment Act 1955 (Act 265) | Primary labour law; Section 69 covers Labour Court claims |
| Employment (Amendment) Act 2022 | Gig and platform worker protections |
| Occupational Safety and Health Act 1994 | OSH complaints |
| Minimum Wages Order 2022 | RM 1,700 minimum wage enforcement |
| Industrial Relations Act 1967 | Unfair dismissal — refers to Industrial Court, not Labour Court |

---

## Contact

**Jabatan Tenaga Kerja Semenanjung Malaysia**
Presint 2, Putrajaya
Toll-free: 1-800-88-8064
Email: aduan@jtksm.gov.my

---

*Prototype developed as a concept submission. Not an official government product.*
