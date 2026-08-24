# CodeVerse Campus — Team Rules

> Official collaboration and development rules for the CodeVerse Campus team.

**Version:** 1.0  
**Status:** Active  
**Team Size:** 3 Developers  
**Project:** CodeVerse Campus  
**Last Updated:** August 2026


# 1. Purpose

This document defines how the CodeVerse Campus team will work together.

The project is being developed by three developers, and all three developers may use AI assistants during development.

The main goal is:

> Three Developers + Multiple AI Assistants = One Consistent Product

These rules prevent:

- Conflicting implementations
- Different coding styles
- Duplicate features
- Unnecessary architecture changes
- AI-generated conflicts
- Database conflicts
- API conflicts
- Broken existing features
- Unclear responsibilities


# 2. Golden Team Principle

CodeVerse Campus is ONE project.

It is NOT:

Developer 1's project
Developer 2's project
Developer 3's project

And it is NOT:

AI 1's architecture
AI 2's architecture
AI 3's architecture

The project follows the official documentation and agreed architecture.

AI tools are assistants.

The team owns the final decisions.


# 3. Team Structure

The project has three developers.

For documentation purposes:

- Developer 1 — Team Lead / Architecture Coordinator
- Developer 2 — Full-Stack Developer
- Developer 3 — Full-Stack Developer

Actual responsibilities may be changed by team agreement.


# 4. Team Lead Responsibility

The Team Lead is responsible for coordinating:

- Overall architecture
- Module assignment
- Major technical decisions
- Documentation consistency
- Integration planning
- Final conflict resolution
- Release coordination

The Team Lead does NOT have unlimited authority to change other people's work without discussion.

Major decisions should be discussed with the team.


# 5. Module Ownership

Each major module should have one primary owner.

Example:

Developer 1:
- Authentication
- College Admin
- User Management

Developer 2:
- Coding Lab
- Faculty Dashboard
- Live Classroom

Developer 3:
- Student Dashboard
- AI Mentor
- Learning Intelligence
- Analytics

Ownership means:

- Primary implementation responsibility
- Understanding the module
- Maintaining the module
- Reviewing related changes

Ownership does NOT mean other developers cannot modify the module.


# 6. Shared Modules

Some parts of the system affect everyone.

Examples:

- Authentication
- Database
- API structure
- Design system
- Shared components
- User roles
- Permissions
- Notification system

Changes to these areas should be discussed before implementation.


# 7. One Source of Truth

The following documents are the official project sources of truth:

PROJECT_BIBLE.md
PRODUCT_REQUIREMENTS.md
AI_CONTEXT.md
DESIGN_SYSTEM.md
DATABASE.md
API_CONTRACT.md
CODING_STANDARDS.md
TEAM_RULES.md
USER_STORIES.md

If an AI suggestion conflicts with these documents:

> The project documentation wins.


# 8. AI Usage Policy

AI is allowed for:

- Code generation
- Debugging
- Refactoring suggestions
- UI generation
- Documentation
- Testing
- Code review
- SQL assistance
- API assistance
- Learning and explanation
- Brainstorming

AI is NOT allowed to independently redefine:

- Project architecture
- Database architecture
- Authentication architecture
- API architecture
- Technology stack
- Major folder structure
- Security model


# 9. AI Context Rule

All three developers should provide their AI assistant with the same project context.

At minimum, AI should understand:

- Project purpose
- User roles
- Current module
- Technology stack
- Database structure
- API contract
- Design system
- Coding standards
- Team rules

This prevents each AI from imagining a different version of CodeVerse Campus.


# 10. AI Must Not Work From Memory Alone

Before asking AI to implement an existing feature, provide the relevant current project context.

Do not assume:

> "AI already knows our project."

The AI must work from the current code and documentation.


# 11. AI Task Prompt Standard

When assigning a task to AI, use this structure:

## Context

Explain the project/module.

## Current State

Explain what already exists.

## Task

Explain exactly what needs to be built.

