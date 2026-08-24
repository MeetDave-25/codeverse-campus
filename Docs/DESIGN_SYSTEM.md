# 🎨 CodeVerse Campus — Design System

> The official visual and UI/UX standard for CodeVerse Campus.

**Version:** 1.0  
**Status:** Active  
**Last Updated:** August 2026

---

# 1. Purpose

The CodeVerse Campus Design System defines the visual language, UI components, interaction patterns, animations, layouts, and accessibility standards used throughout the platform.

The goal is to ensure that:

- All three developers create consistent interfaces.
- All AI coding tools generate consistent UI.
- Every module looks like part of the same product.
- New features reuse existing design patterns.
- The platform feels modern, premium, and professional.
- The interface remains usable for college students and faculty.

---

# 2. Design Vision

CodeVerse Campus should feel like a combination of:

- Modern EdTech
- Developer tools
- Premium SaaS
- AI products
- College learning platforms

The design should communicate:

> Intelligent. Modern. Technical. Premium. Simple.

It should NOT feel like:

- A basic college website.
- A generic admin dashboard.
- An old-fashioned LMS.
- A copy of LeetCode.
- An over-designed gaming website.

---

# 3. Design Principles

Every UI decision should follow these principles.

## 3.1 Clarity

Users should immediately understand:

- Where they are.
- What they can do.
- What happened.
- What they should do next.

---

## 3.2 Consistency

Similar actions should look and behave similarly throughout the platform.

For example:

All primary buttons should follow the same visual pattern.

All cards should follow the same spacing and radius system.

---

## 3.3 Hierarchy

Important information must receive stronger visual emphasis.

Priority:

1. Page title
2. Primary action
3. Important information
4. Supporting information
5. Secondary information

---

## 3.4 Simplicity

Avoid unnecessary visual complexity.

Premium design does not mean adding more elements.

Premium design means:

> Better hierarchy with fewer unnecessary elements.

---

## 3.5 Feedback

Every important user action should provide feedback.

Examples:

- Button loading state
- Success message
- Error message
- Progress indicator
- Submission status
- AI response state

---

## 3.6 Accessibility

The interface should be usable by as many users as possible.

Consider:

- Color contrast
- Readable text
- Keyboard navigation
- Focus states
- Clear error messages
- Appropriate button sizes

---

# 4. Brand Personality

CodeVerse Campus should feel:

- Intelligent
- Confident
- Energetic
- Technical
- Friendly
- Innovative
- Professional

Avoid:

- Childish
- Corporate-heavy
- Excessively futuristic
- Excessively colorful
- Visually noisy

---

# 5. Visual Direction

The interface should use a modern SaaS-inspired visual language.

Recommended characteristics:

- Clean layouts
- Strong typography
- Generous spacing
- Soft borders
- Subtle shadows
- Controlled gradients
- Minimal glass effects
- Smooth micro-interactions
- Data visualization
- Dark coding environments

---

# 6. Theme Strategy

CodeVerse Campus should support:

## Primary Theme

Light mode

Used for:

- Dashboards
- Faculty pages
- Admin pages
- Student learning pages
- Analytics
- Management interfaces

## Secondary Theme

Dark mode

Especially useful for:

- Code editor
- Coding environment
- Developer-focused screens

The overall system should remain visually consistent between themes.

---

# 7. Color System

The project should use a centralized color system.

Do NOT hardcode random colors throughout components.

Use semantic color tokens.

Example:

