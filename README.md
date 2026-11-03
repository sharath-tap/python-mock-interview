# Data Analytics — Interview Question Bank

**Trainer reference copy.** 408 questions across 12 topics, each with a full answer underneath.

**Live:** https://sharath-tap.github.io/python-mock-interview/

| Topic | Questions |
|---|---:|
| SQL | 44 |
| **Write the Query** | **55** |
| Pandas | 36 |
| **Write the Code** | **30** |
| Python | 40 |
| NumPy | 20 |
| Statistics | 43 |
| Probability | 20 |
| Excel | 39 |
| Charts & BI | 26 |
| Scenario & Communication | 39 |
| HR & Behavioural | 16 |

Topic-segregated tabs, section jump links inside each. No batch filtering — ask whatever
is appropriate for the candidate in front of you.

## The two hands-on tabs

**Write the Query** and **Write the Code** are practical tasks, not definitions: a schema,
a sentence of plain English, and the candidate writes it.

Nothing in them is a result typed out by hand.

- Every SQL answer is executed against `seed.py`, an in-memory SQLite database loaded with
  deterministic literal data. MySQL function names (`CONCAT`, `DATE_FORMAT`, `REGEXP`,
  `SUBSTRING_INDEX`, `DATEDIFF`, `YEAR`) are registered on the connection, so the SQL printed
  for the candidate is the exact SQL that produced the result table below it.
- Every pandas/NumPy answer is run twice in two separate interpreters and the build fails if
  the two runs disagree — which catches anything order-dependent.
- A query that does not run, or whose result contradicts its `expect`, fails the build.

Both tabs use **the same dataset**, so almost every question can be asked twice: once in SQL,
then "now write that in pandas".

The sample data is built to carry the traps — a NULL salary, an employee with no department,
a department with no employees, a customer who never ordered, a cancelled order, a discounted
line, a product sold only on that cancelled order, and one employee who out-earns her manager.

## Build

```
cd "DA Curriculum/netlify-mock/build"
python3 build.py
```

One `qb_*.py` module per topic. The build validates tag balance, executes every query and
every snippet, and refuses to write the page if anything fails.

Per-question keys: `q`, `a`, optional `code`, `alt` (a second query shown *and* executed,
where `code` deliberately shows the naive version first), `sqlite` (a dialect translation
executed but not printed), `reslab`, `tag`, `setup`, `show`, `expect`.

> The answers are written for the trainer: ask the question, let the candidate answer, then
> use the text to probe. Several carry an explicit trainer note rather than a model answer.