## Constraints

Explain what must not be changed.

## References

Mention relevant documentation.

## Expected Output

Explain what the AI should produce.

Example:

Context:
We are building the Student Coding Lab module.

Current State:
The lab API already exists.

Task:
Create the student lab problem interface.

Constraints:
Do not modify authentication or database schema.

References:
API_CONTRACT.md
DESIGN_SYSTEM.md
CODING_STANDARDS.md

Expected Output:
React components and required API integration.


# 12. Never Blindly Accept AI Code

Every developer must understand AI-generated code before committing it.

Do not use:

"AI generated it, so it must be correct."

Instead:

AI generates
    ↓
Developer understands
    ↓
Developer tests
    ↓
Developer reviews
    ↓
Developer commits


# 13. AI Conflict Rule

If Developer 1's AI suggests Approach A and Developer 2's AI suggests Approach B:

Do NOT immediately implement both.

Follow:

Approach A
      +
Approach B
      ↓
Check Project Documentation
      ↓
Check Existing Architecture
      ↓
Compare Complexity
      ↓
Discuss With Team
      ↓
Choose One
      ↓
Document Important Decision
      ↓
Implement


# 14. AI Tie-Breaking Rules

When two AI approaches conflict, prefer the solution that:

1. Matches the existing architecture.
2. Matches the existing API contract.
3. Matches the existing database.
4. Requires fewer dependencies.
5. Changes fewer files.
6. Is easier to understand.
7. Is easier to test.
8. Is more secure.
9. Is easier to maintain.
10. Does not duplicate existing functionality.


# 15. No "AI War"

The team must never waste time comparing which AI is "better."

The goal is not:

"Which AI gave the coolest solution?"

The goal is:

"Which solution is best for CodeVerse Campus?"


# 16. Architecture Change Rule

Any major architecture change requires team discussion.

Examples:

- Changing frontend framework
- Changing backend framework
- Changing database
- Adding a major state-management system
- Changing authentication architecture
- Changing API architecture
- Changing code execution architecture
- Changing deployment architecture

Do not make these decisions individually because an AI recommended them.


# 17. Database Change Rule

Database changes are sensitive.

Before changing:

DATABASE.md

the developer must:

1. Understand the current schema.
2. Identify affected modules.
3. Explain the reason for the change.
4. Discuss with the team.
5. Update the schema/migration.
6. Update DATABASE.md.
7. Test affected functionality.


# 18. API Change Rule

Before changing an API contract:

1. Check who uses the API.
2. Identify frontend impact.
3. Identify backend impact.
4. Discuss breaking changes.
5. Update API_CONTRACT.md.
6. Update implementation.
7. Test all affected modules.

Do not silently change API request/response structures.


# 19. Shared Component Rule

Shared UI components must not be redesigned individually.

Examples:

- Button
- Input
- Modal
- Card
- Table
- Sidebar
- Navbar
- Badge
- Code Editor

If a shared component needs a major change:

1. Discuss the change.
2. Check where it is used.
3. Implement carefully.
4. Test affected pages.


# 20. Don't Break Someone Else's Module

Before changing another developer's module:

1. Understand why it exists.
2. Check its dependencies.
3. Check related APIs.
4. Check related components.
5. Inform the module owner if the change is significant.

Do not randomly rewrite someone else's implementation.


# 21. No Unnecessary Rewriting

Do not rewrite existing code simply because:

"AI gave me a cleaner version."

Existing code should only be rewritten when there is a clear reason.

Examples of valid reasons:

- Bug
- Security issue
- Performance problem
- Maintainability problem
- Requirement change
- Architecture decision


# 22. Feature Ownership

When a developer starts a feature, they should communicate:

Feature:
Owner:
Expected Scope:
Dependencies:
Expected Completion:

Example:

Feature:
Live Coding Lab

Owner:
Developer 2

Dependencies:
Authentication
Coding Execution API

Expected Scope:
Faculty creates lab and monitors students.


