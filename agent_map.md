# agent_map.md

## Overview
This document maps the smart agents used in **PersonaForge**. Each agent is described with its inputs, outputs, connected files, and purpose. These agents are powered by Lovable.dev and extend the core MBTI and character arc data into dynamic, generative storytelling tools.

---

## Agents

### 1. MBTI Arc Validator
- **Purpose:** Ensures that every selected MBTI type has at least one valid arc assigned. Suggests alternatives if none exist.
- **Inputs:**  
  - MBTI type (string)  
  - Arc mappings (`data/mbti_arc_compatibility.json`)  
  - Arc definitions (`data/arc_blueprints.json`)  
- **Outputs:**  
  - Validation report (valid/invalid)  
  - List of compatible arcs  
  - Suggestions for missing mappings  
- **Connected Files:**  
  - `data/mbti_profiles.json`  
  - `data/mbti_arc_compatibility.json`  
  - `data/arc_blueprints.json`

---

### 2. Relationship Simulator
- **Purpose:** Generates dialogue, subtext, and compatibility insights between two characters based on MBTI and relationship type.
- **Inputs:**  
  - Character A MBTI  
  - Character B MBTI  
  - Relationship type (string)  
  - Scenario context (optional)  
- **Outputs:**  
  - Dialogue snippet (6–10 lines)  
  - Subtext summary (1–2 lines)  
  - Compatibility rating (optional)  
- **Connected Files:**  
  - `data/mbti_relationships_repaired.json`  
  - `logic_templates/ai_dialogue_prompts.txt`

---

### 3. Triangle Builder
- **Purpose:** Creates narrative triangles (love, friendship, rivalry) between 3 characters, assigning arcs and explaining dynamics.
- **Inputs:**  
  - 3 MBTI profiles  
  - Optional arcs  
- **Outputs:**  
  - Relationship map (JSON)  
  - Written justification (Markdown)  
  - Suggested scenarios for tension  
- **Connected Files:**  
  - `data/mbti_profiles.json`  
  - `data/mbti_arc_compatibility.json`  
  - `data/arc_blueprints.json`

---

### 4. Narrative Prompt Engine
- **Purpose:** Combines MBTI, arcs, and universal scenarios to generate creative writing prompts or backstory hooks.
- **Inputs:**  
  - MBTI type(s)  
  - Arc(s)  
  - Scenario from `logic_templates/ai_dialogue_prompts.txt`  
- **Outputs:**  
  - Writing prompt (1–2 sentences)  
  - Extended backstory idea (optional)  
- **Connected Files:**  
  - `logic_templates/ai_dialogue_prompts.txt`  
  - `data/arc_blueprints.json`

---

## Future Agents (Planned)
- **Conflict Analyzer**: Predicts points of tension between MBTI types and arcs.  
- **Story Seed Generator**: Builds story outlines from ensembles of saved characters.  
- **Evolution Predictor**: Projects how characters may evolve over time given MBTI + arc data.  

---

## Notes
- All agents should be modular and reference existing JSON files directly.  
- Inputs/outputs should remain consistent so they can feed into the app’s story folders and character sheets seamlessly.  
- Agents can be extended in `/agents/` folder with JSON, TS, or prompt templates for clarity.
