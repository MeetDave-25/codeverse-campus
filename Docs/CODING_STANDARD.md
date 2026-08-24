# CodeVerse Campus — Coding Standards

> Official coding rules for the CodeVerse Campus development team.

**Version:** 1.0  
**Status:** Active  
**Last Updated:** August 2026

---

# 1. Purpose

This document defines how CodeVerse Campus code must be written.

The purpose is to ensure that all three developers and all AI coding assistants produce code that follows the same architecture, style, naming conventions, and quality standards.

The goal is:

> One project → One architecture → One coding standard

---

# 2. Core Principle

Code should be:

- Simple
- Readable
- Maintainable
- Reusable
- Secure
- Testable
- Consistent

Avoid unnecessary complexity.

Do not write complicated code just because an AI suggested it.

---

# 3. AI-Assisted Development

AI tools are allowed and encouraged.

However:

> AI is a development assistant, not the project architect.

Every developer is responsible for understanding and reviewing AI-generated code before committing it.

AI-generated code must follow:

- PROJECT_BIBLE.md
- PRODUCT_REQUIREMENTS.md
- AI_CONTEXT.md
- DATABASE.md
- API_CONTRACT.md
- DESIGN_SYSTEM.md
- CODING_STANDARDS.md
- TEAM_RULES.md

---

# 4. Before Asking AI to Code

Before giving a coding task to AI, provide the relevant project context.

The developer should tell the AI:

1. What feature is being built.
2. Which module it belongs to.
3. Existing files involved.
4. Existing API contract.
5. Existing database structure.
6. Existing UI components.
7. What must NOT be changed.

Example:

> Implement the student lab submission screen using the existing API contract and existing Button, Card, Modal, and CodeEditor components. Do not modify authentication, database schema, or unrelated modules.

---

# 5. AI Must Not Invent Architecture

AI must not independently create:

- New frameworks
- New database systems
- New authentication systems
- New API patterns
- New state-management libraries
- New folder structures
- New UI libraries

unless the team has approved the change.

---

# 6. AI Must Read Existing Code

Before modifying a feature, AI should inspect:

- Existing component
- Related API
- Related database model
- Existing utilities
- Existing types
- Existing styles

The AI should extend existing architecture rather than rebuilding it.

---

# 7. No Unnecessary Rewrites

AI must not rewrite an entire file when a small modification is required.

Bad:

> Rewrite the complete dashboard to add one button.

Preferred:

> Add the button to the existing dashboard without changing unrelated components.

---

# 8. Technology Stack

The exact technology stack is defined in PROJECT_BIBLE.md.

Developers must not introduce a new technology without team approval.

Example categories:

Frontend:
- React
- TypeScript
- Tailwind CSS

Backend:
- Approved backend framework

Database:
- PostgreSQL

AI:
- Approved AI provider/service

---

# 9. Frontend Folder Structure

Recommended structure:

frontend/
├── src/
│   ├── components/
│   ├── pages/
│   ├── layouts/
│   ├── features/
│   ├── hooks/
│   ├── services/
│   ├── types/
│   ├── utils/
│   ├── constants/
│   ├── assets/
│   └── styles/
│
└── ...

Feature-specific code should stay close to its feature.

Example:

features/
└── coding-lab/
    ├── components/
    ├── hooks/
    ├── services/
    ├── types/
    └── index.ts

---

# 10. Backend Folder Structure

Recommended structure:

backend/
├── src/
│   ├── controllers/
│   ├── services/
│   ├── repositories/
│   ├── models/
│   ├── routes/
│   ├── middleware/
│   ├── validators/
│   ├── utils/
│   ├── config/
│   └── types/
│
└── ...

The exact structure may change according to the selected backend framework.

---

# 11. Component Rules

React components should follow single-responsibility principles.

A component should ideally have one clear purpose.

Bad:

Dashboard.tsx
→ Authentication
→ API calls
→ Database logic
→ AI logic
→ 500 lines of UI

Better:

Dashboard
├── DashboardHeader
├── StatisticsCards
├── RecentActivity
├── SkillProgress
└── LearningRecommendations

---

# 12. Component Naming

Use PascalCase.

Correct:

