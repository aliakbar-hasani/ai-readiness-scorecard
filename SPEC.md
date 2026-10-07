# AI Readiness Scorecard: spec for version 1

## What this is

A two-minute web assessment for business owners. They answer 10 multiple-choice
questions and get a ranked list of where AI could save them the most time and
money, with a rough yearly figure and the math shown.

## Who it is for

Any business owner, in any industry. The questions are about business functions
every company has, so one question set fits everyone. Business type and team
size are used only to tailor the wording and examples in the results.

## Why someone takes it

They keep hearing they should be using AI and don't know where to start. This
gives them a specific starting point and a dollar figure in two minutes, with no
sales call and no sign-up.

## The flow

1. Landing screen: one headline, one line of explanation, a Start button.
2. Ten questions, one per screen.
3. Results page.

Question screens:

- One question per screen with large tappable answers.
- Tapping an answer moves to the next question automatically.
- A progress bar at the top and a Back button.
- No typing anywhere in the question flow.
- Designed for a phone first. Most people will open it from a text or a link.

## Proof points

The statistics below give the landing page and the questions their credibility.
Show each one with its source name, and link the source from a Sources section
at the foot of the landing page and the results page. Never word a statistic as
a promise of what the visitor will get.

Landing page, as a row of three under the Start button:

| Statistic                                                         | Source label                                      |
|-------------------------------------------------------------------|---------------------------------------------------|
| 55% of small businesses now use AI, up from 39% a year earlier    | Thryv survey of 540 small businesses, 2025        |
| 58% of small businesses using AI save more than 20 hours a month  | Thryv survey of 540 small businesses, 2025        |
| Professionals finished writing tasks 40% faster with AI           | Noy and Zhang, Science, 2023                      |

Thryv source:
https://www.thryv.com/news/ai-adoption-among-small-businesses-surges-41-in-2025-creating-new-era-of-growth-and-efficiency/
Thryv sells software to small businesses and the figures are self-reported, so
always show the source label beside them.

Question screens Q3–Q7, as one line of small text under the answers:

| #  | Line                                                                     | Source label                         |
|----|--------------------------------------------------------------------------|--------------------------------------|
| Q3 | Support agents with an AI assistant resolved 15% more issues per hour.   | Quarterly Journal of Economics, 2025 |
| Q4 | Consultants using AI finished marketing tasks 25% faster.                | Harvard and BCG study, 2023          |
| Q5 | Workers using an AI assistant spent 25% less time on email.              | Microsoft Research, 2025             |
| Q6 | Accounting firms using AI closed their month 7.5 days sooner.            | Stanford and MIT study, 2025         |
| Q7 | Professionals wrote documents 40% faster with AI.                        | Science, 2023                        |

Full citations and links for these five are under "Evidence for the shares".

## The questions

### About the business

**Q1. What kind of business do you run?**
Services / Retail or online store / Trades / Health and wellness / Food and
hospitality / Other

**Q2. How many people work in it?**
Just me / 2–10 / 11–50 / 51+

### Where the time goes

Each of Q3–Q7 asks "How many hours a week does your team spend on this?" and
uses the same four answers:

| Answer        | Hours used in scoring |
|---------------|-----------------------|
| Almost none   | 0.5                   |
| A few hours   | 3                     |
| 5–10 hours    | 7.5                   |
| 10+ hours     | 12                    |

| #  | Area key    | Question text                                                              |
|----|-------------|----------------------------------------------------------------------------|
| Q3 | `customer`  | Answering customer questions by email, phone, chat or DMs                  |
| Q4 | `marketing` | Marketing and following up with leads, such as posts, emails and quotes    |
| Q5 | `admin`     | Scheduling, data entry and copying information between tools               |
| Q6 | `finance`   | Invoicing, bookkeeping and pulling reports                                 |
| Q7 | `documents` | Writing documents you make over and over, such as proposals and contracts  |

When Q2 is "Just me", say "you" in place of "your team" throughout.

### To make the results personal

**Q8. Which of those five frustrates you most?** Pick one of the five areas.

**Q9. Roughly what does an hour of your team's time cost?**
$25 / $50 / $100 / $150+ / Not sure. Score "$150+" as 150 and "Not sure" as 50.

**Q10. How much are you using AI today?**
Not at all / Tried it a few times / Use it weekly / It's built into our tools

## Scoring

For each of the five areas:

```
yearly savings = hours per week × share AI can take on × hourly cost × 48 weeks
```

Share AI can take on, per area:

| Area        | Share | Based on                                             |
|-------------|-------|------------------------------------------------------|
| `customer`  | 13%   | Brynjolfsson, Li and Raymond (2025)                  |
| `marketing` | 25%   | Dell'Acqua et al. (2023)                             |
| `admin`     | 25%   | Dillon, Jaffe, Immorlica and Stanton (2025)          |
| `finance`   | 8.5%  | Choi and Xie (2025)                                  |
| `documents` | 40%   | Noy and Zhang (2023)                                 |