```text
Primary
Primary Hover
Primary Active

Background
Surface
Surface Elevated

Text Primary
Text Secondary
Text Muted

Border
Border Strong

Success
Warning
Error
Info


# 8. Primary Brand Color

The final CodeVerse Campus brand color must be defined centrally and reused throughout the application.

The primary brand color can be used for:

- Primary buttons
- Active navigation items
- Important links
- Selected states
- Progress indicators
- Key highlights
- Important interactive elements

The primary color should not be used everywhere.

It should remain visually meaningful and help users identify important actions.

---

# 9. Semantic Colors

Semantic colors communicate the state or meaning of information.

## Success

Used for:

- Successful code submission
- Completed assignment
- Correct answer
- Successful operation
- Completed learning activity

## Warning

Used for:

- Attention required
- Approaching deadline
- Partial completion
- Important notices

## Error

Used for:

- Failed submission
- Validation error
- Permission error
- System failure
- Incorrect input

## Info

Used for:

- Helpful information
- AI recommendations
- Educational explanations
- System guidance

Semantic colors must remain consistent throughout the application.

---

# 10. Typography

Typography should prioritize:

- Readability
- Clear hierarchy
- Professional appearance
- Accessibility

The system should use a limited number of font families.

## Primary Font

Used for:

- Headings
- Body text
- Navigation
- Buttons
- Forms
- Dashboard content

## Monospace Font

Used for:

- Code
- Code editor
- Console
- Terminal output
- Programming-related content

AI must not introduce additional fonts without approval.

---

# 11. Typography Hierarchy

The typography hierarchy should follow:

Display
↓
H1
↓
H2
↓
H3
↓
H4
↓
Body Large
↓
Body
↓
Body Small
↓
Caption

Page titles should be visually stronger than supporting information.

Important information should receive stronger visual emphasis.

Avoid excessive use of large typography simply for decoration.

---

# 12. Spacing System

All UI spacing should follow a consistent spacing scale.

Recommended base unit:

4px

Common spacing values:

4px
8px
12px
16px
20px
24px
32px
40px
48px
64px
80px

Use the spacing scale instead of random values.

For example:

Avoid:

padding: 17px

Prefer:

padding: 16px

unless there is a specific design reason.

---
# 13. Border Radius

CodeVerse Campus should use a consistent border-radius system.

Recommended scale:

Small: 6px
Medium: 10px
Large: 14px
XL: 18px
Pill: 999px

Use:

Small:
- Inputs
- Compact controls
- Small UI elements

Medium:
- Buttons
- Standard cards
- Dropdowns

Large:
- Dashboard cards
- Large panels
- Feature sections

XL:
- Hero sections
- Important feature containers

Pill:
- Tags
- Status badges
- Technology labels

Do not use random border-radius values throughout the project.

---

# 14. Borders

Borders should be subtle and clean.

Use borders to:

- Separate sections
- Define cards
- Define inputs
- Separate table rows
- Show selected states
- Define important panels

Avoid heavy borders.

Preferred:

Subtle Border
+
Clean Background
+
Proper Spacing

Avoid:

Heavy Border
+
Strong Shadow
+
Multiple Colors

---

# 15. Shadows

Shadows should create hierarchy, not decoration.

Use subtle shadows for:

- Dropdowns
- Modals
- Floating menus
- Elevated cards
- Important interactive surfaces

Avoid strong shadows on every element.

The interface should still look clean when shadows are reduced.

---

# 16. Cards

Cards are one of the main UI building blocks of CodeVerse Campus.

A standard card can contain:

Card
├── Header
│   ├── Icon
│   ├── Title
│   └── Action
│
├── Content
│
└── Footer
    ├── Metadata
    └── Action

Cards should have:

- Consistent padding
- Consistent radius
- Consistent border
- Clear hierarchy
- Appropriate spacing

Cards should group related information.

Do not use cards for every small piece of information.

---

# 17. Buttons

Buttons must clearly communicate their importance.

## Primary Button

Used for the main action.

Examples:

- Create Lab
- Start Coding
- Submit Code
- Create Assignment
- Start Contest

## Secondary Button

Used for supporting actions.

Examples:

- Preview
- View Details
- Cancel

## Ghost Button

Used for low-priority actions.

## Danger Button

Used for destructive actions.

Examples:

- Delete
- Remove
- Revoke Access

---

# 18. Button States

Every interactive button should support appropriate states:

Default
↓
Hover
↓
Active
↓
Focus
↓
Loading
↓
Disabled

Example:

Default:

Submit Code

Loading:

Submitting...

Disabled:

Submit Code

The loading state should clearly communicate that an operation is in progress.

---

# 19. Inputs & Forms

Forms should be simple and predictable.

Every important input should have:

- Label
- Input
- Optional description
- Validation
- Error message

Example:

Problem Title

[ Enter problem title ]

Maximum 100 characters.

Error:

Problem title is required.

Do not rely only on placeholder text as a label.

---

# 20. Navigation

Navigation should remain consistent throughout the application.

Student navigation may contain:

- Dashboard
- Labs
- Assignments
- Practice
- AI Mentor
- Skill Tree
- Analytics
- Achievements
- Portfolio

Faculty navigation may contain:

- Dashboard
- Classes
- Labs
- Assignments
- Problems
- Live Classroom
- Analytics
- AI Tools

Admin navigation may contain:

- Dashboard
- Users
- Departments
- Faculty
- Students
- Classes
- Analytics
- Settings

The navigation must be role-specific.

Users should only see navigation items they are authorized to use.

---

# 21. Sidebar

The dashboard sidebar should contain:

- CodeVerse branding
- Navigation
- Active state
- Icons
- User profile
- Optional collapse control

Example:

CodeVerse

Dashboard
Labs
Assignments
Practice
Analytics
Achievements
Portfolio

----------------

Profile
Settings
Logout

The current page must have a clearly visible active state.

---

# 22. Top Navigation

The top navigation may contain:

- Page title
- Search
- Notifications
- Help
- User profile
- Contextual actions

The top navigation should remain clean.

Do not overcrowd it with unnecessary controls.

---

# 23. Tables

Tables should be used when users need to compare structured data.

Examples:

- Student list
- Faculty list
- Submissions
- Assignments
- Problems
- Lab activity
- User management

A table should provide:

- Clear column headings
- Proper alignment
- Consistent row height
- Hover state
- Pagination when necessary
- Loading state
- Empty state
- Error state

Avoid placing too much information into one row.

---

# 24. Status Badges

Status badges provide quick visual information.

Examples:

- Active
- Pending
- Completed
- Failed
- Draft
- Published
- In Progress
- Submitted

Badges should be:

- Small
- Clear
- Consistent
- Easy to scan

Do not use badges for information that is not actually a status.

---

# 25. Progress Indicators

Progress should be visually understandable.

Possible formats:

- Progress bar
- Circular progress
- Percentage
- Skill level
- Step indicator

Example:

Arrays

████████░░ 80%

8 / 10 concepts completed

Every progress indicator must clearly communicate what is being measured.

---

# 26. Dashboard Design

Dashboards should prioritize useful information over decoration.

Recommended structure:

Page Header
↓
Primary Action
↓
Key Metrics
↓
Important Activity
↓
Analytics
↓
Recommendations

The most important information should appear first.

---

# 27. Student Dashboard

The Student Dashboard should focus on:

- Current coding labs
- Assignments
- Learning progress
- Coding streak
- XP
- Problems solved
- Skill Tree
- AI recommendations
- Recent submissions
- Learning DNA
- Placement readiness

The dashboard should answer:

> "What should I learn or do next?"

Example:

Good Morning 👋

Continue Learning

Current Skill
Arrays & Strings

----------------

XP        Streak       Problems

1200      12 days      86

----------------

Learning Progress

DSA        ████████░░
Python     ██████░░░░
Java       █████░░░░░

----------------

AI Recommendation

"Practice recursion next."

----------------

Recent Activity

---

# 28. Faculty Dashboard

The Faculty Dashboard should focus on:

- Active labs
- Classes
- Student activity
- Submissions
- Assignments
- Problems
- Performance analytics
- AI classroom insights
- Students needing attention

The dashboard should answer:

> "How is my class performing and where do students need help?"

Example insights:

"24/30 students have joined today's lab."

"8 students are struggling with recursion."

"5 students requested hints."

---

# 29. Admin Dashboard

The Admin Dashboard should focus on:

- Total students
- Total faculty
- Departments
- Classes
- Active labs
- Platform activity
- College-wide analytics
- User management

The dashboard should answer:

> "What is happening across my college?"

Example:

Students: 1,240

Faculty: 58

Active Classes: 34

Active Labs: 12

Problems Solved Today: 842

---

# 30. Coding Environment

The Coding Lab is one of the most important parts of CodeVerse Campus.

The coding environment should contain:

Problem Panel
+
Code Editor
+
Test Cases
+
Console
+
Submission Controls
+
AI Assistance

Recommended layout:

┌───────────────────────────────────────────────┐
│ Problem                     Timer             │
├──────────────────┬────────────────────────────┤
│                  │                            │
│ Problem          │       Code Editor          │
│ Statement        │                            │
│                  │                            │
│ Examples         │                            │
│                  │                            │
├──────────────────┼────────────────────────────┤
│ Test Cases       │ Console                    │
└──────────────────┴────────────────────────────┘

The coding environment should feel like a professional developer tool.

---

# 31. Code Editor

The code editor should support:

- Syntax highlighting
- Line numbers
- Code formatting
- Language selection
- Run Code
- Submit Code
- Error output
- Test cases

The editor should use a monospace font.

The coding interface should visually differ from normal dashboard content while remaining part of the same design system.

---

# 32. Coding Submission Experience

The submission flow should be clear.

Student:

Write Code
↓
Run Code
↓
View Output
↓
Fix Errors
↓
Submit
↓
System Evaluation
↓
Result
↓
AI Feedback

Possible results:

Accepted
Wrong Answer
Compilation Error
Runtime Error
Time Limit Exceeded

The result should clearly explain what happened.

---

# 33. AI Mentor Interface

The AI Mentor should feel integrated into the learning environment rather than like a generic chatbot.

Possible actions:

AI Mentor

How can I help?

[ Explain this concept ]

[ Give me a hint ]

[ Review my code ]

[ Explain this error ]

[ Suggest what I should learn next ]

AI responses should use:

- Clear headings
- Short paragraphs
- Code blocks
- Examples
- Step-by-step explanations

Avoid huge walls of text.

---

# 34. AI Hint Interface

The hint system should communicate progressive assistance.

Example:

Need Help?

Hint Level 1
Think about the data structure required.

[ Show Hint ]

----------------

Hint Level 2
Consider how you can track previously visited elements.

[ Show Hint ]

----------------

Hint Level 3
Now think about the time complexity of your approach.

[ Show Hint ]

The student should intentionally request deeper hints.

---

# 35. AI Code Review Interface

After submission, the student may receive:

Code Review

✓ Logic
✓ Readability
⚠ Optimization
⚠ Edge Cases

Overall:

Good implementation.

Suggestions:

1. Improve variable naming.
2. Handle empty input.
3. Consider reducing time complexity.

The purpose is learning, not simply judging.

---

# 36. AI Classroom Insight Interface

Faculty may see AI-generated classroom insights.

Example:

┌──────────────────────────────────────┐
│ AI Classroom Insight                 │
│                                      │
│ 12 of 30 students are struggling     │
│ with array indexing.                 │
│                                      │
│ Recommendation:                      │
│ Consider revising array traversal    │
│ before moving to the next topic.     │
│                                      │
│ [ View Students ]                    │
└──────────────────────────────────────┘

Insights should be based on actual classroom activity.

---

# 37. Learning DNA Visualization

Learning DNA should visually communicate multiple learning dimensions.

Example:

Problem Solving     █████████░ 90%
Debugging           ███████░░░ 70%
Consistency         █████████░ 88%
Optimization        ██████░░░░ 60%
Accuracy            ████████░░ 82%

The visualization should remain understandable.

Do not make the Learning DNA graph unnecessarily complicated.

---

# 38. Skill Tree

The Skill Tree should visually show:

- Locked skills
- Available skills
- In-progress skills
- Completed skills
- Recommended next skills

Example:

Programming
│
├── Fundamentals ✓
│   ├── Variables ✓
│   ├── Conditions ✓
│   └── Loops ✓
│
├── Data Structures
│   ├── Arrays ✓
│   ├── Strings ◉
│   ├── Stack 🔒
│   └── Queue 🔒
│
└── Algorithms
    ├── Searching 🔒
    └── Sorting 🔒

The Skill Tree should encourage exploration without becoming visually overwhelming.

---

# 39. Gamification UI

Gamification should feel rewarding but professional.

Possible UI elements:

- XP counter
- Level
- Streak
- Achievement badges
- Progress bars
- Leaderboard
- Skill milestones

Example:

Level 12

████████░░ 82%

1,240 / 1,500 XP

🔥 12 Day Streak

Animations may be used when:

- A badge is unlocked
- XP is earned
- A level increases
- A streak milestone is reached

Animations must remain subtle.

---

# 40. Notifications

Notifications should be concise and meaningful.

Success:

"Lab created successfully."

Warning:

"Assignment deadline is tomorrow."

Error:

"Unable to submit your code."

Info:

"Your AI learning recommendation is ready."

Notifications should not interrupt the user unnecessarily.

---

# 41. Modals

Modals should be used for focused interactions.

Good use cases:

- Confirmation
- Delete confirmation
- Important forms
- Focused workflows
- Permission changes

Example:

Delete Coding Lab?

This action cannot be undone.

[ Cancel ] [ Delete Lab ]

Avoid using modals for large pages of content.

---

# 42. Tooltips

Tooltips may explain:

- Icon-only buttons
- Technical terminology
- Advanced features
- Less obvious controls

Do not hide critical information inside tooltips.

Critical information should remain visible.

---

# 43. Animation Philosophy

Animations should improve:

- Understanding
- Navigation
- Feedback
- Hierarchy
- Engagement

Animations should NOT exist simply because they look impressive.

Preferred animation characteristics:

- Fast
- Smooth
- Subtle
- Purposeful

Avoid:

- Excessive bouncing
- Constant movement
- Long transitions
- Distracting effects
- Animations on every element

---

# 44. Micro-Interactions

Useful micro-interactions include:

- Button hover
- Card hover
- Progress animation
- Submission success
- XP reward
- Badge unlock
- Streak update
- AI response appearance
- Sidebar transitions

Micro-interactions should make the interface feel responsive without becoming distracting.

---

# 45. Page Transitions

Page transitions should be subtle.

Preferred:

- Fade
- Small slide
- Soft scale

Avoid dramatic transitions that slow down navigation.

Performance should always take priority over visual effects.

---

# 46. AI Visual Language

AI-powered features should have a recognizable visual identity.

AI features include:

- AI Mentor
- AI Hint
- AI Code Review
- AI Classroom Insight
- AI Question Generator
- AI Recommendation

AI components may use a subtle visual distinction such as:

- AI icon
- AI label
- Subtle gradient
- Distinctive background
- Animated response indicator

However, all AI interfaces must still follow the main CodeVerse Design System.

AI features should not look like completely separate products.

---

# 47. Accessibility

The platform should consider:

- Keyboard navigation
- Visible focus states
- Adequate color contrast
- Readable font sizes
- Accessible form labels
- Alternative text for meaningful images
- Semantic HTML
- Screen-reader-friendly controls

Interactive elements must not rely only on color to communicate their meaning.

---

# 48. Responsive Design

CodeVerse Campus should support:

- Desktop
- Laptop
- Tablet
- Mobile

The design should adapt rather than simply shrink.

Priority:

Desktop
↓
Tablet
↓
Mobile

The coding environment may require a specialized responsive layout.

---

# 49. Mobile Design

Mobile interfaces should prioritize:

- Essential information
- Touch-friendly controls
- Simple navigation
- Readability
- Important actions

Do not attempt to display the entire desktop dashboard on a small screen.

Complex features such as the coding editor may require a specialized mobile experience.

---

# 50. Design Consistency Rule

Before creating a new UI component, developers and AI must ask:

1. Does this component already exist?
2. Can an existing component be reused?
3. Does it follow the Design System?
4. Does it use the correct spacing?
5. Does it use the correct typography?
6. Does it use the correct colors?
7. Does it follow existing interaction patterns?

If a new reusable component is introduced, it should be documented in this file.

---

# 51. Final Design Principle

CodeVerse Campus must feel like ONE unified product.

It should never look like:

Developer 1 built one section
+
Developer 2 built another section
+
Developer 3 built another section
+
Different AI tools generated random UI

Instead:

ONE BRAND
+
ONE DESIGN SYSTEM
+
ONE COMPONENT LANGUAGE
+
ONE USER EXPERIENCE

=

CODEVERSE CAMPUS