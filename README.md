# University Exam Review Skill

Evidence-grounded, instructor-aware university exam review for ChatGPT.

## Overview

This Skill helps university students build and update an exam review plan from course materials, classroom reports, teacher requirements, homework, student performance, and the study time remaining. It keeps the evidence behind each decision visible so students can check and revise the plan as they learn more.

## Why

- Course coverage is not the same as exam importance.
- Teacher intent is not an AI inference.
- Exam importance is not student mastery.
- The presence of homework does not establish student weakness.
- Required depth can change over time.
- Limited study time calls for prioritization.

## Core design

The Skill organizes a course into atomic **ExamPoints** and connects them to **Evidence Events** through scoped links. It tracks exam importance, mastery requirements, student mastery, and common errors as distinct information. Review priority combines these signals with the available time. Requirement updates can change what depth is needed, and time-aware planning adjusts what to review next.

## Installation

If your ChatGPT account has Skills access, upload [`skill/university-exam-review/SKILL.md`](skill/university-exam-review/SKILL.md), or package the `skill/university-exam-review/` directory as a ZIP and upload it. Skills availability depends on your ChatGPT account and environment.

## Basic usage

Start with course evidence and ask to inspect the proposed scope:

> Here are my course slides. First build an inspectable candidate scope. I have not told you what the instructor emphasizes yet.

Add instructor requirements when you have them:

> My instructor said this method is very important, but the full derivation is not required.

Then ask for a plan that fits your remaining time:

> I have three hours left before the exam. What should I review first?

## Validation

In controlled synthetic evaluation scenarios using real course-domain materials and synthetic instructor/student evidence, v0.2.3 scored **11/12 PASS** in Fluid Mechanics and **10/12 on two independent valid runs** in Mechatronics. No valid v0.2.3 run triggered a disqualifier. See [the evaluation summary](docs/EVALUATION.md).

## Known limitations

- Exact five-level exam-importance calibration is less stable than final review priority.
- Internal ExamPoint granularity may vary across runs.
- Validation currently covers two course domains.
- The Skill does not predict exams with certainty.
- Instructor evidence supplied by the student may itself be incomplete.

## Version

**v0.2.3 — Cross-course RC1**

Canonical `SKILL.md` SHA256: `C92571B66946CA6B58CDA5263D36A4479EEC5FC93CBC7C4B7D32DB68B846954A`
