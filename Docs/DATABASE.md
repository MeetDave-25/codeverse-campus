# 🗄️ CodeVerse Campus — Database Documentation

> The official database architecture and data model for CodeVerse Campus.

**Version:** 1.0  
**Status:** Active  
**Last Updated:** August 2026

---

# 1. Purpose

This document defines the official database structure for CodeVerse Campus.

It describes:

- Entities
- Tables
- Fields
- Relationships
- Constraints
- Indexes
- Data ownership
- Authentication-related data
- Academic structure
- Coding data
- Learning analytics
- AI-related data
- Gamification data

The database must follow this document.

---

# 2. Database Source of Truth

`DATABASE.md` is the primary documentation source for the database architecture.

Before creating or modifying a database table, model, migration, or relationship, developers and AI tools must check this document.

The correct workflow is:

Requirement
↓
Check DATABASE.md
↓
Check Existing Schema
↓
Determine Required Change
↓
Update DATABASE.md
↓
Create Migration / Schema Change
↓
Implement
↓
Test

---

# 3. Database Philosophy

The CodeVerse Campus database should be:

- Simple
- Consistent
- Secure
- Scalable
- Maintainable
- Normalized where appropriate
- Easy for the team to understand

Avoid unnecessary complexity.

The database should support the current college-level MVP without designing an unnecessarily complicated enterprise architecture.

---

# 4. Core Architecture

The platform can be understood through the following data domains:

```text
Identity
   ↓
College
   ↓
Academic Structure
   ↓
Learning
   ↓
Coding
   ↓
Assessment
   ↓
Analytics
   ↓
AI
   ↓
Gamification
   ↓
Portfolio

# 5. Primary Entities

The initial CodeVerse Campus database will contain the following major entities:

## Identity & Organization

1. Users
2. Colleges
3. Departments
4. Classes
5. Faculty Profiles
6. Student Profiles

## Coding & Labs

7. Coding Problems
8. Coding Labs
9. Lab Problems
10. Lab Sessions
11. Lab Participants
12. Submissions

## Assignments

13. Assignments
14. Assignment Submissions

## AI Features

15. AI Conversations
16. AI Messages
17. AI Code Reviews
18. Hints

## Learning Intelligence

19. Skills
20. Student Skills
21. Learning Activity

## Gamification

22. Achievements
23. Student Achievements
24. Coding Streaks

## Portfolio & Career

25. Student Portfolio
26. Projects

## Communication

27. Notifications

Additional entities may be introduced when a real product requirement requires them.

New entities must not be created simply because an AI tool recommends them.

---

# 6. Entity Relationship Overview

The high-level database relationship is:

College
│
├── Departments
│       │
│       └── Classes
│              │
│              ├── Faculty
│              └── Students
│
├── Users
│
└── Coding Labs
        │
        ├── Problems
        ├── Sessions
        └── Participants
                │
                └── Submissions

Learning System:

Student
│
├── Skills
├── Learning Activity
├── Achievements
├── Coding Streak
├── Portfolio
└── AI Interactions

---

# 7. Users

The `users` entity represents every authenticated user of CodeVerse Campus.

A user can currently have one of the following primary roles:

- College Administrator
- Faculty
- Student

Future roles may include:

- Placement Cell
- Company / Recruiter

Future roles should not be added to the MVP without team approval.

---

# 8. Users Table

Suggested structure:

```text
users
├── id
├── college_id
├── email
├── password_hash
├── first_name
├── last_name
├── profile_image
├── role
├── status
├── last_login_at
├── created_at
└── updated_at

# 9. User Fields

## 9.1 id

Unique identifier for the user.

Recommended type:

UUID

Requirements:

- Primary key
- Unique
- Not null

---

## 9.2 college_id

References the college associated with the user.

Relationship:

users.college_id
        ↓
colleges.id

This identifies which college the user belongs to.

---

## 9.3 email

User's login email.

Requirements:

- Required
- Validated
- Unique according to authentication requirements

---

## 9.4 password_hash

Stores the securely hashed password.

Never store plain-text passwords.

Passwords must never be returned through normal API responses.

---

## 9.5 first_name

User's first name.

---

## 9.6 last_name

User's last name.

May be optional.

---

## 9.7 profile_image

Optional profile image URL or storage reference.

---

## 9.8 role

Defines the user's primary platform role.

