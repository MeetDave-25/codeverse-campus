# 👥 CodeVerse Campus — User Stories

> **This document defines what each CodeVerse Campus user needs to accomplish and how the platform should respond.**

**Document Status:** Active
**Version:** 1.0
**Last Updated:** August 2026

---

# 1. What Is a User Story?

A user story describes a feature from the perspective of the person using it.

The standard format is:

> **As a [user], I want to [action], so that [reason/result].**

User stories help us build features based on actual user needs instead of simply adding features because they sound interesting.

---

# 2. User Types

## Primary Users

1. College Administrator
2. Faculty
3. Student

## Future Users

4. Placement Cell
5. Company / Recruiter

---

# 3. College Administrator User Stories

The College Administrator manages the college environment within CodeVerse Campus.

---

## ADMIN-001 — Login

**Story**

> As a College Administrator, I want to securely log into CodeVerse Campus so that I can access college management features.

### Expected Behaviour

* Admin enters credentials.
* System validates credentials.
* System identifies the user's role.
* Admin is redirected to the Admin Dashboard.
* Unauthorized users cannot access admin pages.

---

## ADMIN-002 — View Dashboard

> As a College Administrator, I want to see an overview of my college so that I can understand platform activity.

### Dashboard should show

* Total Students
* Total Faculty
* Departments
* Active Classes
* Active Coding Labs
* Platform Usage
* Recent Activity
* Basic Coding Statistics

---

## ADMIN-003 — Manage Departments

> As a College Administrator, I want to create and manage departments so that the college structure is represented correctly in the system.

### Actions

* Create department
* View department
* Edit department
* Activate/deactivate department

---

## ADMIN-004 — Manage Faculty

> As a College Administrator, I want to manage faculty accounts so that authorized faculty can use the platform.

### Actions

* Add faculty
* View faculty
* Edit faculty
* Assign department
* Activate/deactivate account
* Reset account access

---

## ADMIN-005 — Manage Students

> As a College Administrator, I want to manage student accounts so that students can access the appropriate classes and learning resources.

### Actions

* Add student
* Import students
* View students
* Edit student information
* Assign department
* Activate/deactivate account

---

## ADMIN-006 — Manage Classes

> As a College Administrator, I want to manage classes so that students and faculty are organized correctly.

### Actions

* Create class
* Assign faculty
* Add students
* Edit class
* Archive class

---

## ADMIN-007 — View College Analytics

> As a College Administrator, I want to view college-level analytics so that I can understand overall programming activity and student participation.

### Possible information

* Coding activity
* Lab participation
* Submission statistics
* Student engagement
* Class performance
* Department comparison

---

## ADMIN-008 — Generate Reports

> As a College Administrator, I want to generate reports so that I can evaluate college-level performance.

### Reports

* Student report
* Faculty report
* Class report
* Lab report
* Department report

---

# 4. Faculty User Stories

Faculty members use CodeVerse Campus to conduct programming education and understand student performance.

---

## FAC-001 — Login

> As a Faculty member, I want to securely log into the platform so that I can access my teaching dashboard.

---

## FAC-002 — View Faculty Dashboard

> As a Faculty member, I want to see today's teaching activities and student performance so that I can manage my classes efficiently.

### Dashboard should show

* Today's classes
* Active labs
* Upcoming assignments
* Student activity
* Recent submissions
* Performance overview
* AI insights

---

## FAC-003 — Manage Classes

> As a Faculty member, I want to manage my assigned classes so that I can organize students for programming activities.

### Actions

* View class
* View students
* Create class (if permitted by Admin)
* Add students
* Remove students
* View class performance

---

## FAC-004 — Create Coding Lab

> As a Faculty member, I want to create a coding lab so that students can solve programming problems during a class.

### Faculty can configure

* Lab title
* Description
* Date
* Start time
* Duration
* Questions
* Difficulty
* Programming languages
* Submission rules

---

## FAC-005 — Start Live Coding Lab

> As a Faculty member, I want to start a coding lab so that students can participate in a live programming session.

### System should

