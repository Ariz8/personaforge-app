# project_map.md

## Overview
PersonaForge is a modular storytelling app that enables writers and creators to build psychologically authentic characters using MBTI profiles, narrative arcs, and relational dynamics. Characters can be assigned MBTI types, connected to story arcs, organized into story folders, and simulated through AI-driven dialogue engines.

## Pages & Components

### 1. Home
- Overview of app purpose
- Quick Start for new users
- Load Saved Stories (from database)

### 2. MBTI Personality Selection Page
- List/Grid of all 16 MBTI personality types
- Preview modal with summary of key traits and title (e.g., ENFJ – The Protagonist)
- “Select This Personality” button

### 3. Character Sheet Page
- MBTI Profile Overview
- Cheat Sheet Sections:
  - Love Language & Relationship Dynamics
  - Strengths / Weaknesses
  - Cognitive Function Stack
  - Dialogue Style
  - Conflict Style
  - Growth Arc Potential
  - Ideal Story Roles
  - Compatibility: Works Well With / Struggles With
- Arc Selection Area
- “Save to Story Folder” button

### 4. Story Folders Page
- List of all saved stories
- View and manage characters in each story
- Add/Remove Characters

### 5. Relationship Mapping Page
- Define inter-character relationships (e.g. crushes, enemies, friendships)
- Auto-generate narrative consequences (e.g. love triangles)
- Update character sheets based on connections

### 6. AI Interaction Page
- Input: Select two characters + scenario
- Output: Simulated dialogue (based on MBTI traits and context)
- Emotional breakdown and interaction report

---

## Functionalities & Modules

- MBTI Profile Loader: `src/utils/personalityLoader.ts`
- Cheat Sheet Engine: `src/components/cheatSheetDisplay.tsx`
- Arc Matcher Engine: `src/logic/arcMatcher.ts`
- Story Folder System: `src/hooks/useStoryStorage.ts`
- Relationship Graph: `src/logic/relationshipMapper.ts`
- AI Simulation Engine: `src/ai/dialogueSimulator.ts`

---

## Database Schema (Supabase)

### Table: users
- user_uuid (PK)
- email
- created_at

### Table: stories
- story_id (PK)
- user_uuid (FK → users.user_uuid)
- title
- description

### Table: characters
- char_id (PK)
- story_id (FK → stories.story_id)
- name
- mbti_type
- assigned_arc
- notes

### Table: relationships
- relation_id (PK)
- char_a_id (FK → characters.char_id)
- char_b_id (FK → characters.char_id)
- relationship_type (enum: crush, enemy, friend, sibling, etc.)
- inferred_impact

### Table: interactions
- interaction_id (PK)
- char_a_id (FK → characters.char_id)
- char_b_id (FK → characters.char_id)
- scenario (text)
- ai_output (text)
- date_created

---

## RLS (Row-Level Security) Rules
- All tables must have RLS enabled.
- Each user can only view and modify:
  - Their own stories
  - Characters associated with their stories
  - Relationships and interactions connected to their characters

---

## Modularity Rules

- Each core feature must be independently modular (e.g. MBTI selector should not rely on character folder logic).
- Use a centralized state management system (e.g. Zustand or Redux).
- Maintain standard naming conventions across all foreign keys (e.g., user_uuid, story_id, char_id).
- All features should default to a no-dependency skeleton before extending functionality.

---

## Development Flow (UX → Functionality → DB → UI)

1. UX Flow Design (Pages, Navigation)
2. Functional Logic Implementation (Profile loading, matching)
3. Database Modeling (Tables & RLS)
4. UI Polish (Styling, Interactivity)