# 23. Avoid Duplicate Work

Before starting a feature:

Search the repository.

Check:

- Existing components
- Existing APIs
- Existing services
- Existing database tables
- Existing hooks
- Existing utilities

Do not build something that already exists.


# 24. Task Assignment

Tasks should be specific.

Bad:

"Work on student section."

Better:

"Implement Student Coding Lab problem list with difficulty filters and API integration."


# 25. Task Breakdown

Large features should be broken into smaller tasks.

Example:

Student Coding Lab

1. Lab listing
2. Lab details
3. Problem list
4. Problem editor
5. Code execution
6. Submission
7. Result display
8. Submission history
9. XP calculation
10. Progress update


# 26. Git Branch Rule

Each feature should use its own branch.

Examples:

feature/student-lab
feature/faculty-monitoring
feature/ai-mentor

Do not directly work on main for major features.


# 27. Main Branch Rule

`main` should always represent a stable version of the project.

Never intentionally push broken code to main.

Never use main as a personal experimentation branch.


# 28. Pull Request Rule

Every significant feature should be merged through a Pull Request.

The Pull Request should explain:

- What was added
- What was changed
- What files were affected
- What was tested
- Any known limitations


# 29. Code Review Rule

At least one other team member should review important changes.

The reviewer should check:

- Functionality
- Security
- Architecture
- API compatibility
- Database compatibility
- UI consistency
- Error handling
- Code quality


# 30. Review Is Not Personal

Code review is about the code.

Not the person.

Avoid:

"Your code is bad."

Prefer:

"This approach may create duplicate API logic. Can we use the existing service layer?"


# 31. Disagreement Rule

If two developers disagree:

1. Explain both approaches.
2. Check project documentation.
3. Compare technical consequences.
4. Discuss.
5. Choose the better approach.
6. Document the decision if significant.

Do not continue arguing without evidence.


# 32. Final Technical Decision

For unresolved major technical disagreements:

Team discussion
      ↓
Technical comparison
      ↓
Team Lead coordinates decision
      ↓
Decision documented
      ↓
Team follows the decision

Once a decision is made, the team should move forward instead of repeatedly reopening the same argument.


# 33. Decision Documentation

Important decisions should be recorded.

Example:

Decision:
Use service-layer architecture for API communication.

Reason:
Prevents API calls from being scattered across components.

Date:
August 2026

Impact:
All frontend modules must use the service layer.


# 34. No Silent Changes

Do not silently change:

- API response format
- Database schema
- User roles
- Permissions
- Authentication
- Shared components
- Global design tokens

If a change affects others, communicate it.


# 35. Communication Rule

Before making a change that affects another developer's module, send a short message.

Example:

"I need to add `labSessionId` to the submission API because the new live-lab flow requires it. This affects the faculty monitoring module. Please check before I merge."


# 36. Documentation Rule

If the implementation changes an important project decision, update documentation.

Examples:

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

Team process change
→ TEAM_RULES.md


# 37. Security Rule

No team member may commit:

- API keys
- Passwords
- Database credentials
- JWT secrets
- Private tokens
- Production credentials
- Private certificates

If accidentally committed:

1. Stop using the secret.
2. Revoke it.
3. Generate a replacement.
4. Remove it from the repository.
5. Inform the team.


# 38. Student Data Protection

Real student information should not be used in development unnecessarily.

Use demo data whenever possible.

Example:

Student:
Demo Student

Email:
student@example.com

Enrollment:
DEMO001


# 39. Production Data Rule

Production data must not be copied into development environments without proper authorization and protection.

Development should use:

- Mock data
- Seed data
- Anonymized data
- Test accounts


# 40. Testing Before Merge

Before merging:

[ ] Feature works

[ ] Existing features still work

[ ] API works

[ ] Validation works

[ ] Error states work

[ ] Loading states work

[ ] Responsive UI works

[ ] No console errors

[ ] No secrets included

[ ] Documentation updated where necessary