* Activate the lab
* Allow enrolled students to join
* Track participation
* Track submissions
* Show live activity

---

## FAC-006 — Monitor Live Classroom

> As a Faculty member, I want to monitor students during a live lab so that I can identify students who may need help.

### Faculty can see

* Students online
* Students offline
* Students currently coding
* Students who submitted
* Students who are stuck
* Hint requests
* Submission status

---

## FAC-007 — Create Assignment

> As a Faculty member, I want to create coding assignments so that students can practice concepts outside the live lab.

### Faculty can define

* Title
* Description
* Questions
* Deadline
* Difficulty
* Allowed languages
* Submission rules

---

## FAC-008 — Create Contest

> As a Faculty member, I want to create coding contests so that students can participate in competitive programming activities.

### Contest configuration

* Contest name
* Start time
* End time
* Problems
* Difficulty
* Participants
* Scoring rules

---

## FAC-009 — Generate Questions Using AI

> As a Faculty member, I want AI to generate coding questions so that I can create practice material faster.

### Faculty selects

* Topic
* Difficulty
* Programming language
* Number of questions

### AI generates

* Problem statement
* Constraints
* Examples
* Expected output
* Difficulty suggestion
* Test cases

### Important

AI-generated questions should be reviewed by the faculty before publishing.

---

## FAC-010 — Review Submissions

> As a Faculty member, I want to review student submissions so that I can understand how students approached problems.

### Faculty can view

* Submitted code
* Submission time
* Result
* Attempts
* Execution information
* AI feedback

---

## FAC-011 — View Student Analytics

> As a Faculty member, I want to view individual student analytics so that I can identify strengths and weaknesses.

### Analytics may include

* Problems solved
* Success rate
* Attempts
* Topics practiced
* Weak concepts
* Coding consistency
* Progress over time

---

## FAC-012 — View Class Analytics

> As a Faculty member, I want to view class-level analytics so that I can identify concepts that many students are struggling with.

### System can show

* Class success rate
* Problem difficulty
* Most common mistakes
* Weak topics
* Submission patterns
* Participation

---

## FAC-013 — Receive AI Classroom Insights

> As a Faculty member, I want AI to summarize classroom performance so that I can quickly identify important teaching issues.

### Example

```text
AI Classroom Insight

68% of students struggled with recursion.

42% required hints.

Most students failed on edge-case handling.

Recommendation:
Conduct a short revision on recursion and
base cases before moving to the next topic.
```

AI suggestions are advisory. Faculty makes the final teaching decision.

---

## FAC-014 — Send Feedback

> As a Faculty member, I want to provide feedback on student work so that students can understand how to improve.

---

## FAC-015 — Generate Reports

> As a Faculty member, I want to generate class and lab reports so that I can track and document student performance.

---

# 5. Student User Stories

Students are the primary learning users of CodeVerse Campus.

---

## STU-001 — Login

> As a Student, I want to securely log into CodeVerse Campus so that I can access my learning environment.

---

## STU-002 — View Student Dashboard

> As a Student, I want to see my learning progress in one place so that I know what I should focus on.

### Dashboard may show

* Today's tasks
* Coding streak
* XP
* Recent activity
* Recommended practice
* Learning progress
* Upcoming labs
* Skill progress
* Placement readiness

---

## STU-003 — Join Class

> As a Student, I want to join my class so that I can access the coding activities assigned by my faculty.

---

## STU-004 — Join Coding Lab

> As a Student, I want to join a live coding lab so that I can solve programming problems during class.

### System should

* Verify enrollment
* Mark participation
* Display lab information
* Display available problems
* Start coding environment

---

## STU-005 — Solve Coding Problem

> As a Student, I want to solve programming problems in an online editor so that I can practice coding without leaving the platform.

### Student can

* Select language
* Write code
* Run code
* Test code
* Submit code
* View output
* View errors

---

## STU-006 — Receive AI Hint

> As a Student, I want to request hints when I am stuck so that I can understand the problem without immediately receiving the complete solution.

### Hint levels