MVP:

ADMIN
FACULTY
STUDENT

Future:

PLACEMENT
COMPANY

Future roles require team approval.

---

## 9.9 status

Possible values:

ACTIVE
INACTIVE
SUSPENDED
PENDING

---

## 9.10 last_login_at

Timestamp of the user's most recent successful login.

---

## 9.11 created_at

Timestamp when the account was created.

---

## 9.12 updated_at

Timestamp when the account was last modified.

---

# 10. Colleges

The `colleges` entity represents an educational institution using CodeVerse Campus.

The MVP may initially operate for one college.

The database should still maintain college relationships so future multi-college support is possible.

---

# 11. Colleges Table

Suggested structure:

colleges
├── id
├── name
├── code
├── email
├── phone
├── address
├── city
├── state
├── country
├── logo_url
├── website_url
├── status
├── created_at
└── updated_at

---

# 12. College Fields

## 12.1 id

Unique UUID.

Primary key.

---

## 12.2 name

Official college name.

---

## 12.3 code

Short unique college identifier.

Example:

LJCCA

---

## 12.4 email

Official college email.

---

## 12.5 phone

Official college contact number.

---

## 12.6 address

College address.

---

## 12.7 city

College city.

---

## 12.8 state

College state.

---

## 12.9 country

College country.

---

## 12.10 logo_url

Reference to the college logo.

---

## 12.11 website_url

Official college website.

---

## 12.12 status

Possible values:

ACTIVE
INACTIVE

---

## 12.13 created_at

Timestamp when the college was created.

---

## 12.14 updated_at

Timestamp when the college was modified.

---

# 13. Departments

The `departments` entity represents an academic department.

Examples:

- Computer Applications
- Computer Science
- Information Technology

Relationship:

College
   ↓
Department

---

# 14. Departments Table

departments
├── id
├── college_id
├── name
├── code
├── description
├── head_user_id
├── status
├── created_at
└── updated_at

---

# 15. Department Fields

## 15.1 id

Unique UUID.

Primary key.

---

## 15.2 college_id

References the college.

departments.college_id
        ↓
colleges.id

---

## 15.3 name

Official department name.

---

## 15.4 code

Short department code.

Example:

BCA

---

## 15.5 description

Optional department description.

---

## 15.6 head_user_id

Optional reference to the department head.

departments.head_user_id
        ↓
users.id

---

## 15.7 status

ACTIVE
INACTIVE

---

## 15.8 created_at

Timestamp when created.

---

## 15.9 updated_at

Timestamp when modified.

---

# 16. Classes

The `classes` entity represents an academic class or batch.

Examples:

BCA Semester 4 - A
BCA Semester 4 - B

Relationship:

College
   ↓
Department
   ↓
Class

---

# 17. Classes Table

classes
├── id
├── department_id
├── name
├── code
├── academic_year
├── semester
├── section
├── status
├── created_at
└── updated_at

---

# 18. Class Fields

## 18.1 id

Unique UUID.

---

## 18.2 department_id

References the department.

classes.department_id
        ↓
departments.id

---

## 18.3 name

Human-readable class name.

Example:

BCA Semester 4 - A

---

## 18.4 code

Unique class code.

Example:

BCA4A

---

## 18.5 academic_year

Example:

2026-27

---

## 18.6 semester

Example:

4

---

## 18.7 section

Example:

A

---

## 18.8 status

ACTIVE
INACTIVE
ARCHIVED

---

## 18.9 created_at

Timestamp when created.

---

## 18.10 updated_at

Timestamp when modified.

---

# 19. Faculty Profiles

Faculty-specific information should be stored separately from authentication data.

Relationship:

users
  │
  └── faculty_profiles

---

# 20. Faculty Profiles Table

faculty_profiles
├── id
├── user_id
├── employee_id
├── department_id
├── designation
├── specialization
├── joining_date
├── created_at
└── updated_at

---

# 21. Faculty Profile Fields

## 21.1 id

Unique UUID.

---

## 21.2 user_id

References the user.

faculty_profiles.user_id
        ↓
users.id

The referenced user must have role FACULTY.

---

## 21.3 employee_id

College employee identifier.

Example:

FAC-1024

---

## 21.4 department_id

References the faculty member's department.

faculty_profiles.department_id
        ↓
departments.id

---

## 21.5 designation

Examples:

