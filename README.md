[README (2).md](https://github.com/user-attachments/files/27852047/README.2.md)
# ERP Sales Agent — AI-Powered Sales Automation Dashboard

A professional, fully static sales intelligence dashboard built for ERP solution providers. Designed for sales teams who need a clean, fast, and beautiful interface to manage leads, track outreach, and leverage AI-driven scoring — all from a single HTML file with zero dependencies.

---

## Live Demo

Deploy instantly via GitHub Pages — no build step, no server, no framework.

---

## Screenshots

> Dashboard with lead scoring, charts, activity feed, and typography system.

---

## Features

- **AI Lead Scoring** — Leads automatically scored 0–100 and categorized as Hot, Warm, Cold, or Not Fit
- **Industry Segmentation** — Manufacturing, Retail, Construction, Logistics, Healthcare
- **ERP Module Recommendations** — Context-aware module suggestions per lead
- **Live Activity Feed** — Real-time log of emails sent, opened, replied, and meetings booked
- **Donut & Bar Charts** — SVG-rendered, zero-dependency data visualizations
- **Type System Panel** — Full typographic scale reference built into the UI
- **Animated Stat Counters** — Smooth count-up animations on page load
- **Responsive Table** — Filterable leads table with status badges and pagination
- **Sidebar Navigation** — Full nav with badges for active pipeline counts
- **Dark Mode Ready** — Uses CSS variables that adapt automatically

---

## Tech Stack

| Layer | Choice |
|---|---|
| Framework | None — pure HTML/CSS/JS |
| Icons | Tabler Icons (outline, CDN) |
| Fonts | Google Fonts (Syne + DM Sans + JetBrains Mono) |
| Charts | Hand-crafted SVG |
| Animations | CSS transitions + vanilla JS |
| Dependencies | Zero npm packages |

---

## Getting Started

### Option 1 — GitHub Pages (recommended)

1. Fork or clone this repository
2. Make sure `index.html` is in the root of the repo
3. Go to **Settings → Pages**
4. Set source to `main` branch, root folder
5. Click **Save** — your dashboard will be live at:

```
https://your-username.github.io/your-repo-name
```

### Option 2 — Run locally

```bash
git clone https://github.com/your-username/erp-sales-agent.git
cd erp-sales-agent
open index.html
```

No `npm install`. No build step. Just open the file.

---

## File Structure

```
erp-sales-agent/
├── index.html       # Entire application — self-contained
└── README.md        # This file
```

Everything lives in `index.html` — styles, scripts, charts, and layout are all co-located for maximum portability.

---

## Customisation

### Change the sales rep name

Search for `Good morning, Steven` in `index.html` and replace with your name.

### Add or remove leads

Find the `<tbody>` tag inside the leads table section and add or remove `<tr>` rows following the existing pattern. Each row includes:

- Company name, logo initials, and URL
- Industry tag with color class (`blue`, `green`, `amber`, `red`, `gray`)
- ERP score and heat label
- Pain points and recommended modules
- Contact status badge
- Last activity timestamp

### Update stat card numbers

The animated counters are driven by `countUp(id, target, suffix, duration)` calls in the `<script>` block at the bottom. Change the `target` values to match your real pipeline numbers.

### Swap colors

All colors use CSS custom properties defined in `:root`. The main accent is `--accent-purple: #7c5cfc`. Change it once and every button, badge, and glow updates automatically.

### Add real data via API

Replace the static `<tbody>` rows with a `fetch()` call to your CRM or ERP API:

```js
fetch('https://your-api.com/leads')
  .then(res => res.json())
  .then(leads => {
    const tbody = document.querySelector('tbody');
    tbody.innerHTML = leads.map(lead => `
      <tr>
        <td>${lead.company}</td>
        <td>${lead.score}</td>
        ...
      </tr>
    `).join('');
  });
```

---

## Roadmap

- [ ] Connect to real CRM API (HubSpot, Pipedrive, Odoo)
- [ ] Add search and filter functionality
- [ ] Export leads to CSV
- [ ] Email template composer
- [ ] Meeting scheduler integration
- [ ] Mobile-responsive layout
- [ ] AI chat panel (Claude API)

---

## License

MIT — free to use, modify, and distribute.

---

## Author

Built by **Steven Bush**  
Powered by AI lead intelligence and zero npm packages.

---

*ERP Sales Agent — because good sales tools should be as sharp as your pitch.*
