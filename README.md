# Kansas City Chapter, NECA — Member App

A mobile-friendly React web app for the Kansas City Chapter, National Electrical Contractors Association.

---

## What's Inside

| Section | Description |
|---|---|
| **Home** | Mission statement, quick links, and IBEW union partner contact info |
| **Agreements** | CBA detail screens for LU 95, 124, 453, and 545 with wages, fringes, package totals, and embedded agreement documents |
| **Directory** | Searchable 2026 membership directory with contractor representative, address, email, and website details |
| **Meetings** | Full 2026 meeting schedule with KC Chapter and national/regional events |
| **Staff/Board** | Staff directory with photos and full Board of Directors |
| **Contact** | Chapter address, phone, email, and office hours |

---

## Tech Stack

- **React 18** (Create React App)
- No external UI libraries — all styling is inline
- Self-contained: all images and agreement pages are base64-embedded in `App.jsx`

---

## Getting Started (Local Development)

### Prerequisites
- Node.js v16 or higher ([nodejs.org](https://nodejs.org))
- npm (comes with Node.js)

### Install & Run

```bash
# 1. Unzip the project folder
unzip kc-neca-app.zip
cd kc-neca-app

# 2. Install dependencies
npm install

# 3. Start the development server
npm start
```

The app will open at **http://localhost:3000** in your browser.

---

## Building for Production

```bash
npm run build
```

This creates an optimized `build/` folder ready to deploy.

---

## Deployment Options

### Option 1 — Netlify (Recommended, Free)

1. Create a free account at [netlify.com](https://netlify.com)
2. Drag and drop the `build/` folder onto the Netlify dashboard
3. Netlify gives you a live URL instantly (e.g. `kc-neca.netlify.app`)
4. Optional: connect a custom domain like `app.kcneca.com`

A `netlify.toml` config file is already included for automatic builds.

### Option 2 — Vercel (Free)

1. Create a free account at [vercel.com](https://vercel.com)
2. Import the project folder or connect a GitHub repo
3. Vercel auto-detects Create React App and deploys automatically

### Option 3 — GitHub Pages (Free)

```bash
npm install --save-dev gh-pages
```

Add to `package.json`:
```json
"homepage": "https://yourusername.github.io/kc-neca-app",
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d build"
}
```

Then run:
```bash
npm run deploy
```

---

## Making It a Mobile App (Optional Future Step)

To publish to the Apple App Store and Google Play Store, the web app can be wrapped using:

- **Capacitor** ([capacitorjs.com](https://capacitorjs.com)) — most recommended
- **React Native Web** — larger refactor

This would require an Apple Developer account ($99/yr) and a Google Play Developer account ($25 one-time).

---

## Keeping Content Updated

All content is currently hardcoded in `src/App.jsx`. To make updates easier in the future, a developer can extract the data into separate JSON files:

| Data | Suggested file |
|---|---|
| CBA wage/fringe data | `src/data/cbas.js` |
| Membership directory | `src/data/members.js` |
| Meeting schedule | `src/data/meetings.js` |
| Staff & board | `src/data/staff.js` |
| Contact info | `src/data/contact.js` |

For fully dynamic content (admin can update without a developer), consider connecting to a headless CMS like **Contentful** or a simple **Google Sheet** via API.

---

## Project Structure

```
kc-neca-app/
├── public/
│   └── index.html          # HTML shell
├── src/
│   ├── App.jsx             # Main app component (all screens)
│   ├── index.js            # React entry point
│   └── index.css           # Global CSS reset
├── .gitignore
├── netlify.toml            # Netlify deployment config
├── package.json
└── README.md
```

---

## Contact

Kansas City Chapter, NECA  
800 E 101st Terrace, Suite 220  
Kansas City, MO 64131  
(816) 753-7444  
info@kcneca.com  