# 41. Definition of Done

A task is DONE only when:

Requirement completed
      ↓
Implementation completed
      ↓
Testing completed
      ↓
Code reviewed
      ↓
Documentation updated if required
      ↓
Pull Request approved
      ↓
Merged


# 42. No "Works on My Machine"

If something works only on one developer's computer, it is not considered complete.

The team should be able to reproduce the setup using documented configuration.


# 43. Environment Consistency

All developers should use:

- Same Node version where applicable
- Same package manager
- Same project dependencies
- Same environment variable structure
- Same database migration system
- Same coding standards

Environment differences should be documented.


# 44. Dependency Installation

Do not install packages randomly.

Before adding a dependency:

1. Search existing dependencies.
2. Check if the functionality already exists.
3. Discuss significant dependencies.
4. Add only what is necessary.


# 45. Experimental Code

Experiments should not be merged directly into main.

Use:

feature/
experiment/
prototype/

branches when necessary.

Once the experiment is complete:

- Keep it if useful.
- Remove it if unnecessary.
- Document important findings.


# 46. AI Prompt Consistency

All team members should use a common AI instruction when working on CodeVerse.

Recommended base instruction:

"You are contributing to CodeVerse Campus. Follow the project's documentation and existing architecture. Do not invent new architecture. Reuse existing components, services, APIs, and database structures. Before modifying code, understand the current implementation. Make the smallest necessary change. Do not expose secrets. If requirements conflict with the existing architecture, explain the conflict before implementing."


# 47. AI Must Ask Before Major Changes

If an AI determines that the requested feature requires a major architecture change, it should explain the issue instead of silently changing the architecture.

Example:

"The requested feature appears to require a database schema change. I will not modify the schema automatically. Here is the proposed change and its impact."


# 48. AI Context Updates

When important architecture changes occur, update:

AI_CONTEXT.md

This ensures all developers can provide the latest project context to their AI assistants.


# 49. AI Session Rule

Do not assume that two AI conversations have the same context.

Every new AI session should receive enough project context to safely perform the requested task.


# 50. AI Generated Dependencies

If AI suggests a new library:

Do not immediately install it.

First ask:

- Why is it needed?
- Is there an existing solution?
- Does it increase complexity?
- Is it compatible with our stack?
- Is it actively maintained?
- Does the team approve it?


# 51. AI Generated Architecture

If AI suggests:

"Let's completely change the architecture."

Stop.

Check:

PROJECT_BIBLE.md
DATABASE.md
API_CONTRACT.md
CODING_STANDARDS.md

Then discuss with the team.

AI suggestions are proposals, not decisions.


# 52. Emergency Bug Rule

For critical bugs:

1. Identify the problem.
2. Fix the smallest possible area.
3. Test the fix.
4. Inform the team.
5. Merge the fix.
6. Document if necessary.

Do not use an emergency bug as an excuse to rewrite the entire application.


# 53. Deadline Rule

When deadlines are close:

Do NOT sacrifice:

- Security
- Data integrity
- Authentication
- Authorization

Instead reduce:

- Optional animations
- Non-essential features
- Experimental functionality
- Cosmetic improvements


# 54. Feature Priority

When time is limited:

Priority should be:

1. Core functionality
2. Security
3. Data integrity
4. User experience
5. Analytics
6. Advanced AI features
7. Cosmetic enhancements


# 55. Presentation vs Product

Do not build features only because they look impressive in a presentation.

Every feature should have a real purpose.

CodeVerse Campus should demonstrate:

> Practical value + Technical depth + AI innovation


# 56. No Feature Creep

New ideas are welcome.

However, adding a new feature during development requires checking:

- Is it required?
- Does it fit the project?
- How much time will it take?
- What existing feature could it affect?
- Is it worth the complexity?


# 57. Feature Freeze

Before the final college presentation/demo, the team should establish a feature freeze.

After feature freeze:

Only:

- Critical bugs
- Security fixes
- Demo-breaking issues

