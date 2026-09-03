# Lab 233 — Working with the Linux File System

**Module**: Linux
**Date**: 2026-09-03
**Objective**: Create a folder structure, then reorganize it using copy, move, and delete operations.

## What I did

Created the `CompanyA` folder structure with `mkdir` and `touch`, then verified the full tree with `ls -laR`.

![full-structure](../../screenshots/cloud/linux/lab233-full-structure.png)

Copied the `Finance` folder and its content into `HR` with `cp -r`.

![copy-finance](../../screenshots/cloud/linux/lab233-copy-finance-hr.png)

Attempted to remove the original `Finance` folder with `rmdir`, which failed since the folder still contained files.

![rmdir-fails](../../screenshots/cloud/linux/lab233-rmdir-not-empty.png)

Removed the files inside `Finance`, then successfully removed the empty folder with `rmdir`.

![finance-removed](../../screenshots/cloud/linux/lab233-finance-removed.png)

Moved the `Management` folder inside `HR` with `mv`.

![management-moved](../../screenshots/cloud/linux/lab233-management-moved.png)

Created an `Employees` folder inside `HR` and moved `Assessments.csv` and `TrialPeriod.csv` into it, then verified the final structure with `ls . Employees`.

![final-structure](../../screenshots/cloud/linux/lab233-final-structure.png)

## Key commands
```bash
mkdir CompanyA
cd CompanyA
mkdir Finance HR Management
touch HR/Assessments.csv HR/TrialPeriod.csv
touch Finance/Salary.csv Finance/ProfitAndLossStatements.csv
touch Management/Managers.csv Management/Schedule.csv
ls -laR

cp -r Finance HR
rmdir Finance
rm Finance/ProfitAndLossStatements.csv Finance/Salary.csv
rmdir Finance

mv Management HR
cd HR
mkdir Employees
mv Assessments.csv TrialPeriod.csv Employees
ls . Employees
```

## Issue encountered
The lab instructions contain a typo inconsistency: the initial folder structure lists the file as `Assessments.csvv` (double v), while a later example output in the same document shows it as `Assessments.cvs` (letters swapped). Neither spelling is correct, the actual valid name is `Assessments.csv`.

## Fix
Used the correct spelling `Assessments.csv` throughout, based on context rather than either flawed version in the instructions.
