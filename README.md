# AI Talent Acquisition Copilot

**Illustrative Prototype – Developed as a practical demonstration of AI-enabled recruitment capabilities.**
Author: Arslan Khan · aPHRi™ · CHRP® — designed by Arslan, built with Claude as a coding partner.

A single-file browser app that shows how a recruiter can use AI to move from a hiring requirement to a structured, reviewable hiring process — while every decision stays with people.

```
Hiring requirement → AI role analysis → Sourcing strategy → Screening support
→ Interview kit → Human evaluation & decision → Pipeline tracker → Metrics dashboard
```

## What it is — and what it is not

| Level | Status | What it means |
|---|---|---|
| **Working prototype** | ✅ This file | Runs in any modern browser. *Sample mode* replays pre-generated outputs; *Live mode* sends prompts to Claude through the Anthropic API with your own key. |
| **Prompt-based workflow** | ✅ Included | Every step has **Copy prompt** — the same prompts work in Claude or ChatGPT chat with no integration. |
| **Production automation** | ❌ Not built | No ATS (e.g., Ashby), LinkedIn, GitHub or Hugging Face integration. No scraping. A production version would need approved APIs, access control, retention rules, a privacy review and bias monitoring. |

All job briefs, candidates and dashboard data are **synthetic**.

## How to use it

1. Open `index.html` in Chrome, Edge, Firefox or Safari (double-click, or host it — see below).
2. **Step 1 – Hiring requirement:** keep the sample brief or paste your own. Click **Analyse role with AI**.
3. **Step 2 – Role analysis:** edit any competency, type or weight directly in the table. Enter a reviewer name and click **Approve** *(Human checkpoint 1 — later steps are locked until this is approved).*
4. **Step 3 – Sourcing:** generate Boolean / GitHub / X-ray strings, a channel plan and an outreach template. Run searches yourself on each platform. *(Checkpoint 2 — nothing is sent automatically.)*
5. **Step 4 – Screening support:** pick a synthetic candidate. Toggle **Redact personal data** to see exactly what is sent to the AI. Click **Extract evidence** — the AI quotes CV evidence per competency or says “No evidence found”, and suggests questions. Mark each line **Verified / Incorrect** *(Checkpoint 3).* The AI gives **no score, rank or recommendation**.
6. **Step 5 – Interview kit:** competency-based questions, follow-ups, strong-answer signals and red flags.
7. **Step 6 – Human evaluation:** interviewers rate 1–5; the weighted score is calculated; a person records **Advance / Hold / Decline** with a job-related rationale *(Checkpoint 4 — no AI in this step).*
8. **Step 7 – Pipeline tracker:** move candidates between stages; every move is logged.
9. **Step 8 – Dashboard:** funnel, source of hire, withdrawal rate by stage — calculated live from a synthetic dataset — plus an AI-drafted weekly update that the recruiter checks before sending.
10. **Audit log & prompts:** every AI call and human action with timestamps; export as JSON. View every system and user prompt.

### Live mode (optional)
Click **Live mode (Claude API)**, paste an Anthropic API key and keep the default model or type another available model name. The key is held only in the page’s memory (not stored) and requests go directly from the browser to `api.anthropic.com`. Use a key with a spending limit and send only synthetic or consented, redacted data.
*Note: live mode was built against the public Messages API but was not run end-to-end in the build environment (no network access there). Test it once with your key before a demo — sample mode always works offline.*

## Sample inputs and outputs
- **Input:** the fictional brief “Associate Machine Learning Engineer — Generative Imaging” (Step 1).
- **Output (Step 2):** 6 competencies with types and weights, ideal profile, “not required” list (e.g., degree), questions for the hiring manager.
- **Input (Step 4):** synthetic CV C-104, redacted: names, email, phone and links replaced.
- **Output (Step 4):** evidence table — e.g., *Inference optimisation → “Cut GPU cost by moving to fp16 and dynamic batching”*; *Model evaluation → “before/after quality reviews” — unclear whether quantitative evaluation is used*; plus 3 questions for the recruiter call.
- Screenshots of every step are in `screenshots/`.

## Responsible-AI design
- AI drafts; people approve, edit and decide — enforced by checkpoints.
- The screening prompt forbids scores, rankings, recommendations and any reference to protected characteristics or school/employer prestige; it must quote evidence.
- Personal data is redacted before any AI call.
- No scraping; no platform integrations.
- Limitations: AI can misread or invent details (hence line-by-line verification); keyword evidence under-represents non-traditional candidates; it cannot judge technical depth — engineers do.

## Publish it (get a shareable link)
- **Netlify Drop:** go to app.netlify.com/drop and drag the `copilot` folder in → you get a public URL.
- **GitHub Pages:** create a public repo, upload `index.html` (and `screenshots/`), then Settings → Pages → Deploy from branch → `main` / root.
- Record a 2–3 minute Loom using `AI_Copilot_Demo_Script.docx`.

## Files
- `index.html` — the prototype (no dependencies, no build step)
- `README.md` — this file
- `screenshots/` — storyboard images of each step
