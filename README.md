# Class Mark Book — Student Marks, Rank Lists & Report Cards

> A mobile-first class mark book for teachers — enter marks subject by subject, then get toppers, rank lists, grade charts, year-long trends and printable student report cards instantly. Works offline, with no sign-up. A learning project built with AI assistance.

**Tech:** HTML, CSS, JavaScript
**Tools:** GitHub Pages, localStorage
**AI Tools:** Claude

## About

A single-page **mark book and result-analysis app** for one class. A teacher sets up the class once, types marks for each exam, and the app works out totals, percentages, grades, ranks and pass/fail — then turns them into dashboards and printable reports.

- **Frontend:** one self-contained `index.html` (HTML + CSS + vanilla JS, no framework, no build step)
- **Storage:** the browser's `localStorage` — no server, no login, works offline
- **Backup:** download / restore a JSON file, or export everything to Excel (CSV)
- **Hosting:** GitHub Pages — `https://<your-username>.github.io/student-report/`
- **Built for:** a phone in a teacher's hand — large buttons, number keypad, bottom navigation

## What it shows

| Tab | What it does | Answers |
|-----|--------------|---------|
| 🏫 Setup | Class details, subjects, exam maximums, student list, backup tools | "How do I set up my class?" |
| ✏️ Marks | Enter marks for one exam and one subject at a time | "How do I record marks quickly?" |
| 📊 Exam | Class dashboard and rank list for a single exam | "How did the class do in this exam?" |
| 📈 All Exams | Year-wise trends, subject averages, most improved, overall ranking | "How is the class changing across the year?" |
| 🧑‍🎓 Student | One student's report card with progress chart and strengths | "How is this student doing?" |

## Getting started

1. Open the app and tap **▶ Try with a sample class** to see every screen filled with demo data, or continue below with your own class.
2. In **Setup**, fill in school, class & section, academic year and teacher name.
3. Check the **subject list** (one subject per line) and the **maximum marks** for each exam.
4. Add students — type roll number and name, tap **＋ Add student** (the next roll number is filled in for you), or paste a whole list from Excel.
5. Tap **💾 Save details**, then go to **✏️ Marks**.

> Don't rename a subject after marks are entered for it — marks are stored against the subject name.

## Setup

| Setting | Default | Notes |
|---------|---------|-------|
| Academic year | 2026-27 | Free text |
| Pass mark | 35 % | Applies to every subject in every exam |
| Subjects | Tamil, English, Maths, Science, Social Science | Edit freely, one per line; duplicates are removed |
| Exams | Mid Term (50), Quarterly (100), Half Yearly (100), Annual (100) | Only the maximum marks are editable |

### Adding students

- **One by one:** type roll number and name; ✕ removes a row.
- **Paste from Excel:** copy the Roll No. and Name columns and paste into the box. Lines such as `101 Priya` also work, and a header row is ignored.
- Roll numbers must be unique; the list is sorted by roll number automatically.
- Removing a student asks for confirmation and hides their marks.

## Entering marks

1. Choose the **exam**, then the **subject**.
2. Type each student's mark; **Next / Enter** moves to the next student.
3. Tap **AB** (or type `A` / `AB`) for an absent student.
4. Marks save automatically after every entry.

Helpful details:

- A mark above the exam maximum, below 0 or not a number is rejected with a red warning.
- Marks below the pass mark show in **red**, absentees in **orange**.
- A progress line shows *"x of y entered"*, and subject buttons get a **✔** once everyone's mark is in.
- Half marks (e.g. `42.5`) are accepted.
- At the last subject, a button jumps straight to the exam report.

## Reports

### Exam dashboard

- **Cards:** students appeared, class average, % who passed all subjects, highest score.
- **Missing marks warning:** lists subjects with marks still to enter.
- **🏆 Toppers:** top three with medals.
- **Subject-wise average:** bars with pass percentage, coloured by performance.
- **Grade distribution:** how many students fall in each grade.
- **Students who need help:** everyone below pass mark, with the subjects.
- **Rank list:** rank, roll, name, every subject, total, %, grade and Pass / Fail / Incomplete.

