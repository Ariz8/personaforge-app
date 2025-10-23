# PersonaForge

PersonaForge is a character development app for writers, game designers, and creators who want to craft psychologically authentic, story-driven characters using the Myers-Briggs Type Indicator (MBTI) system, narrative arc templates, and intelligent inter-character simulations.

---

## 🧠 Purpose

This app empowers storytellers to create layered, believable characters by integrating deep psychological archetypes (MBTI), simplified but potent story arcs, and dynamic relationship tracking. Whether you're writing a novel, building a game, or creating a webcomic, PersonaForge is your creative co-pilot.

---

## ✨ Concept

PersonaForge merges three powerful storytelling tools into one platform:

1. **MBTI-Based Character Creation** – Select from 16 personality types, each with predefined cognitive stacks, love languages, conflict styles, and dialogue patterns.
2. **Protagonist Arc Blueprint System** – Choose from a library of narrative arcs to guide character development across stories.
3. **Story Folders & Character Management** – Group characters by story, track their development, and organize their details in one place.
4. **Relationship Dynamics Engine** *(coming soon)* – Define emotional bonds, rivalries, and love triangles between characters, with automated narrative implications.
5. **AI Dialogue Simulator** *(coming soon)* – Drop two characters into a scenario and generate authentic interactions based on their MBTI profiles.

---

## 🚀 Setup Instructions (Optional)

To run this project locally or contribute:
1. Clone the GitHub repository.
2. Connect to a Supabase project (schema in `schemas/supabase_schema.sql`).
3. Add seed data from `data/mbti_profiles.json` and `arc_blueprints.json`.
4. Launch the frontend via your preferred framework (e.g., Next.js, Vite, etc.).

> This project is designed for integration with [Lovable.dev](https://www.lovable.dev), a low-code AI-assisted platform. If you're using Lovable, connect this repo and execute instructions via `request.txt`.

---

## 🎯 Vision

To become the go-to creative tool for authors, worldbuilders, and storytellers who want to bring emotionally intelligent characters to life. We envision this app as a modular hub that connects to future tools like worldbuilding platforms, dialogue engines, and RPG systems.

---

## 💼 Use Cases

- Novelists building rich cast ensembles.
- Screenwriters plotting love triangles and rivalries.
- Game designers scripting companion behavior.
- Worldbuilders linking personalities to lore systems.
- Writing teachers and students exploring character arcs.

---

## 📬 Contributions Welcome

If you'd like to contribute arcs, personality data, or help improve features—open an issue or submit a pull request! We aim to build a community-driven character creation ecosystem.

## 🤖 Lovable Smart Agents

PersonaForge integrates with [Lovable.dev](https://www.lovable.dev) to leverage AI agents that extend beyond static data. These agents provide dynamic logic for personality-driven storytelling, ensuring creators can simulate, validate, and explore character interactions in real time.

### 📌 Current Agents

| Agent Name | Purpose | Data Sources |
|------------|---------|--------------|
| **MBTI Arc Validator** | Ensures that every selected MBTI type is linked to at least one compatible arc. Returns alignment scores, alternative arcs, and suggestions when gaps are found. | `data/mbti_profiles.json`, `data/character_arc_mbti_mapping.json`, `data/character_arcs_option_b.json` |
| **Relationship Simulator** | Generates dialogue snippets, emotional subtext, and compatibility notes between two characters based on MBTI and relationship type. Useful for love triangles, rivalries, or alliances. | `data/mbti_relationships_repaired.json`, `logic_templates/ai_dialogue_prompts.txt` |
| **Triangle Builder** | Automatically builds narrative triangles (love/friendship/antagonist sets) by pairing MBTI profiles with arcs. Produces justification and writing prompts for each connection. | MBTI + Arc datasets |
| **Narrative Prompt Engine** | Combines MBTI types, arcs, and universal situations into rich writing prompts or backstory seeds. Assists authors when characters need to be thrown into unexpected scenarios. | `logic_templates/ai_dialogue_prompts.txt`, scenario templates |

### 🛠️ How Agents Work

- **Trigger:** Agents run when prompted in Lovable’s chat or when workflows reference `request.txt`.  
- **Behavior:** They consume the structured JSON data in `/data` and `/logic_templates`, then generate validated outputs or writing suggestions.  
- **Integration:** Their outputs feed directly into PersonaForge’s character sheets, story folders, and simulation tools.  

### 🔮 Future Agents

- **Conflict Analyzer**: Predicts points of tension between MBTI types and arcs.  
- **Story Seed Generator**: Builds short summaries of possible stories based on saved character ensembles.  
- **Evolution Predictor**: Outlines how a character may change over time given their MBTI and assigned arc.  