```text
StudentDashboard.tsx
CodingLabCard.tsx
SubmissionResult.tsx

# 12. Variable Naming

Use camelCase for variables.

Correct:

studentName
problemId
submissionStatus
currentLab

Avoid:

student_name
ProblemID
CURRENTLAB

Variables should have meaningful names.

Bad:

const x = 10;

Better:

const maxAttempts = 10;


# 13. Function Naming

Functions should clearly describe their purpose.

Correct:

getStudentProfile()
submitCode()
calculateScore()
generateHint()
updateLabStatus()

Avoid vague names:

doThing()
process()
handle()
test()

unless the context makes the purpose completely clear.


# 14. Boolean Naming

Boolean variables should clearly indicate a true/false state.

Preferred:

isLoading
isAuthenticated
isActive
hasSubmitted
canEdit
canSubmit

Avoid:

loading
auth
active
submit

when their meaning is unclear.


# 15. Constants

Constants must have descriptive names.

Examples:

MAX_CODE_LENGTH
DEFAULT_PAGE_SIZE
MAX_HINT_LEVEL
SUPPORTED_LANGUAGES

Avoid magic numbers.

Bad:

if (attempts > 5)

Better:

if (attempts > MAX_ATTEMPTS)


# 16. TypeScript Rules

Use TypeScript types/interfaces for important data structures.

Example:

interface Student {
  id: string;
  name: string;
  email: string;
  role: "STUDENT";
}

Avoid unnecessary `any`.

Bad:

const student: any = data;

Preferred:

const student: Student = data;


# 17. API Types

API request and response structures must match `API_CONTRACT.md`.

Example:

interface CreateProblemRequest {
  title: string;
  description: string;
  difficulty: "EASY" | "MEDIUM" | "HARD";
  category: string;
}

Do not invent a different frontend API structure.


# 18. API Calls

API communication should happen through a dedicated service layer.

Preferred architecture:

Component
    ↓
Hook
    ↓
Service
    ↓
API
    ↓
Backend

Avoid scattering raw API requests throughout UI components.


# 19. API Error Handling

Every API request must handle:

- Loading
- Success
- Error
- Empty state

Never silently ignore API errors.

Example:

Loading
    ↓
Success → Display data

Loading
    ↓
Error → Display useful message


# 20. User-Friendly Errors

Do not expose internal technical errors directly to users.

Bad:

PostgreSQL foreign key constraint failed

Better:

Unable to save the changes. Please try again.

Detailed technical errors should remain available in development logs where appropriate.


# 21. Loading States

Every asynchronous UI operation should have a loading state.

Examples:

- Login
- AI response
- Code execution
- Submission
- Dashboard analytics
- File upload

The interface should never appear frozen during a network operation.


# 22. Empty States

Every list should have a meaningful empty state.

Example:

No coding problems found.

Try changing your filters or create a new problem.

Never leave a blank screen when there is no data.


# 23. Responsive Design

All frontend features should support:

- Desktop
- Laptop
- Tablet
- Mobile

The platform is primarily designed for college programming labs, but smaller screens should remain usable.


# 24. Accessibility

UI should consider:

- Keyboard navigation
- Proper labels
- Readable contrast
- Focus states
- Semantic HTML
- Screen-reader compatibility

Do not rely only on color to communicate information.


# 25. Design System

Developers must follow `DESIGN_SYSTEM.md`.

Do not randomly create new:

- Colors
- Buttons
- Cards
- Shadows
- Typography
- Border styles
- Animations

when an existing design token or component already exists.


# 26. Reusable Components

Before creating a new component, check whether an existing component can be reused.

Example:

If the project already has:

<Button />

do not create:

<CustomButton />

for the same purpose.


# 27. No Duplicate Components

Before creating:

StudentCard.tsx

search the project for existing components such as:

StudentCard
UserCard
ProfileCard

Reuse or extend an existing component when appropriate.


# 28. State Management

Use the simplest state-management approach appropriate for the feature.

Preferred order:

Local State
    ↓
Context
    ↓
Global State

Global state should only be introduced when genuinely necessary.

Do not add a state-management library simply because an AI suggested it.


# 29. Forms

Forms must include:

- Validation
- Error messages
- Loading state
- Submit state
- Success feedback

Frontend validation improves UX.

Backend validation remains mandatory.


# 30. Security

Never hardcode:

- API keys
- Passwords
- Tokens
- Database credentials
- Secrets

Use environment variables.

Correct:

process.env.AI_API_KEY

Incorrect:

const apiKey = "real-secret";


# 31. Environment Variables

Use:

.env

for local secrets.

Use:

.env.example

for documenting required configuration.

Never commit:

.env
.env.production
.env.local


# 32. Authentication

Authentication logic must remain centralized.

Do not create separate authentication systems for:

- Student
- Faculty
- Admin

Use one authentication architecture with role-based authorization.


# 33. Authorization

Never rely only on frontend route protection.

For example, hiding:

Admin Dashboard

does NOT make the API secure.

The backend must independently verify permissions.


# 34. Database Access

Frontend applications must not directly perform unauthorized database operations.

Preferred:

Frontend
    ↓
API
    ↓
Backend
    ↓
Database

Database access must remain controlled by the backend.


# 35. Database Changes

Before changing database structure:

1. Read `DATABASE.md`.
2. Check the existing schema.
3. Discuss major changes.
4. Create a migration.
5. Update documentation.
6. Test the migration.

Never silently modify the production database.


# 36. API Contract Changes

Before changing an API:

1. Read `API_CONTRACT.md`.
2. Search where the endpoint is used.
3. Identify affected modules.
4. Update the API contract.
5. Update the backend.
6. Update the frontend.
7. Test the complete flow.


# 37. AI Feature Rules

AI features must be isolated behind backend services.

Preferred:

Frontend
    ↓
Backend AI Service
    ↓
AI Provider

Never expose AI provider credentials to the browser.


# 38. AI Output Validation

AI-generated content must not automatically be treated as correct.

Validate AI-generated:

- Coding problems
- Explanations
- Hints
- Recommendations
- Analytics
- Code reviews

AI output is assistance, not absolute truth.


# 39. Code Execution Security

Student code must never execute directly inside the main application process.

Student code should run inside a controlled execution environment or sandbox.

The execution system should enforce:

- Time limits
- Memory limits
- Resource limits
- Supported languages
- Process isolation


# 40. Comments

Comments should explain WHY something exists.

Good:

// Keep the previous submission visible so students can compare improvement.

Avoid comments that simply repeat the code.

Bad:

// Increment i
i++;


# 41. TODO Comments

TODO comments must be specific.

Good:

TODO: Replace temporary mock analytics with real submission analytics.

Avoid:

TODO: Fix this

TODO: Later


# 42. Dead Code

Do not keep unused:

- Components
- Functions
- Imports
- Variables
- API endpoints
- Dependencies

Remove confirmed unnecessary code.


# 43. Dependency Rules

Do not add a new package without checking:

1. Is it already installed?
2. Can existing functionality solve the problem?
3. Is the package maintained?
4. Does it introduce unnecessary complexity?
5. Does the team agree?


# 44. Performance

Do not optimize prematurely.

Priority:

1. Correctness
2. Maintainability
3. Security
4. User experience
5. Performance

Performance optimization should be based on an actual requirement or measurable problem.


# 45. Git Branches

Use feature branches for development.

Example:

main
│
├── feature/authentication
├── feature/coding-lab
├── feature/ai-mentor
└── feature/student-dashboard

Major features should not be developed directly on `main`.


# 46. Branch Naming

Recommended formats:

feature/<feature-name>
fix/<bug-name>
refactor/<area>
docs/<document-name>

Examples:

feature/student-dashboard
feature/live-lab-monitoring
fix/submission-timeout
docs/api-contract


# 47. Commit Messages

Use meaningful commit messages.

Preferred:

feat: add student lab dashboard
feat: implement code submission API
fix: resolve submission status bug
docs: update API contract
refactor: simplify lab session service

Avoid:

update
changes
final
final2
working
done


# 48. Pull Requests

Before merging a Pull Request:

- Code works
- No secrets are included
- Tests pass
- API contract is respected
- Database changes are documented
- No unnecessary files are changed
- No unrelated refactoring exists
- UI follows the design system


# 49. Code Review

Important changes should be reviewed by at least one other team member.

Review:

- Logic
- Security
- API compatibility
- Database compatibility
- UI consistency
- Error handling
- AI-generated code


# 50. AI Code Review

AI may be used for code review.

However:

AI review does not replace human review.

The developer who submits the code remains responsible for understanding and approving it.


# 51. Handling Conflicting AI Suggestions

If two AI tools suggest different implementations:

DO NOT choose randomly.

Use this process:

AI Suggestion A
       ↓
AI Suggestion B
       ↓
Check PROJECT_BIBLE.md
       ↓
Check Existing Architecture
       ↓
Check API_CONTRACT.md
       ↓
Check DATABASE.md
       ↓
Compare Complexity
       ↓
Team Decision
       ↓
Implement One Approach


# 52. AI Tie-Breaking Rule

When AI suggestions conflict, prefer the solution that:

1. Fits the existing architecture.
2. Requires fewer unnecessary dependencies.
3. Changes fewer existing files.
4. Is easier for the team to understand.
5. Is easier to test.
6. Is more secure.
7. Is easier to maintain.

The newest or most impressive AI suggestion is NOT automatically better.


# 53. No AI-Driven Architecture Changes

AI must not independently decide:

- Database architecture
- Authentication architecture
- API architecture
- Deployment architecture
- Major framework changes

without team approval.


# 54. Before Merging AI-Generated Code

The developer must personally verify:

[ ] I understand the code.

[ ] It follows the project architecture.

[ ] It follows API_CONTRACT.md.

[ ] It follows DATABASE.md.

[ ] It follows DESIGN_SYSTEM.md.

[ ] No secrets are included.

[ ] No unnecessary dependencies were added.

[ ] Existing functionality still works.

[ ] Tests pass.


# 55. File Ownership

Developers may be responsible for specific modules, but nobody individually owns the architecture.

Example:

Developer 1:
Authentication + Admin

Developer 2:
Coding Lab + Faculty

Developer 3:
Student + AI + Analytics

These assignments may change.

All developers must follow the same project architecture.


# 56. Shared Components

Shared components must be treated carefully.

Examples:

- Button
- Modal
- Input
- Table
- Card
- Navbar
- Sidebar
- Code Editor

Changes to shared components can affect multiple modules.

Major shared-component changes should be reviewed before merging.


# 57. Feature Isolation

A feature should avoid modifying unrelated modules.

For example, while building:

AI Mentor

do not unnecessarily modify:

- Authentication
- Admin
- Placement
- Database

unless the feature genuinely requires those changes.


# 58. Mock Data

Mock data is allowed during UI development.

However, it must be clearly labelled.

Example:

// MOCK DATA
// Replace with API integration after endpoint implementation.

Mock data must not accidentally be shipped as real production functionality.


# 59. Testing Principle

Every major feature should have appropriate testing.

Possible testing levels:

- Unit tests
- Integration tests
- API tests
- Component tests
- End-to-end tests

Testing depth depends on the importance and risk of the feature.


# 60. Definition of Done

A feature is considered complete only when:

Requirement implemented
        ↓
UI completed
        ↓
API integrated
        ↓
Validation implemented
        ↓
Error handling implemented
        ↓
Security checked
        ↓
Testing completed
        ↓
Documentation updated
        ↓
Code reviewed
        ↓
Merged


# 61. Documentation Rule

If code changes project architecture, update the relevant documentation.

Database change
→ DATABASE.md

API change
→ API_CONTRACT.md

Design change
→ DESIGN_SYSTEM.md

Product behavior change
→ PRODUCT_REQUIREMENTS.md

AI behavior change
→ AI_CONTEXT.md

Team workflow change
→ TEAM_RULES.md


# 62. Don't Break Existing Features

Before merging a feature, verify that existing functionality still works.

Important areas include:

- Login
- Role permissions
- Student dashboard
- Faculty dashboard
- Admin dashboard
- Coding labs
- Coding submissions
- AI features


# 63. Keep Changes Small

Prefer small, focused commits.

Bad:

Add AI + authentication + dashboard + database + redesign

Better:

feat: add AI mentor conversation API

feat: add AI mentor chat UI

feat: add AI mentor loading state

test: add AI mentor API tests


# 64. Code Quality Priority

When making implementation decisions:

Security
    ↓
Correctness
    ↓
Maintainability
    ↓
Consistency
    ↓
Performance
    ↓
Convenience

Never sacrifice security or correctness for development speed.


# 65. Final Team Principle

CodeVerse Campus is not three separate projects.

It is one project built by three developers.

Therefore:

We do not build according to what "my AI prefers."

We build according to:

PROJECT_BIBLE.md
        +
PRODUCT_REQUIREMENTS.md
        +
DATABASE.md
        +
API_CONTRACT.md
        +
DESIGN_SYSTEM.md
        +
CODING_STANDARDS.md
        +
TEAM_RULES.md

These documents define the project.

AI tools assist us in implementing the project.

They do not redefine the project.


# 66. Golden Rule

Before writing code:

READ.

Before changing architecture:

DISCUSS.

Before changing an API:

CHECK.

Before changing the database:

CHECK.

Before trusting AI-generated code:

REVIEW.

Before merging:

TEST.

Before committing:

VERIFY.

> One Codebase. One Architecture. One Standard.