### All exams

- Class average and pass % for each exam, with a line chart across the year.
- Subject averages per exam as a chart and a colour-shaded table.
- **Most improved** and **marks dropping** lists (first exam vs latest exam).
- **Overall ranking** by average across all exams, with a trend arrow.

### Student report card

- Pick a student from the list or step with **◀ Previous / Next ▶**.
- Subject-wise marks for every exam, with total, percentage, grade, class rank and result.
- A progress chart against the class average, and strongest / weakest subject.
- Signature lines for class teacher and parent.

### Printing

Every report has **🖨️ Print / Save as PDF**. The print layout hides the navigation and shows a school heading (school, class, year, teacher) at the top.

## How results are calculated

| Item | Rule |
|------|------|
| Percentage | Total marks ÷ maximum marks for the subjects entered |
| Pass mark per subject | Exam maximum × pass % (rounded up) — e.g. 35 % of 50 → 18 |
| Result | **Fail** if any subject is below pass mark or absent; **Pass** if all entered subjects pass and all are entered; **Incomplete** if some subjects are still missing |
| Absent (AB) | Counted as a fail; left out of totals and averages |
| Rank | Highest percentage first; equal percentages share the same rank |
| Overall % | Average of the percentages across all exams with marks |
| Trend | Latest exam % minus first exam %; ▲ / ▼ shown for changes of 2 points or more |

### Grades

| Grade | Percentage |
|-------|-----------|
| A+ | 90 and above |
| A | 75 – 89 |
| B | 60 – 74 |
| C | 50 – 59 |
| D | 35 – 49 |
| E | Below 35 |

### Colour guide

Green = very good (75 %+) · Blue = good (60 %+) · Orange = average (above pass mark) · Red = needs attention.

## Your data & backup

All marks live **only in the browser on that device**. Clearing browser data or switching phones loses them, so back up after every exam.

- **⬇️ Download backup** — saves `MarkBook_Backup_<class>_<date>.json`; the Setup page shows when you last did it. Send it to yourself on WhatsApp or save to Google Drive.
- **⬆️ Restore backup** — loads a backup file after a confirmation; invalid files are rejected.
- **📊 Export all marks to Excel** — a CSV with every student, subject, total, % and result for each exam (opens correctly in Excel with Tamil or other Unicode names).
- **🗑️ Start a new class** — erases everything; asks you to type `DELETE` to confirm.

## Run it locally

1. Download the repo.
2. Double-click `index.html` — it opens in your browser. No server or install needed.

## Deploy on GitHub Pages

1. Push the repo to GitHub.
2. **Settings → Pages → Deploy from a branch → `main` / root**.
3. Open the Pages link on your phone and use **Add to Home Screen**.

## How AI Helped

- **Claude** — app layout and mobile-first UI, marks-entry flow, ranking and grading logic, charts, report-card and print layouts, backup / restore, debugging and documentation

## Project structure

```
student-report/
├── index.html    # the whole app (HTML + CSS + JS)
└── README.md     # this file
```

## Tech notes

- **No build step, no framework:** one HTML file; charts are drawn as inline SVG, so there are no chart libraries to load.
- **Single data object:** class details, subjects, exams, students and marks are saved together under the `classMarkBook_v1` key, and older or partial saves are merged with defaults on load.
- **Marks storage:** each mark is keyed by `exam | subject | student id`, so renaming a student or changing roll numbers never breaks their marks.
- **Teacher-friendly input:** numeric keypad on phones, Enter-to-advance, instant validation and a "Saved ✓" confirmation after each change.
- **Safe by default:** all names are HTML-escaped before display; destructive actions (remove student, restore, erase) ask for confirmation.
- **Print-ready:** a dedicated print stylesheet hides controls and keeps each card on one page.
- **Limits:** one class per device, data stays in the browser until backed up, and the pass mark and grade bands apply to the whole class.