Each share comes from one published study, listed under "Evidence for the
shares" below. Keep the shares and their source labels in one config file so
they are easy to change, and show the share and its source next to each figure
on the results page.

Ranking:

1. Sort the five areas by yearly savings, highest first.
2. If the Q8 pick is not first and its savings is within 25% of the top area,
   move it to first.
3. Break any remaining ties with the Q8 pick, then question order.

Q10 sets the tone of the advice:

- "Not at all" or "Tried it a few times": start with one small, low-risk change
  in the top area.
- "Use it weekly": connect AI to the tools already used in the top area.
- "It's built into our tools": look at automating a whole workflow end to end.

## Evidence for the shares

Each share is taken from one study of people doing similar work with and
without AI. None of the studies was run on small businesses specifically, so the
results are estimates of what is possible, not predictions.

| Area        | Share | What the study found                                                                                                  | Source |
|-------------|-------|-----------------------------------------------------------------------------------------------------------------------|--------|
| `customer`  | 13%   | 5,172 support agents with an AI assistant resolved 15% more issues per hour, which is about 13% less time per issue.   | Brynjolfsson, Li and Raymond, "Generative AI at Work", Quarterly Journal of Economics, 2025. https://arxiv.org/abs/2304.11771 |
| `marketing` | 25%   | 758 consultants using GPT-4 on product and marketing tasks finished 25.1% faster, with higher-rated work.              | Dell'Acqua et al., "Navigating the Jagged Technological Frontier", working paper, 2023. https://www.oneusefulthing.org/p/centaurs-and-cyborgs-on-the-jagged |
| `admin`     | 25%   | In a six-month randomized trial with 6,000 workers, those who used an AI assistant spent 25% less time on email.       | Dillon, Jaffe, Immorlica and Stanton, "Shifting Work Patterns with Generative AI", 2025. https://www.microsoft.com/en-us/research/publication/shifting-work-patterns-with-generative-ai/ |
| `finance`   | 8.5%  | Across 79 small and midsize firms, accountants using AI moved about 8.5% of their time off routine data entry and closed the month 7.5 days sooner. | Choi and Xie, "Human and AI in Accounting: Early Evidence from the Field", 2025. https://mitsloan.mit.edu/ideas-made-to-matter/how-generative-ai-can-make-accountants-more-productive |
| `documents` | 40%   | 453 professionals given ChatGPT finished 20 to 30 minute writing tasks 40% faster, with quality rated 18% higher.      | Noy and Zhang, "Experimental evidence on the productivity effects of generative artificial intelligence", Science, 2023. https://economics.mit.edu/news/study-finds-chatgpt-boosts-worker-productivity-some-writing-tasks |

Known weak spots:

- `admin` is the loosest match. The study measured email, while the question
  asks about scheduling, data entry and copying information between tools.
- `finance` uses time moved away from data entry as a stand-in for time saved.
- `marketing` comes from a working paper that had not been peer reviewed when
  it was released. The same study found AI made results worse on a task it was
  not suited to.

Reality check to show on the results page, in one line: these shares apply to
specific tasks, and savings across a whole job are smaller. US workers who use
generative AI report saving about 5.4% of their work hours (Bick, Blandin and
Deming, Federal Reserve Bank of St. Louis,
https://www.stlouisfed.org/open-vault/2025/oct/generative-ai-productivity-future-work),
and a Danish study of about 25,000 workers found 2.8% (Humlum and Vestergaard,
"Large Language Models, Small Labor Market Effects", 2025,
https://bfi.uchicago.edu/wp-content/uploads/2025/04/BFI_WP_2025-56-3.pdf).

## Results page

- A headline naming the top area and its yearly figure.
- All five areas in ranked order. Each shows hours per week, the yearly figure,
  the formula with their numbers filled in, and one concrete example of what AI
  would do there, worded for their Q1 business type.
- A total across all areas, labelled as a rough estimate.
- The one-line reality check from "Evidence for the shares", and a Sources
  section listing the study behind each share with its link.
- One short paragraph of next-step advice based on Q10.
- One call to action: a button to book a call. The URL lives in the config file.
- A Start over link.

Round every dollar figure to the nearest $100, and call figures estimates
everywhere they appear.

## Build constraints

- A static site with no backend, no database and no AI or API calls.
- No secrets. Nothing in version 1 needs an API key.
- Vite, React and TypeScript.
- Questions, answer values, shares and example text live in one config file.
- Scoring is a pure function with unit tests that cover the ranking rules above.
- Answers are held in memory only and are never sent anywhere.
- Deployable to a static host such as Vercel or Netlify.

## Not in version 1

- Email capture and any email service.
- Accounts, saved results or shareable result links.
- AI-generated or free-text content.
- Analytics.

## Done when

- All 10 questions can be answered on a phone in about two minutes.
- The results page ranks the five areas by the rules above, and the unit tests
  pass.
- Refreshing the page starts over and nothing is stored.
- The site builds and runs from a clean clone with the commands in the README.
