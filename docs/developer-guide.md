# Developer Guide

This guide provides an overview of the code architecture and script managers for the HarnMaster 3.5E ruleset.

---

## Project Structure

The ruleset follows the standard Fantasy Grounds XML / Lua layered architecture with `base.xml` as the master entry point.

### Key Directories

| Directory | Purpose |
| :--- | :--- |
| **`scripts/`** | Global script packages (`manager_*.lua`) and static dataset definitions (`data_*.lua`). |
| **`campaign/`** | Window classes and XML definitions for Characters, NPCs, Items, Injuries, and Records. |
| **`ct/`** | Combat Tracker layouts and scripts (`ct_host_hm3.xml`, `ct_client_hm3.xml`). |
| **`utility/`** | Resolution windows and dialogs (Combat Resolution, Medical Resolution). |
| **`graphics/`** | UI frames, icons, buttons, and asset definitions. |
| **`strings/`** | String tables and localization resources. |

---

## Core Script Managers

Global script packages are registered in `base.xml` under their package names:

### Core & System Logic
* **`GameSystem`** (`scripts/manager_gamesystem_hm3.lua`): System-specific constants (Attributes, Currencies, Actions).
* **`DataCommon`** (`scripts/data_common_hm3.lua`): Static lookup tables (Combat matrices, skill defaults, sunsign mods).

### Combat & Action Pipeline
* **`CombatManager2`** (`scripts/manager_combat2_hm3.lua`): Combat Tracker orchestration, initiative, and turn progression.
* **`CombatResolutionManager`** (`scripts/manager_combat_resolution_hm3.lua`): Matrix lookup and opposed check comparison.
* **`HitLocationManager`** (`scripts/manager_hitlocations_hm3.lua`): Zone logic (High/Mid/Low) and body part hit location resolution.
* **`ActionAttack`** (`scripts/manager_action_attack_hm3.lua`): Attack actions, weapon specs, and modifier application.
* **`ActionDefend`** (`scripts/manager_action_defend_hm3.lua`): Defense actions (Block, Dodge, Counterstrike).
* **`ActionDamage`** (`scripts/manager_action_damage_hm3.lua`): Effective impact calculations, armor penetration, and wound creation.

### Medical & Injuries
* **`MedicalManager`** (`scripts/manager_medical_hm3.lua`): Medical checks, triage resolution, and treatment tracking.

### Characters & Skills
* **`CharManager`** (`scripts/manager_char_hm3.lua`): Character lifecycle, attribute updates, and skill base calculations.
* **`ActionSkill`** (`scripts/manager_action_skill_hm3.lua`): Percentile test resolution against Mastery Levels (ML).
* **`LanguageManagerHM3`** (`scripts/manager_language_hm3.lua`): Spoken and written language fluency checks.

---

## UI Architecture & Conventions

* **Window Classes**: Formatted XML with layered controls (`subwindow`, `stringfield`, `numberfield`, `buttoncontrol`).
* **Templates**: Shared elements defined in `campaign/template_char_hm3.xml` and CoreRPG base templates.
* **Script Scoping**: Global managers are accessed directly by name (e.g., `CombatResolutionManager.getMatrixResult(...)`).
