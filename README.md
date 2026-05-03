# resume-review — Claude Code Skill

A Claude Code skill that runs a structured PM resume review using a simulated panel of three reviewers: Recruiter, Hiring Manager, and CPO.

Built for product managers targeting Staff, Director, or Group PM roles — especially at AI-focused, B2B SaaS, or technical companies.

---

## What it does

When triggered, the skill:

1. **Gathers context** — target role, target companies, and any specific concerns
2. **Runs a three-lens panel review**, each reviewer citing specific bullets and sections:
   - **Recruiter**: formatting, ATS coverage, scannability, first-pass signal
   - **Hiring Manager**: outcomes vs. outputs, metrics quality, cross-functional evidence, strategic scope
   - **CPO**: career narrative, scope progression, executive presence, AI depth (where relevant)
3. **Produces a scorecard** with scores and top concerns per reviewer
4. **Prioritizes the top 5 edits** by impact, with specific guidance on what to fix and why
5. **Offers to rewrite** weak sections on the spot

The tone is direct. If something will get filtered before a human reads it, the skill says so.

---

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or desktop app)

---

## Installation

1. Clone or download this repo
2. Copy the `resume-review/` folder into your Claude Code skills directory:

**macOS / Linux:**
```bash
cp -r resume-review ~/.claude/skills/resume-review
```

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse resume-review "$env:USERPROFILE\.claude\skills\resume-review"
```

Your skills directory should look like:
```
~/.claude/skills/
  resume-review/
    SKILL.md
    evals/
      evals.json
```

3. Restart Claude Code (or reload the window in the desktop app)

---

## Usage

Just ask Claude to review your resume. Any of these will trigger it:

- "Review my resume — I'm targeting Staff PM roles at AI companies"
- "Can you critique my PM resume?"
- "Is my resume strong enough for a Director of Product role?"
- "Help me improve my resume for fintech companies"
- Or paste your resume content and ask for feedback

The skill will gather any missing context, then run the full panel review.

---

## Evals

The `evals/` folder contains three test cases with fictional resumes across different PM seniority levels and target roles. These are used for testing and iterating on the skill's behavior.

---

## Customization

The skill's default voice for rewrites is outcome-first, active, and lean — no filler verbs, real metrics, sounds like a person not a job description.

If you want to adjust the skill for a different role type (engineering, design, sales), edit `SKILL.md` and update the reviewer criteria to match that function's hiring lens.

---

## License

MIT
