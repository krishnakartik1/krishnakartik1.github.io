# AGENTS.md - Portfolio Repo Notes

## Overview
Static HTML/CSS/JS portfolio site for Krishna Kartik Darsipudi.
Live at: https://krishnakartik1.github.io/

## Architecture
- `index.html` — single-page portfolio (all content here)
- `view/style.css` — custom styles
- `view/css/bootstrap.min.css` — Bootstrap framework
- `view/js/` — scripts (utils.js, bootstrap.min.js, script.js, jquery.csv.js)
- `view/images/` — profile photo and background gif
- `.github/workflows/preview.yml` — Netlify PR preview workflow

## CSS Classes (section backgrounds)
- `.background-white` — `#FFFFFF` — used for Profile, Skills sections
- `.background-light` — `#f5f5f5` — used for Projects section
- `.background-gray` — `#434242` — dark charcoal, used for Contact section ONLY (do NOT use for content sections — it renders very dark)

## Navbar Order
Profile > Experiences > Projects > Technical Skills > Contact

## Branch Protection
- `master` branch is protected — never push directly
- Always create a branch and open a PR
- Netlify preview auto-deploys on PR open/update (requires NETLIFY_AUTH_TOKEN + NETLIFY_SITE_ID secrets)

## Git Workflow
```bash
git checkout master && git pull
git checkout -b update/your-feature-name
# make changes
git add . && git commit -m "Description"
git push origin update/your-feature-name
# Then open PR via GitHub API or web UI
```

## GitHub API (create PR)
```bash
curl -s -X POST "https://api.github.com/repos/krishnakartik1/krishnakartik1.github.io/pulls" \
  -H "Authorization: token $PORTFOLIO_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"title": "...", "body": "...", "head": "branch-name", "base": "master"}'
```

## Token
PORTFOLIO_TOKEN stored in MEMORY.md. Needs scopes: Contents (R/W), Pull Requests (R/W), Workflows.

## Content Sections
1. Profile — About me + photo
2. Experiences — Education + Career (chronological, newest first)
3. Projects — REVAL first, then NYU/VIT projects
4. Technical Skills — AI/ML, Languages, Databases, Developer Tools, Infrastructure
5. Contact — LinkedIn, GitHub, email

## Key Content Notes
- Dell role: highlight LLM hackathon win, IRC microservices, OpenTelemetry
- REVAL: AWS 10K AIdeas top 1000 semi-finalist, counterfactual pair testing, LLM-as-judge
- Email: krishnakartik1@gmail.com (NOT the old reversed NYU email)
- Tagline: "AI Engineering | LLMs | Go & Python"
