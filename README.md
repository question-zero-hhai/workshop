# Q0 Workshop — HHAI 2026

> **Question Zero: Should We Build This AI System at All?**  
> Workshop co-located with HHAI 2026 · July 6–7

---

## Quick Setup

### 1. Create the GitHub repo

```bash
gh repo create q0-workshop-2026 --public
cd q0-workshop-2026
```

Or create via the GitHub UI, then clone it.

### 2. Add the files

```
q0-workshop-2026/
├── index.html              ← workshop website
├── parse_cfp.py            ← LaTeX → JSON parser
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml      ← GitHub Pages auto-deploy
```

### 3. Enable GitHub Pages

In your repo → **Settings → Pages**:
- Source: **GitHub Actions**

Push to `main` — the site deploys automatically.

---

## Updating the site

### Fill in the blanks

Search `index.html` for these placeholders and replace them:

| Placeholder | Replace with |
|---|---|
| `[insert URL]` | Your GitHub Pages URL (e.g. `https://youorg.github.io/q0-workshop-2026`) |
| `[insert email]` | Workshop contact email |
| `Name TBC` (×4) | Organizer names and affiliations |
| `workshop@example.com` | Submission email or link |

### Parse the LaTeX for structured data

```bash
python parse_cfp.py cfp.tex > data/cfp.json
```

This gives you a clean JSON representation of the CfP
you can use to drive future templating or a JS-powered site.

### Re-deploy

Just push to `main`:

```bash
git add .
git commit -m "update organizers"
git push
```

GitHub Actions builds and deploys automatically (~30 seconds).

---

## Structure

| File | Purpose |
|---|---|
| `index.html` | Single-file static site (no build step) |
| `parse_cfp.py` | Parses a `.tex` CfP into structured JSON |
| `.github/workflows/deploy.yml` | Auto-deploys to GitHub Pages on push to `main` |

---

## Sections

1. **Overview** — What is Q0?
2. **Topics of Interest** — 10 research themes
3. **Workshop Format** — Day 1 (academic) + Day 2 (policy)
4. **Submissions** — Guidelines + important dates
5. **Organizing Committee** — TBC placeholders
6. **Why This Workshop** — Motivation + preliminary material link