should be merged unless the team agrees otherwise.


# 58. Final Presentation Stability

Before the final presentation:

- Freeze major architecture changes.
- Freeze database structure.
- Freeze authentication changes.
- Test all major workflows.
- Prepare demo accounts.
- Prepare backup data.
- Prepare backup deployment.


# 59. Backup Rule

Important project data and source code must be backed up.

Recommended:

Git repository
+
Cloud backup
+
Local backup where appropriate


# 60. Knowledge Sharing

No important module should be understood by only one person.

Each developer should understand the basic architecture of:

- Authentication
- Database
- API
- Coding Lab
- Student system
- Faculty system
- AI system

This prevents the project from depending completely on one person.


# 61. Documentation Is Team Memory

If an important decision exists only in someone's memory, it is not a reliable team decision.

Important decisions should be written down.


# 62. Respect Existing Work

Do not delete or replace another developer's work without understanding why it exists.

If you believe something should be removed:

1. Explain why.
2. Discuss it.
3. Confirm impact.
4. Remove it safely.


# 63. No Competition Between Developers

The goal is not:

"Who wrote the most code?"

The goal is:

"Did we build the best working product?"


# 64. Quality Over Code Volume

More code does not mean better development.

Prefer:

Less code
+
Clear architecture
+
Reusable components
+
Reliable functionality


# 65. Team Working Principle

Every developer should follow:

Understand
    ↓
Plan
    ↓
Implement
    ↓
Test
    ↓
Review
    ↓
Document
    ↓
Merge


# 66. Conflict Resolution Summary

When any conflict occurs:

## Code Conflict

Use Git conflict resolution.

## Architecture Conflict

Check PROJECT_BIBLE.md and discuss.

## API Conflict

Check API_CONTRACT.md.

## Database Conflict

Check DATABASE.md.

## Design Conflict

Check DESIGN_SYSTEM.md.

## AI Conflict

Compare against project architecture.

## Team Conflict

Discuss objectively and document major decisions.


# 67. The Three-AI Rule

If all three developers use different AI tools and receive different solutions:

AI 1 → Solution A
AI 2 → Solution B
AI 3 → Solution C

The team must NOT implement A + B + C.

Instead:

A + B + C
    ↓
Compare
    ↓
Check Documentation
    ↓
Check Existing Code
    ↓
Evaluate Trade-offs
    ↓
Choose ONE
    ↓
Document if significant
    ↓
Implement ONE


# 68. The Existing-Code Rule

When choosing between:

A new AI-generated approach

and

An existing project approach

prefer the existing project approach unless there is a clear reason to change it.


# 69. The Smallest-Change Rule

When implementing a feature:

> Make the smallest change that correctly solves the problem.

Avoid unnecessary refactoring during feature development.


# 70. The Ownership Rule

The developer responsible for a module should be consulted before major changes to that module.

However, ownership does not prevent collaboration.


# 71. The Transparency Rule

If something goes wrong:

Tell the team.

Examples:

- Broken migration
- Exposed secret
- Failed deployment
- Major bug
- AI-generated incorrect code
- Accidental deletion
- API incompatibility

Do not hide problems.


# 72. The Learning Rule

AI should help the team learn, not make the team dependent on AI.

Every developer should understand the important code they commit.


# 73. Final Team Agreement

We agree that:

1. CodeVerse Campus is one project.
2. Documentation defines the architecture.
3. AI assists development but does not control architecture.
4. Major changes require team discussion.
5. Existing code must be respected.
6. Shared components require care.
7. Security is everyone's responsibility.
8. Every developer is responsible for their code.
9. Important decisions should be documented.
10. The final goal is a stable, useful, impressive product.


# 74. Final Rule

> BUILD TOGETHER.
>
> REVIEW TOGETHER.
>
> DECIDE TOGETHER.
>
> SHIP TOGETHER.

**One Team.  
One Codebase.  
One Architecture.  
One CodeVerse Campus.**