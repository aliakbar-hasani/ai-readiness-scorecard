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

| Area        | Share |
|-------------|-------|
| `customer`  | 30%   |
| `marketing` | 30%   |
| `admin`     | 40%   |
| `finance`   | 25%   |
| `documents` | 40%   |

These shares are starting assumptions, not measured results. Keep them in one
config file so they are easy to change, and state the share on the results page
next to each figure.

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

## Results page

- A headline naming the top area and its yearly figure.
- All five areas in ranked order. Each shows hours per week, the yearly figure,
  the formula with their numbers filled in, and one concrete example of what AI
  would do there, worded for their Q1 business type.
- A total across all areas, labelled as a rough estimate.
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
