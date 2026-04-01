# Lab 1 — Grade Evaluator & Archiver
### by bidriss-hub

---

## What is this project?

This project reads a student's grades from a CSV file, validates them, calculates the final GPA, and tells you whether the student passed or failed. It also includes a shell script that automatically archives old grade files and keeps the workspace clean.

---

## Files in this project

- **grade-evaluator.py** — the main Python program
- **grades.csv** — the student grade data
- **organizer.sh** — a Bash script that archives grades.csv
- **README.md** — this file

---

## How to run the Python program

Make sure you have Python 3 installed. Open your terminal in the project folder and run:
```
python grade-evaluator.py
```

When asked, type the filename:
```
grades.csv
```

The program will show you:
- Whether all scores and weights are valid
- The student's GPA out of 5.0
- Whether the student PASSED or FAILED
- Which assignments are eligible for resubmission

---

## How to run the shell script

Open Git Bash in the project folder and run:
```
bash organizer.sh
```

The script will:
- Create an archive folder if it does not exist
- Rename grades.csv with a timestamp and move it to the archive folder
- Create a fresh empty grades.csv ready for new data
- Log everything it did in organizer.log

---

## grades.csv format

The file uses commas to separate values and must have these four columns:
```
assignment,group,score,weight
```

- **assignment** — name of the assignment
- **group** — either Formative or Summative
- **score** — a number between 0 and 100
- **weight** — how much the assignment counts toward the final grade

---

## Grading rules

- Formative assignments must add up to a weight of 60
- Summative assignments must add up to a weight of 40
- The student must score at least 50% in BOTH categories to pass
- GPA is calculated as: (Final Grade / 100) x 5.0

---

## Example output
```
--- Processing Grades ---

>> Grade Validation:
   All scores are valid (0-100).

>> Weight Validation:
   Total Weight:      100.0 (expected 100)
   Formative Weight:  60.0 (expected 60)
   Summative Weight:  40.0 (expected 40)
   All weights are valid.

>> Grade Calculation:
   Formative Score:   56.67%
   Summative Score:   65.00%
   Final Grade:       60.00%
   GPA:               3.00 / 5.0

>> Pass/Fail Status:
   Formative: PASSED (56.67%)
   Summative: PASSED (65.00%)

==================================================
   FINAL STATUS: PASSED

>> Resubmission Eligible Assignment(s):
   - Group Exercise (Score: 40.0%, Weight: 20.0)
   - Functions and Debugging Lab (Score: 45.0%, Weight: 20.0)
==================================================
```