```text
Level 1 → Conceptual Hint
      ↓
Level 2 → Direction
      ↓
Level 3 → Logic Guidance
      ↓
Level 4 → Detailed Explanation
```

The goal is to encourage students to solve problems themselves.

---

## STU-007 — Receive AI Code Review

> As a Student, I want AI to review my code so that I can understand mistakes and improve my programming practices.

### AI may analyze

* Logic
* Bugs
* Edge cases
* Time complexity
* Space complexity
* Code quality
* Naming
* Possible improvements

---

## STU-008 — Ask AI Mentor

> As a Student, I want to ask the AI Mentor questions so that I can understand programming concepts.

The AI Mentor can help with:

* Concept explanations
* Examples
* Debugging guidance
* Practice questions
* Learning recommendations

---

## STU-009 — View Learning DNA

> As a Student, I want to see my Learning DNA so that I can understand my programming strengths and weaknesses.

### Possible dimensions

* Problem Solving
* Debugging
* Consistency
* Optimization
* Accuracy
* Topic Mastery

---

## STU-010 — View Skill Tree

> As a Student, I want to see a visual skill tree so that I understand which programming concepts I have mastered and which I should learn next.

Example:

```text
Programming
     ↓
Basics
     ↓
Loops
     ↓
Arrays
     ↓
Searching
     ↓
Sorting
     ↓
Trees
     ↓
Graphs
```

---

## STU-011 — View Learning Replay

> As a Student, I want to see how my performance has changed over time so that I can understand my improvement.

The system can compare:

* Previous attempts
* Current attempts
* Success rate
* Problem-solving time
* Topic mastery

---

## STU-012 — Participate in Contest

> As a Student, I want to participate in coding contests so that I can challenge myself and improve my problem-solving speed.

---

## STU-013 — Earn Achievements

> As a Student, I want to earn XP, badges, and streaks so that I remain motivated to practice consistently.

Examples:

* First Problem
* 7-Day Streak
* 50 Problems Solved
* Debugging Master
* Contest Participant
* Topic Master

---

## STU-014 — View Leaderboard

> As a Student, I want to view a leaderboard so that I can compare my coding activity and achievements with classmates.

The leaderboard should encourage healthy competition and should not become the only measure of learning.

---

## STU-015 — Build Coding Portfolio

> As a Student, I want the platform to maintain my coding achievements and skills so that I can demonstrate my progress.

Portfolio can contain:

* Problems solved
* Skills
* Achievements
* Contest history
* Certificates
* Projects
* Coding statistics

---

## STU-016 — View Placement Readiness

> As a Student, I want to see my placement readiness so that I understand which technical areas I should improve.

Possible factors:

* Coding consistency
* DSA progress
* Problem-solving
* Core programming concepts
* Projects
* Skill development

The placement score should be presented as an indicator, not as a guarantee of placement.

---

# 6. Future User Stories — Placement Cell

These stories are planned for future versions.

---

## PLC-001 — View Placement Dashboard

> As a Placement Cell member, I want to see student placement readiness so that I can identify students who need preparation support.

---

## PLC-002 — Filter Students

> As a Placement Cell member, I want to filter students by technical skills and readiness so that I can identify suitable candidates for opportunities.

---

## PLC-003 — Track Placement Activity

> As a Placement Cell member, I want to track recruitment activity so that I can maintain placement records.

---

# 7. Future User Stories — Company / Recruiter

These stories are planned for future versions.

---

## COM-001 — Create Company Profile

> As a recruiter, I want to create a company profile so that students and the college can view our organization.

---

## COM-002 — Create Coding Assessment

> As a recruiter, I want to create a coding assessment so that I can evaluate candidates.

---

## COM-003 — View Candidate Portfolio

> As a recruiter, I want to view student coding portfolios so that I can identify suitable candidates.

---

## COM-004 — Shortlist Candidates

> As a recruiter, I want to shortlist candidates based on assessment and profile information so that I can continue the hiring process.

---

# 8. Cross-User Workflows

These workflows connect multiple users.

---

## Workflow 1 — Coding Lab

