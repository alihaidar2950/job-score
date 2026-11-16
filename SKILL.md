---
name: job-score
description: Score job posts out of 100 against the user's CV, rank them, and say which to apply to now, which to apply to after tailoring the CV, and which to skip. Use when the user shares one or more job posts (text, files or links) with their CV and asks whether to apply, which job fits best, or how well they match.
---

# job-score

Read the user's CV and every job post they give you. Score each job out of 100 for **how well this
person matches it today**, rank them, and tell them where to spend their applications.

The score is about the fit between this CV and this post. It is never a verdict on the company or
on the person's worth.

## Inputs

- **CV:** a file path, pasted text, or a PDF. If none is given, ask for it. Never guess one.
- **Job posts:** files, pasted text or URLs (fetch them). One or many.

## Scoring (100 points)

| Part | Points | What earns them |
| --- | --- | --- |
| Must-have skills | 35 | Each required skill or tool the CV shows real evidence of. Split the 35 evenly across the post's must-haves. |
| Seniority | 25 | Years and level asked vs the CV. Full marks inside the range; minus 5 per missing year; 0 if the post wants a lead or senior and the CV is junior. |
| Proof | 10 | Projects, GitHub, shipped work or numbers on the CV that back the matching skills. |
| Nice-to-haves | 10 | Preferred or "a plus" skills the CV shows. |
| Day-to-day fit | 10 | Does the daily work described match what the CV has actually done? |
| Logistics | 10 | Location, office or remote, right to work, language, contract type. Unknown counts as half. |

Rules:

- **Evidence only.** A skill counts only if the CV shows it. Quote the job line and the CV line
  behind every point you give or take.
- **Never invent or inflate experience**, in the score or in the advice.
- **Say what you could not judge** (salary missing, visa unclear) instead of assuming.

## Verdict

- **75–100: apply now.**
- **55–74: apply after tailoring.** List the CV edits that would honestly raise the score.
- **0–54: skip.** Name the one or two gaps that sink it, so the user knows what to learn.

## Output

1. **Ranking table**, best first: `# | Job | Score | Verdict | Biggest gap`.
2. **Per job**, short: the score split by part, two lines of evidence for and against, and the
   verdict.
3. **Next move:** the best job to apply to today and up to three honest CV edits for it, written
   as the user would put them on their CV, only from experience the CV already shows.

Answer in the language the user writes in. Keep technical terms (React, REST, Git) in English.