Professor
Assistant Professor
Lecturer

---

## 21.6 specialization

Examples:

Web Development
Artificial Intelligence
Data Structures

---

## 21.7 joining_date

Date the faculty member joined.

---

## 21.8 created_at

Timestamp when created.

---

## 21.9 updated_at

Timestamp when modified.

---

# 22. Student Profiles

Student-specific information should be stored separately from authentication data.

Relationship:

users
  │
  └── student_profiles

---

# 23. Student Profiles Table

student_profiles
├── id
├── user_id
├── enrollment_number
├── department_id
├── current_class_id
├── semester
├── admission_year
├── graduation_year
├── phone
├── created_at
└── updated_at

---

# 24. Student Profile Fields

## 24.1 id

Unique UUID.

---

## 24.2 user_id

References the student user.

student_profiles.user_id
        ↓
users.id

The referenced user must have role STUDENT.

---

## 24.3 enrollment_number

Official college enrollment number.

Example:

BCA20260045

Should be unique within the college.

---

## 24.4 department_id

References the student's department.

student_profiles.department_id
        ↓
departments.id

---

## 24.5 current_class_id

References the student's current class.

student_profiles.current_class_id
        ↓
classes.id

---

## 24.6 semester

Current semester.

Example:

4

---

## 24.7 admission_year

Example:

2024

---

## 24.8 graduation_year

Example:

2027

---

## 24.9 phone

Student contact number.

This information must be protected according to privacy requirements.

---

## 24.10 created_at

Timestamp when created.

---

## 24.11 updated_at

Timestamp when modified.

---

# 25. Academic Relationship

The main academic structure is:

College
   │
   └── Department
          │
          └── Class
                 │
                 ├── Faculty
                 │
                 └── Students

These relationships must remain consistent.

---

# 26. Faculty-Class Relationship

A faculty member may teach multiple classes.

A class may have multiple faculty members.

Therefore, use a junction entity:

faculty_classes
├── id
├── faculty_id
├── class_id
├── role
├── created_at
└── updated_at

Possible role values:

PRIMARY
ASSISTANT

---

# 27. Student-Class Relationship

For the MVP, the student's current class can be stored using:

student_profiles.current_class_id

If historical enrollment is required later, create:

student_class_enrollments
├── id
├── student_id
├── class_id
├── academic_year
├── semester
├── start_date
├── end_date
└── status

Do not introduce historical enrollment complexity unless required.

---

# 28. Data Ownership

Every entity must have a clear owner.

College
→ Admin

Department
→ Admin

Class
→ Admin / Authorized Faculty

Student
→ Admin / Authorized Faculty

Coding Lab
→ Faculty

Coding Problem
→ Faculty / Authorized Content Manager

Submission
→ Student

AI Conversation
→ Student / Faculty

Authorization must always be enforced by the backend.

---

# 29. Multi-College Readiness

The architecture should allow future expansion.

Example:

College A
├── Students
├── Faculty
├── Classes
└── Labs

College B
├── Students
├── Faculty
├── Classes
└── Labs

The MVP should not implement unnecessary multi-tenant complexity.

---

# 30. Coding Problems

The `coding_problems` entity stores reusable programming problems.

Problems may be used in:

- Coding Labs
- Assignments
- Practice Arena
- Contests
- Assessments

---

# 31. Coding Problems Table

coding_problems
├── id
├── created_by
├── title
├── slug
├── description
├── difficulty
├── category
├── constraints
├── input_format
├── output_format
├── examples
├── starter_code
├── solution_reference
├── time_limit
├── memory_limit
├── status
├── created_at
└── updated_at

---

# 32. Coding Problem Fields

## 32.1 id

Unique UUID.

Primary key.

---

## 32.2 created_by

References the faculty/user who created the problem.

coding_problems.created_by
        ↓
users.id

---

## 32.3 title

Problem title.

---

## 32.4 slug

URL-friendly unique identifier.

Example:

two-sum

---

## 32.5 description

Complete problem statement.

---

## 32.6 difficulty

Possible values:

EASY
MEDIUM
HARD

---

## 32.7 category

Examples:

Arrays
Strings
Loops
Recursion
Sorting
Searching
Data Structures

---

## 32.8 constraints

Problem constraints.

---

## 32.9 input_format

Expected input description.

---

## 32.10 output_format

Expected output description.