```text
Faculty
   ↓
Creates Coding Lab
   ↓
Student
   ↓
Joins Lab
   ↓
Solves Problem
   ↓
Code Execution
   ↓
AI Analysis
   ↓
Student Feedback
   ↓
Learning Data
   ↓
Faculty Analytics
```

---

## Workflow 2 — Assignment

```text
Faculty
   ↓
Creates Assignment
   ↓
Student
   ↓
Views Assignment
   ↓
Solves Problem
   ↓
Submits
   ↓
AI Review
   ↓
Faculty Review
   ↓
Student Progress
```

---

## Workflow 3 — AI Learning

```text
Student Attempt
       ↓
AI Analysis
       ↓
Mistake Detection
       ↓
Hint / Explanation
       ↓
Student Retry
       ↓
Improved Attempt
       ↓
Learning Data Update
```

---

## Workflow 4 — Contest

```text
Faculty
   ↓
Creates Contest
   ↓
Students Join
   ↓
Solve Problems
   ↓
Submissions
   ↓
Scoring
   ↓
Leaderboard
   ↓
Achievements
```

---

# 9. User Permissions Summary

| Action                 |     Admin     |      Faculty      | Student |
| ---------------------- | :-----------: | :---------------: | :-----: |
| Manage Departments     |       ✅       |         ❌         |    ❌    |
| Manage Faculty         |       ✅       |         ❌         |    ❌    |
| Manage Students        |       ✅       |      Limited      |    ❌    |
| Manage Classes         |       ✅       |  Assigned Classes |   Join  |
| Create Coding Lab      |       ❌       |         ✅         |    ❌    |
| Join Coding Lab        |       ❌       |      Monitor      |    ✅    |
| Create Assignment      |       ❌       |         ✅         |    ❌    |
| Solve Problems         |       ❌       |      Optional     |    ✅    |
| Submit Code            |       ❌       |         ❌         |    ✅    |
| Request AI Hint        |       ❌       |         ❌         |    ✅    |
| AI Code Review         |       ❌       |       Review      |    ✅    |
| View Student Analytics |    College    | Assigned Students |   Own   |
| View Class Analytics   |    College    |    Own Classes    |    ❌    |
| AI Classroom Insights  | College-level |         ✅         |    ❌    |
| Generate AI Questions  |       ❌       |         ✅         |    ❌    |
| Create Contest         |       ❌       |         ✅         |    ❌    |
| Participate in Contest |       ❌       |      Optional     |    ✅    |
| View Leaderboard       |    College    |       Class       |    ✅    |
| Manage Platform        |       ✅       |         ❌         |    ❌    |

**Note:** Exact permissions will be finalized in `PRODUCT_REQUIREMENTS.md` and implemented through role-based access control.

---

# 10. User Story Priority

Each user story will eventually receive a priority:

### P0 — Critical

Required for the core MVP.

### P1 — Important

Should be implemented if time permits.

### P2 — Enhancement

Useful but not required for the MVP.

### P3 — Future

Not part of the current academic MVP.

---

# 11. Acceptance Criteria

A user story is considered complete only when:

* The intended user can perform the action.
* The system produces the expected result.
* Appropriate validation exists.
* Unauthorized users cannot perform the action.
* Errors are handled properly.
* The UI communicates success or failure clearly.
* The feature works with the project's existing architecture.
* Relevant documentation is updated.

---

# 12. Important Product Rule

A user story describes **what the user needs**.

It should not dictate the technical implementation.

For example:

> "Student wants AI Code Review."

This document defines the user's need.

The technical implementation belongs in:

* `PRODUCT_REQUIREMENTS.md`
* `API_CONTRACT.md`
* `DATABASE.md`
* `AI_CONTEXT.md`

---

# 13. Future Expansion

Additional user stories may be added as the product evolves.

However, adding a user story does not automatically mean the feature belongs in the MVP.

Every new story must be evaluated against the Project Bible and the current project roadmap.

---

# Final Principle

> **Build for the user's problem, not for the feature list.**

Every major CodeVerse Campus feature should ultimately answer one question:

**"Who does this help, and what problem does it solve?"**
