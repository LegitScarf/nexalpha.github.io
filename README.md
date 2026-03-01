# NexAlpha — Intelligent Market Systems

A static company website built to showcase and provide access to two AI-powered financial intelligence products: **OptiTrade** and **BharatAlpha**. The site is designed with a trading terminal aesthetic and is deployed via GitHub Pages.

---

## Overview

NexAlpha is the product brand for a suite of multi-agent AI systems built for the Indian financial markets. This repository contains the static website (`index.html`) that serves as the public-facing landing page — communicating the company vision, presenting both products, and directing users to the live beta applications.

Both products are currently in beta. Next-generation versions are actively in development.

---

## Products

### OptiTrade — Multi-Agent Options Trading Assistant
A sophisticated AI system purpose-built for Nifty50 Futures & Options trading. Multiple specialized agents collaborate in real time to scan the market, analyze options chains, and surface actionable trade signals.

**Key capabilities:**
- Real-time Nifty50 options chain monitoring
- Multi-agent signal synthesis and validation
- Open interest and implied volatility analysis
- Risk-calibrated trade recommendations
- Live P&L tracking and Greeks dashboard

**Status:** Beta v0.1 — deployed on AWS (ap-south-1)

---

### BharatAlpha — Equity Research and Intelligence Platform
A deep equity research platform built specifically for the Indian market. Designed to give retail investors and serious traders access to the kind of fundamental and sector-level intelligence previously available only to institutional desks.

**Key capabilities:**
- BSE and NSE comprehensive coverage
- AI-driven fundamental and technical analysis
- Sector rotation and macro intelligence
- Company-specific research report generation
- Portfolio screening and risk assessment

**Status:** Beta v0.1 — deployed on AWS (ap-south-1)

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Vanilla JavaScript |
| Fonts | Orbitron, Share Tech Mono, Syne (Google Fonts) |
| Animations | CSS keyframes, SVG stroke-dashoffset, IntersectionObserver API |
| Hosting | GitHub Pages |
| Product Backend | AWS (Application Load Balancer, ap-south-1 region) |

---

## Repository Structure

```
nexalpha/
└── index.html        # Single-file static website (all CSS and JS inline)
└── README.md         # Project documentation
```

The entire site is contained within a single `index.html` file. No build tools, frameworks, or package managers are required.

---

## Local Development

No installation is needed. Simply open the file in a browser:

```bash
# Clone the repository
git clone https://github.com/your-username/your-username.github.io.git

# Open in browser
open index.html
```

Alternatively, use a local development server to avoid any browser CORS restrictions:

```bash
# Using Python
python -m http.server 5500

# Using Node.js (npx)
npx serve .
```

Then visit `http://localhost:5500` in your browser.

---

## Deployment

This site is deployed using **GitHub Pages**.

1. Push `index.html` to the `main` branch of a repository named `your-username.github.io`
2. Go to **Settings > Pages** in the repository
3. Set source to **Deploy from a branch**, branch `main`, folder `/ (root)`
4. The site will be live at `https://your-username.github.io`

Any subsequent changes to `index.html` will trigger an automatic redeploy within 1–2 minutes.

---

## Updating Product Links

The product URLs are referenced in four places in `index.html`. Search for the following values to locate them:

- `href="http://optitrade-alb-...` — appears in the OptiTrade product card and the CTA section
- `href="http://bharatalpha-alb-...` — appears in the BharatAlpha product card and the CTA section

Replace these with updated URLs whenever the products are migrated or redeployed.

> **Note:** The current product backends are served over HTTP. Since GitHub Pages enforces HTTPS, browsers may flag redirects to HTTP endpoints as mixed content. This is expected behavior for the beta phase. Once the products are served over HTTPS via a custom domain or AWS Certificate Manager, this will be resolved.

---

## Design Notes

The website is built around a **trading terminal aesthetic** with the following design decisions:

- **Color system:** Near-black background (`#030608`) with green (`#00ff88`) and amber (`#ffb800`) as primary accent colors — reflecting bullish/bearish market conventions
- **Typography:** Orbitron for display headings, Share Tech Mono for data and UI labels, Syne for body text
- **Effects:** CRT scanline overlay, animated grid background, SVG chart animations with stroke-dashoffset draw-on technique, and a custom cursor ring
- **Live ticker:** A scrolling marquee bar at the top simulates a real-time market data feed for Nifty50 constituent stocks
- **Scroll reveals:** Sections animate into view using the IntersectionObserver API with CSS transitions

---

## Roadmap

- [ ] Migrate product backends to HTTPS via custom domain and SSL certificate
- [ ] Replace static ticker data with a live market data API (e.g., NSE/BSE data feed or Yahoo Finance)
- [ ] Add individual product detail pages
- [ ] Launch V2 of OptiTrade with expanded instrument coverage and predictive capabilities
- [ ] Launch V2 of BharatAlpha with deeper agent collaboration and enhanced portfolio intelligence
- [ ] Add a contact / waitlist form for early access to V2

---

## Disclaimer

The content on this website is for informational purposes only and does not constitute financial advice. Trading in Futures and Options involves significant risk. Users should conduct their own research and consult a registered financial advisor before making investment decisions.

---

## License

All rights reserved. This codebase and the products it references are proprietary. Unauthorized reproduction or distribution is not permitted.

&copy; 2025 NexAlpha. All rights reserved.
