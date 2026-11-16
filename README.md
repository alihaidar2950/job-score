# job-score

A Claude Code skill that scores job posts out of 100 against your CV, ranks them, and tells you
which to **apply to now**, which to **apply to after tailoring your CV**, and which to **skip**.

skill لـClaude Code بيعطي كل وظيفة علامة من 100 على الـCV تبعك، بيرتّبن، وبيقلّك: قدّم هلّق، عدّل الـCV
وقدّم، أو لا تضيّع وقتك.

## Install · التركيب

Copy this folder into your skills folder:

```bash
git clone https://github.com/alihaidar2950/job-score ~/.claude/skills/job-score
```

## Use · الاستعمال

In Claude Code, in a folder with your CV and the job posts (text files, PDFs or links):

```text
/job-score My CV is cv.pdf. Score every job in jobs/.
/job-score هيدا الـCV تبعي: cv.pdf. قيّم هالوظايف وقلّي على أيا وحدة قدّم.
```

## How it scores · كيف بيحسب العلامة

| Part | Points |
| --- | --- |
| Must-have skills | 35 |
| Seniority (years and level) | 25 |
| Proof (projects, GitHub, numbers) | 10 |
| Nice-to-haves | 10 |
| Day-to-day fit | 10 |
| Logistics (location, visa, language) | 10 |

Every point comes with the job line and the CV line behind it. It never invents experience, and it
says what it couldn't judge (salary, visa) instead of guessing.

**Scores move by a point or two between runs** (it's an AI reading text); the ranking and the
verdicts held across our test runs. Treat it as a second opinion, not a hiring decision.

MIT licence.
