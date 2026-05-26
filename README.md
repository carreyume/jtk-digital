# Portal Digital JTK — Jabatan Tenaga Kerja Semenanjung Malaysia

Front-end prototype for the digital labour services portal of Jabatan Tenaga Kerja Semenanjung Malaysia (JTK), built following the [Malaysia Government Design System (MYDS)](https://design.digital.gov.my/en).

**Live demo:** `https://carreyume.github.io/jtk-digital/`

---

## Pages

### `index.html` — Landing Page
Hub utama. Mengarahkan pengguna ke e-Aduan atau e-Mahkamah Buruh melalui halaman log masuk.

- Official GOV banner (MYDS standard)
- Two service cards with contextual descriptions
- Help note explaining which portal to use
- Fully responsive down to 375px
- Both cards route through `jtk-login.html` before entering the portal

### `jtk-login.html` — Log Masuk
LHDN-style split-screen login page. Shared by both portals, with destination routing via `?dest=aduan` or `?dest=mahkamah`.

- Left panel: navy branding with portal features
- Right panel: two authentication methods
  - **MyDigitalID** — one-click simulated redirect (no password required)
  - **No. Kad Pengenalan + Kata Laluan** — IC number input with show/hide password, validation, error/success alerts
- After successful login, automatically redirects to the correct portal
- Mobile responsive — left panel collapses on small screens

### `jtk-eaduan-portal.html` — e-Aduan JTK
Online complaint portal for JTK's administrative enforcement mandate.

- Authenticated header showing logged-in user + Log Keluar button
- 6 complaint category cards (Pekerja Gig, Gaji, OSH, Kontrak, Diskriminasi, Pekerja Asing)
- 4-step complaint wizard with file upload
- **Status tracking table** — all 5 "Lihat →" buttons open a full case detail modal with:
  - Complainant & employer information
  - Complaint category, legislation, amount claimed
  - Full case description
  - Step-by-step case timeline (with live/done/pending states)
  - Document list with verification status
- FAQ accordion

### `jtk-emahkamah-buruh.html` — e-Mahkamah Buruh
Digital Labour Court system replacing the current offline proceedings.

- Sidebar navigation with 8 sections
- **Dashboard** — live hearing alert, 4 stat cards, recent cases list, case timeline
- **Kes Saya** — full case table with "Lihat →" and "Award →" buttons opening detailed modals
- **Failkan Tuntutan** — 5-step filing wizard with pre-filled user data, RM 100k cap, fee summary
- **Perbicaraan Dalam Talian** — virtual hearing room with live participant status, agenda, auto-notes
- **Mediasi** — settlement offer form + June 2026 calendar with hearing/deadline markers
- **Dokumen** — document management with verification status and deadline alerts
- **Keputusan & Award** — itemised award breakdown with PDF download button
- **All "Lihat →" / "Award →" buttons** open full case detail modals with:
  - Full case parties, judge, registrar, legislation
  - Detailed claim description
  - Complete chronological timeline
  - Award breakdown (for resolved cases)
  - Document list

---

## User Flow

```
index.html (Landing)
    │
    ├─→ jtk-login.html?dest=aduan
    │       └─→ (after login) jtk-eaduan-portal.html
    │
    └─→ jtk-login.html?dest=mahkamah
            └─→ (after login) jtk-emahkamah-buruh.html
```

---

## File Structure

```
jtk-digital/
├── index.html                    # Landing page — renamed from jtk-portal-utama.html
├── jtk-login.html                # Shared login page (MyDigitalID + IC/Password)
├── jtk-eaduan-portal.html        # e-Aduan complaint portal
├── jtk-emahkamah-buruh.html      # e-Mahkamah Buruh (Labour Court)
└── README.md
```

> **Important:** Rename `jtk-portal-utama.html` → `index.html` before deploying to GitHub Pages.

---

## Design System

All pages follow [MYDS by Jabatan Digital Negara (JDN)](https://design.digital.gov.my/en):

| Token | Value |
|---|---|
| Font | Plus Jakarta Sans |
| Blue 900 (Navy) | `#042C53` |
| Blue 600 | `#185FA5` |
| Blue 50 | `#E6F1FB` |
| Gray 900 | `#2C2C2A` |
| Yellow (GOV stripe) | `#FFD600` |
| Border radius (md) | `8px` |
| Border radius (lg) | `12px` |

---

## Deployment (GitHub Pages)

1. Rename `jtk-portal-utama.html` → `index.html`
2. Push all 5 files to a **public** GitHub repository
3. Go to **Settings → Pages**
4. Source: **Deploy from branch → main → / (root)** → Save
5. Live at `https://yourusername.github.io/repo-name/` within ~60 seconds

---

## Sample Login Credentials (Demo)

Any IC number of 6+ digits and password of 4+ characters will pass the demo login. Examples:

| Method | Input |
|---|---|
| MyDigitalID | Click "Teruskan dengan MyDigitalID" |
| IC + Password | IC: `880512145678` / Password: `test1234` |

---

## Scope & Limitations

This is a **front-end prototype only**. Production deployment requires:

- Backend API (REST/GraphQL)
- Real MyDigitalID / MYSSO integration (JDN)
- FPX payment gateway (Paynet Malaysia)
- WebRTC for live video hearings
- PostgreSQL / Oracle DB integration with JTK's existing systems
- Email/SMS notification system (MAMPU infrastructure)
- PDPA 2010 compliance audit
- ISMS certification (ISO 27001)
- Penetration testing & OWASP compliance

---

## Relevant Legislation

| Act | Relevance |
|---|---|
| Employment Act 1955 (Act 265) | Primary labour law; Section 69 = Labour Court claims |
| Employment (Amendment) Act 2022 | Gig and platform worker protections |
| Occupational Safety and Health Act 1994 | OSH complaints |
| Minimum Wages Order 2022 | RM 1,700 minimum wage enforcement |
| Personal Data Protection Act 2010 | Data privacy for all user submissions |
| Industrial Relations Act 1967 | Unfair dismissal → Industrial Court (not Labour Court) |

---

## Contact

**Jabatan Tenaga Kerja Semenanjung Malaysia**  
Presint 2, Putrajaya  
Toll-free: `1-800-88-8064`  
Email: `aduan@jtksm.gov.my`

---

*Prototype developed as a concept submission. Not an official government product.*