---

## 32.11 examples

Example inputs and outputs.

---

## 32.12 starter_code

Optional initial code shown to students.

---

## 32.13 solution_reference

Reference to a secure solution or evaluation system.

Reference solutions must not be exposed to students.

---

## 32.14 time_limit

Maximum execution time.

---

## 32.15 memory_limit

Maximum allowed memory.

---

## 32.16 status

Possible values:

DRAFT
PUBLISHED
ARCHIVED

AI-generated problems must initially remain in DRAFT status.

---

# 33. Coding Labs

A coding lab represents a faculty-created programming laboratory.

Example:

Data Structures Lab - Arrays

A lab can contain multiple coding problems.

---

# 34. Coding Labs Table

coding_labs
├── id
├── class_id
├── created_by
├── title
├── description
├── instructions
├── start_time
├── end_time
├── duration_minutes
├── status
├── created_at
└── updated_at

---

# 35. Coding Lab Fields

## 35.1 id

Unique UUID.

---

## 35.2 class_id

Class for which the lab is intended.

coding_labs.class_id
        ↓
classes.id

---

## 35.3 created_by

Faculty who created the lab.

coding_labs.created_by
        ↓
users.id

---

## 35.4 title

Lab title.

---

## 35.5 description

Lab description.

---

## 35.6 instructions

Instructions provided to students.

---

## 35.7 start_time

Scheduled start time.

---

## 35.8 end_time

Scheduled end time.

---

## 35.9 duration_minutes

Expected duration.

---

## 35.10 status

Possible values:

DRAFT
SCHEDULED
ACTIVE
COMPLETED
CANCELLED

---

## 35.11 created_at

Timestamp when created.

---

## 35.12 updated_at

Timestamp when modified.

---

# 36. Lab Problems

A coding lab can contain multiple coding problems.

Use a junction entity:

lab_problems
├── id
├── lab_id
├── problem_id
├── order_number
├── points
├── created_at
└── updated_at

Relationship:

Coding Lab
   │
   └── Lab Problems
           │
           └── Coding Problem

---

# 37. Lab Sessions

A lab session represents an actual running instance of a coding lab.

This is important because the same lab may be scheduled or executed multiple times.

lab_sessions
├── id
├── lab_id
├── started_at
├── ended_at
├── status
├── created_at
└── updated_at

Possible status:

SCHEDULED
ACTIVE
COMPLETED
CANCELLED

---

# 38. Lab Participants

This records which students participated in a lab session.

lab_participants
├── id
├── session_id
├── student_id
├── joined_at
├── left_at
├── participation_status
└── created_at

Possible participation status:

JOINED
ACTIVE
LEFT
COMPLETED

This data can later support smart participation analytics.

---

# 39. Submissions

The `submissions` entity stores student coding submissions.

This is one of the most important entities in CodeVerse Campus.

It allows the platform to analyze:

- Attempts
- Correctness
- Errors
- Coding behaviour
- Improvement
- Learning progress

---

# 40. Submissions Table

submissions
├── id
├── student_id
├── problem_id
├── lab_session_id
├── language
├── source_code
├── status
├── score
├── execution_time
├── memory_used
├── test_cases_passed
├── total_test_cases
├── submitted_at
└── created_at

---

# 41. Submission Status

Possible values:

PENDING
RUNNING
ACCEPTED
WRONG_ANSWER
COMPILATION_ERROR
RUNTIME_ERROR
TIME_LIMIT_EXCEEDED
MEMORY_LIMIT_EXCEEDED
SYSTEM_ERROR

---

# 42. Submission Ownership

A submission belongs to the student who created it.

The student must be able to access their own submissions.

Faculty may access submissions belonging to students in authorized classes.

Students must never be able to access another student's private submissions.

---

# 43. Source Code Security

Source code submitted by students must be stored securely.

The application must never expose private submissions through unauthorized APIs.

If source code is displayed in analytics or reviews, authorization must be checked first.

---

# 44. Assignments

Assignments represent academic work created by faculty.

Assignments may contain:

- Coding problems
- Theory questions
- Written tasks
- File uploads

This allows CodeVerse Campus to support more than only coding.

---

# 45. Assignments Table

assignments
├── id
├── class_id
├── created_by
├── title
├── description
├── instructions
├── due_date
├── total_points
├── status
├── created_at
└── updated_at

