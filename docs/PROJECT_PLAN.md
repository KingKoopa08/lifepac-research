# Homeschool App and Website Project Plan

## Goal
Build a homeschool learning platform using the LIFEPAC research repo as the curriculum foundation.

The product has two primary experiences:

1. Student curriculum side: students work through grade, subject, unit, lesson, practice, quiz, and test material.
2. Parent side: parents assign work, monitor progress, review scores, see trouble spots, and manage children.

Initial platforms:

- Website first, responsive and parent-friendly
- Android app first for mobile/tablet use
- iOS after the core platform is stable

## Product pillars

### 1. Curriculum engine
The existing LIFEPAC research gives us grade, subject, unit, and outline structure. The app needs to convert that into a clean internal curriculum model.

Core objects:

- Grade
- Subject
- Unit
- Section
- Lesson
- Activity
- Assignment
- Quiz
- Test
- Score
- Progress event

Important boundary: the repo contains public research/index data only. We should not store paid workbook content unless Kaecey provides legally usable content or we create original lesson content around the outline.

### 2. Student learning experience
Students should be able to log in, see today's work, continue a lesson, complete activities, take quizzes/tests, and see encouraging progress.

MVP student features:

- Dashboard
- Today's assignments
- Curriculum browser
- Lesson player
- Practice activity shell
- Quiz/test shell
- Progress indicator
- Streak or completion motivation

### 3. Parent command center
Parents need a clear, no-drama view of how their kids are doing.

MVP parent features:

- Parent dashboard
- Add/manage child profiles
- Assign grade/subjects/units
- Daily/weekly progress view
- Scores and completion reports
- Struggle alerts
- Manual grade adjustments or notes
- Print/export progress summary

### 4. Admin/curriculum tools
We need a way to import, clean, edit, and publish curriculum data.

MVP admin features:

- Import LIFEPAC outline JSON
- Map outline rows to grade/subject/unit structure
- Flag missing content
- Edit lesson metadata
- Publish curriculum version
- Track source and licensing status

### 5. Platform foundation
The site and apps should share one backend and data model.

Recommended stack:

- Web: Next.js
- API: Next.js API routes or separate Node/Nest API
- Database: Postgres
- ORM: Prisma
- Auth: Clerk or similar family/account auth
- Android: Kotlin/Jetpack Compose, or React Native if we want fastest shared mobile work
- iOS later: SwiftUI if native, or React Native if shared mobile path wins

Recommendation: use Next.js + Postgres + Prisma for web/backend, then decide Android native vs React Native after the UX is sketched. If speed matters most, React Native can cover Android now and iOS later with less duplicate work.

## MVP scope

### MVP 0: Planning and operations
- Linear workspace/project created
- GitHub repos connected
- Task workflow defined
- Agent rules written
- Labels, priorities, and milestones created

### MVP 1: Curriculum data foundation
- Normalize LIFEPAC research data into database-ready schema
- Import grades 1 through 12, subjects, units, and outline sections
- Create curriculum browser on web
- Build admin review screen for curriculum gaps

### MVP 2: Parent + student accounts
- Parent signup/login
- Parent creates child profile
- Child login/access flow
- Parent assigns grade and subjects

### MVP 3: Student learning loop
- Student dashboard
- Today's assignments
- Lesson shell
- Activity completion
- Quiz/test shell
- Progress tracking

### MVP 4: Parent reporting loop
- Parent dashboard
- Completion by child/subject/unit
- Scores
- Trouble spots
- Weekly summary/export

### MVP 5: Android app
- Student dashboard
- Today's work
- Lesson shell
- Quiz/test shell
- Parent quick progress view
- Sync with same backend

### MVP 6: Beta readiness
- QA pass
- Seed curriculum review
- Deployment
- Analytics/logging
- Feedback capture

## Linear workflow from the reference video

Linear becomes the source of truth.

Every issue should have:

- Clear title
- Priority
- Status
- Owner
- Acceptance criteria
- Test/verification step
- Linked GitHub branch/PR when implementation starts

Suggested statuses:

- Backlog
- Ready
- In Progress
- In Review
- Done
- Blocked

Suggested priority order:

1. P0: Foundation blockers
2. P1: MVP required
3. P2: Important soon
4. P3: Later polish

Suggested projects:

- HOM-001: Product Planning and Linear Setup
- HOM-002: Curriculum Data Foundation
- HOM-003: Web App MVP
- HOM-004: Parent Portal
- HOM-005: Student Learning Experience
- HOM-006: Android App MVP
- HOM-007: Admin Curriculum Tools
- HOM-008: QA, Beta, and Launch
- HOM-009: iOS App Later

## First build recommendation
Start with the web/backend plus curriculum importer. Do not start Android until the curriculum model and core API are stable. Otherwise we will build the same uncertainty twice.

First sprint:

1. Set up Linear project and workflow
2. Create repo structure for web/backend
3. Define database schema
4. Build LIFEPAC importer
5. Build basic curriculum browser
6. Build parent/child auth model
7. Build student dashboard wireframe
8. Build parent dashboard wireframe

## Open decisions

- App name and branding
- Faith-forward positioning vs neutral homeschool positioning
- Native Android vs React Native
- Clerk vs custom auth
- Whether curriculum content is original, licensed, parent-entered, or linked/indexed only
- Whether parents can customize pacing and skip/replace units