---

# 46. Assignment Status

Possible values:

DRAFT
PUBLISHED
OPEN
CLOSED
ARCHIVED

---

# 47. Assignment Submissions

Students submit their assignment work through this entity.

assignment_submissions
├── id
├── assignment_id
├── student_id
├── text_content
├── file_url
├── submitted_at
├── score
├── feedback
├── status
├── created_at
└── updated_at

Possible status:

DRAFT
SUBMITTED
REVIEWED
LATE

---

# 48. AI Conversations

The AI Mentor needs a conversation history.

ai_conversations
├── id
├── user_id
├── context_type
├── context_id
├── title
├── created_at
└── updated_at

Possible context types:

GENERAL
PROBLEM
SUBMISSION
LAB
LEARNING

---

# 49. AI Messages

Individual messages inside an AI conversation are stored separately.

ai_messages
├── id
├── conversation_id
├── sender_type
├── message
├── metadata
├── created_at
└── updated_at

Possible sender types:

USER
AI
SYSTEM

---

# 50. AI Code Reviews

AI-generated code reviews should be stored separately.

ai_code_reviews
├── id
├── submission_id
├── summary
├── logic_feedback
├── quality_feedback
├── optimization_feedback
├── edge_case_feedback
├── complexity_analysis
├── created_at
└── updated_at

AI reviews should remain linked to the original submission.

---

# 51. Hints

The hint system can track hints requested by students.

hints
├── id
├── problem_id
├── student_id
├── hint_level
├── hint_content
├── requested_at
└── created_at

Possible hint levels:

1
2
3
4

The system can later use hint usage as one learning signal.

---

# 52. Skills

Skills represent programming concepts.

Examples:

- Variables
- Conditions
- Loops
- Arrays
- Strings
- Functions
- Recursion
- Sorting
- Searching
- Stack
- Queue
- Linked List

skills
├── id
├── name
├── category
├── description
├── difficulty
├── parent_skill_id
├── created_at
└── updated_at

The `parent_skill_id` allows hierarchical skill relationships.

---

# 53. Student Skills

This entity tracks a student's progress for each skill.

student_skills
├── id
├── student_id
├── skill_id
├── mastery_score
├── status
├── problems_attempted
├── problems_solved
├── last_activity_at
├── created_at
└── updated_at

Possible status:

LOCKED
AVAILABLE
IN_PROGRESS
MASTERED

---

# 54. Learning Activity

Learning activity records meaningful student interactions.

learning_activity
├── id
├── student_id
├── activity_type
├── reference_id
├── metadata
├── occurred_at
└── created_at

Possible activity types:

PROBLEM_SOLVED
PROBLEM_ATTEMPTED
LAB_JOINED
LAB_COMPLETED
ASSIGNMENT_SUBMITTED
HINT_REQUESTED
AI_REVIEW_REQUESTED
SKILL_COMPLETED
CONTEST_COMPLETED

This data can support Learning DNA and analytics.

---

# 55. Achievements

Achievements represent meaningful milestones.

Examples:

- First Problem Solved
- 10 Problems Solved
- 7 Day Streak
- First Contest
- Debugging Master
- Array Explorer

achievements
├── id
├── name
├── description
├── icon
├── criteria
├── xp_reward
├── created_at
└── updated_at

---

# 56. Student Achievements

Tracks achievements earned by students.

student_achievements
├── id
├── student_id
├── achievement_id
├── earned_at
└── created_at

A student should not receive the same unique achievement multiple times unless explicitly supported.

---

# 57. Coding Streaks

Coding streak information tracks consistency.

coding_streaks
├── id
├── student_id
├── current_streak
├── longest_streak
├── last_activity_date
├── created_at
└── updated_at

Streak calculations should be based on meaningful learning activity.

Simply opening the website should not automatically count as a coding day.

---

# 58. Student Portfolio

The student portfolio represents their CodeVerse learning profile.

student_portfolios
├── id
├── student_id
├── headline
├── bio
├── github_url
├── linkedin_url
├── portfolio_url
├── visibility
├── created_at
└── updated_at

Possible visibility:

PRIVATE
COLLEGE
PUBLIC

---

# 59. Projects

Students may add projects to their coding portfolio.

projects
├── id
├── student_id
├── title
├── description
├── technologies
├── github_url
├── live_url
├── image_url
├── created_at
└── updated_at

AI must never automatically create fake projects.

---

# 60. Notifications

Notifications communicate important events.

notifications
├── id
├── user_id
├── type
├── title
├── message
├── reference_type
├── reference_id
├── is_read
├── created_at
└── read_at

Possible notification types:

LAB_STARTED
ASSIGNMENT_CREATED
ASSIGNMENT_DEADLINE
SUBMISSION_RESULT
ACHIEVEMENT
AI_RECOMMENDATION
SYSTEM

---

# 61. Database Relationships Summary

The core relationships are:

College
↓
Departments
↓
Classes
↓
Faculty / Students

Faculty
↓
Coding Labs
↓
Lab Problems
↓
Coding Problems

Student
↓
Lab Participation
↓
Submissions

Student
↓
Assignments
↓
Assignment Submissions

Student
↓
Skills
↓
Learning Activity
↓
Learning DNA

Student
↓
Achievements
↓
XP / Streak

Student
↓
Portfolio
↓
Projects

Student / Faculty
↓
AI Conversations
↓
AI Messages

---

# 62. Primary Keys

Every major entity should have a unique primary key.

Recommended:

UUID

Example:

users.id
colleges.id
students.id
labs.id

Avoid relying on human-readable values such as:

- Email
- Enrollment number
- Class code

as primary keys.

These can change.

---

# 63. Foreign Keys

Relationships should use foreign keys wherever appropriate.

Examples:

users.college_id
departments.college_id
classes.department_id
student_profiles.user_id
student_profiles.current_class_id
coding_labs.class_id
submissions.student_id
submissions.problem_id

Foreign key constraints should prevent invalid relationships.

---

# 64. Timestamps

Most entities should include:

created_at
updated_at

Activity entities may additionally use:

occurred_at
submitted_at
started_at
ended_at

All timestamps should use a consistent timezone strategy.

Store timestamps consistently and convert them for display when necessary.

---

# 65. Soft Delete

Important records should generally not be physically deleted when historical data is valuable.

Instead, consider:

status
archived_at
deleted_at

depending on the entity.

Examples where historical preservation may matter:

- Submissions
- Learning activity
- AI reviews
- Assignments
- Achievements

---

# 66. Indexing

Indexes should be added to frequently queried fields.

Potential indexes include:

users.email
users.college_id
users.role

departments.college_id

classes.department_id

student_profiles.user_id
student_profiles.current_class_id

coding_labs.class_id
coding_labs.created_by

submissions.student_id
submissions.problem_id
submissions.lab_session_id

learning_activity.student_id
learning_activity.occurred_at

notifications.user_id
notifications.is_read

Indexes should be added based on actual query requirements.

Do not create indexes for every column.

---

# 67. Unique Constraints

Potential unique constraints:

users.email

college.code

department.code within college

class.code within department/college

faculty employee_id within college

student enrollment_number within college

coding_problem.slug

Unique constraints should match actual business requirements.

---

# 68. Data Validation

Database constraints should protect important rules.

Examples:

- Required fields cannot be null.
- Email format should be validated at the application layer.
- Scores should remain within valid ranges.
- Foreign keys must reference valid records.
- Difficulty must use approved values.
- Status fields must use approved values.

Validation should exist at both:

Application Layer
+
Database Layer

where appropriate.

---

# 69. Security Rules

Sensitive data must be protected.

Never expose:

- Password hashes
- Authentication secrets
- Private AI data
- Private student data
- Unauthorized submissions
- Internal system metadata

Authorization must be enforced at the API/backend layer.

---

# 70. Student Data Isolation

A student should only access their own private data.

Examples:

Student A

✓ Own submissions
✓ Own AI conversations
✓ Own achievements
✓ Own learning analytics

Student A

✗ Student B submissions
✗ Student B private analytics
✗ Student B AI conversations

Backend authorization must enforce this.

---

# 71. Faculty Data Access

Faculty should only access data they are authorized to manage.

For example:

Faculty A teaches Class A.

Faculty A:

✓ Class A students
✓ Class A labs
✓ Class A submissions
✓ Class A analytics

Faculty A:

✗ Unrelated private student data
✗ Another faculty member's restricted data

---

# 72. Admin Data Access

College administrators may manage college-level data according to their permissions.

Admin access may include:

- Students
- Faculty
- Departments
- Classes
- Labs
- Analytics
- User management

Admin access must still follow authentication and authorization rules.

---

# 73. AI Data Storage

AI-related data should be stored only when necessary.

The system should avoid storing unnecessary personal information inside AI prompts or metadata.

AI conversations should be associated with the correct user.

Sensitive information should not be unnecessarily sent to external AI providers.

---

# 74. Analytics Data

Analytics should preferably be generated from existing platform activity rather than duplicating large amounts of data.

For example:

Submission
+
Learning Activity
+
Lab Participation

can generate:

- Coding consistency
- Problem-solving trends
- Skill progress
- Classroom insights

Avoid creating duplicate analytics data when it can be calculated reliably from existing records.

---

# 75. Learning DNA Data

Learning DNA should be derived from measurable learning activity.

Possible signals:

- Problems attempted
- Problems solved
- Failed attempts
- Hint usage
- Code review requests
- Improvement over attempts
- Skill mastery
- Coding consistency

Learning DNA should not be stored as an unquestionable measure of intelligence.

---

# 76. Placement Readiness Data

Placement readiness may use:

- Skills
- Coding activity
- Problem-solving progress
- Projects
- Contest participation
- Learning consistency

The database should store the underlying evidence wherever possible.

The system should not store only:

placement_score = 92

without knowing how that score was generated.

---

# 77. Audit Logs

For important administrative actions, an audit system may be introduced.

Possible entity:

audit_logs
├── id
├── user_id
├── action
├── entity_type
├── entity_id
├── metadata
├── ip_address
└── created_at

Examples:

- User created
- User suspended
- Faculty assigned
- Lab deleted
- Assignment published

Audit logs should be introduced according to actual security requirements.

---

# 78. Database Migration Rules

Every database schema change must be performed through a migration system.

Never manually change production database structure without recording the change.

Migration workflow:

Requirement
↓
Update DATABASE.md
↓
Create Migration
↓
Test Migration
↓
Review
↓
Apply Migration

---

# 79. Migration Safety

Before modifying a table:

Check:

- Existing data
- Foreign keys
- Indexes
- API dependencies
- Frontend dependencies

Avoid destructive migrations unless explicitly approved.

---

# 80. Naming Convention

Use consistent naming.

Recommended:

Tables:

snake_case

Examples:

student_profiles
coding_problems
lab_sessions

Columns:

snake_case

Examples:

created_at
student_id
problem_id

Primary keys:

id

Foreign keys:

<entity>_id

Examples:

student_id
class_id
problem_id

---

# 81. No Duplicate Tables

Before creating a table, search the existing database documentation and schema.

Do not create:

students
student_data
student_information

for the same responsibility.

Use one clearly defined entity.

---

# 82. No Duplicate Relationships

Before adding a relationship, verify whether it already exists.

Avoid storing the same relationship in multiple places unless there is a documented reason.

Example:

If `student_profiles.current_class_id` already represents the current class, do not also create another unrelated field such as:

student_profiles.class_name

unless there is a specific requirement.

---

# 83. Database Change Approval

Major database changes require team discussion.

Examples:

- New core entity
- Removing an entity
- Changing primary keys
- Changing relationships
- Changing authentication structure
- Major normalization changes

Small additions that follow the existing architecture may be handled normally.

---

# 84. AI Database Rules

AI coding assistants must:

1. Read DATABASE.md before database work.
2. Inspect the existing schema.
3. Reuse existing tables.
4. Avoid duplicate models.
5. Follow naming conventions.
6. Use migrations.
7. Protect foreign-key relationships.
8. Avoid destructive changes.
9. Explain major schema changes.
10. Update DATABASE.md when architecture changes.

---

# 85. Database Development Workflow

The standard workflow is:

Requirement
↓
Identify Data
↓
Check DATABASE.md
↓
Check Existing Schema
↓
Identify Relationships
↓
Design Change
↓
Update Documentation
↓
Create Migration
↓
Implement Model
↓
Implement API
↓
Test
↓
Review

---

# 86. Final Database Principle

The CodeVerse Campus database must remain:

Simple
+
Consistent
+
Secure
+
Understandable
+
Maintainable

The database should support the product rather than become the product.

The team should always prefer:

Clear Architecture
over
Unnecessary Complexity

One Project
+
One Database Architecture
+
One Source of Truth

=
CodeVerse Campus