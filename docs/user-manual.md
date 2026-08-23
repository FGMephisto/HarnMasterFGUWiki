# HarnMaster 3.5E for Fantasy Grounds — User Manual

## Table of Contents

1. [Introduction](#introduction)
2. [The Character Sheet](#the-character-sheet)
   - [Skills Tab — Attributes](#skills-tab-attributes)
   - [Skills Tab](#skills-tab)
   - [Mystic Tab — Magic & Powers](#mystic-tab-magic-powers)
   - [Inventory Tab](#inventory-tab)
   - [Combat Tab — Armor & Penalties](#combat-tab-armor-penalties)
   - [Combat Tab — Injuries](#combat-tab-injuries)
   - [Combat Tab — Strike Locations](#combat-tab-strike-locations)
   - [Actions Tab — Weapons](#actions-tab-weapons)
   - [GM Tab — Background](#gm-tab-background)
3. [Making Rolls](#making-rolls)
   - [The Modifier Box](#the-modifier-box)
4. [Combat](#combat)
   - [Initiative](#initiative)
   - [Attack](#attack)
   - [Defense](#defense)
   - [Damage](#damage)
   - [Shock Rolls](#shock-rolls)
5. [Game Master Guide](#game-master-guide)
   - [The Combat Tracker](#the-combat-tracker)
   - [Combat Resolution](combat-resolution.md)
   - [NPCs](#npcs)
   - [Encounters](#encounters)
   - [GM Options](#gm-options)

---

## Introduction

This manual covers the Fantasy Grounds Unity implementation of **HarnMaster 3.5E**. It focuses on how to use the software — what each button does, how the roll sequence works, and how data is laid out — rather than repeating the tabletop rules. Keep your HarnMaster rulebook handy for the underlying mechanics.

---

## The Character Sheet

The character sheet has six tabs:

| Tab | Contents |
|---|---|
| **Skills** | All attributes and skills, ML, SB, development |
| **Actions** | Weapons and their attack/defense/damage actions |
| **Combat** | Armor worn, penalty summary |
| **Locations** | Strike location table with armor per location |
| **Mystic** | Convocation spells and rituals |
| **Inventory** | Carried items, encumbrance |
| **GM** | Biographical data (GM-only) |

---

### Skills Tab — Attributes {#skills-tab-attributes}

The top portion of the Skills tab always shows the character's fifteen attributes in a compact grid.

**Main view (compact):** Each row shows the attribute abbreviation and its **Total** score — the final value used in play. Click the roll button to make an attribute roll. The roll can be adjusted using the Modifier Box (see below).

**Attribute Editor (detail popup):** Click the **Details** button (top-right of the ATTRIBUTES header) to open the attribute editor in a separate window. Each row there shows:

| Column | Meaning |
|---|---|
| **Name** | Full attribute name |
| **Base** | The raw value set during character creation — editable |
| **Mod.** | A flat bonus (from species, magic, etc.) — editable |
| **Total** | Computed final value (Base + Mod.) — read-only |

---

### Skills Tab {#skills-tab}

Below the attributes, the same tab shows the character's skill list in compact form.

**Main view (compact):** Each row shows:

| Column | Meaning |
|---|---|
| **Name** | Skill name (with speciality appended if set) |
| **SB** | Skill Base — computed from the linked attributes |
| **ML** | Mastery Level — the number rolled against; click to roll |

Skills are grouped by skill group (Physical, Combat, etc.). Use the filter box at the bottom to search by name.

**Rolling a skill:** Click the roll button on the right of any skill row to send the roll to chat.

**Detailed Skills Window:** Click the **Details** button (top-right of the SKILLS header) to open the full skill editor in a wider popup window. Each row there shows all fields:

| Column | Meaning |
|---|---|
| **Name** | Skill name |
| **Speciality** | Optional specialization within the skill |
| **Skill Group** | Category (Physical, Combat, Crafts & Lore, etc.) |
| **Attributes** | The attributes the SB is derived from (up to three) |
| **Sunsigns** | Sunsign bonus value (if applicable) |
| **OML** | Opening Mastery Level — the initial ML at skill acquisition |
| **SB** | Skill Base — computed, read-only |
| **Dev.** | Development ranks added through play — editable |
| **ML** | Mastery Level — computed final value |

The detailed window also has a **Development Roll** button per row (the dice icon next to ML). Use this to test whether the skill improves.

---

### Mystic Tab — Magic & Powers {#mystic-tab-magic-powers}

> *Note: Mystic powers and spellcasting features are currently in active development.*

The Mystic tab contains the character's magical abilities. HarnMaster magic is convocation-based:

| Convocation | Element |
|---|---|
| **Fyvria** | Earth / Nature |
| **Jmorvi** | Metal / Craft |
| **Lyahvi** | Light / Illusion |
| **Odivshe** | Water / Cold |
| **Peleahn** | Fire / Energy |
| **Savorya** | Mind / Spirit |

Each spell entry displays:

- **Name** — Title of the spell
- **Convocation** — Spell convocation
- **Complexity Level** — Casting difficulty rating
- **Casting Time** — Action duration
- **Range / Area** — Distance and area of effect
- **Duration** — How long the effect lasts
- **Summary** — Short description
- **Description / Bonus Effects** — Full spell rules and enhancements

Click a spell to cast it (rolls the appropriate convocation skill). Fatigue cost is tracked automatically.

---

### Inventory Tab {#inventory-tab}

The Inventory tab lists all items carried. Key fields:

- **WT** — Item weight
- **WQ** — Weapon Quality (for weapons in inventory)
- **Penalty** — Encumbrance penalty calculated from total carried weight (feeds into Universal Penalty)

Drag an item into the list to add it. Check the **Equipped** box to mark worn armor — equipped armor feeds its protection values into the strike location armor table automatically.

---

### Combat Tab — Armor & Penalties {#combat-tab-armor-penalties}

The Combat tab summarizes three key systems:

1. **Strike location armor** — The strike location table showing B/E/P/F protection values per body location. See [Combat Tab — Strike Locations](#combat-tab-strike-locations) below.
2. **Penalties list** — A summary of active injury penalties feeding into Universal Penalty and Physical Penalty.
3. **Injury list** — All current wounds. See [Combat Tab — Injuries](#combat-tab-injuries) below.

---

### Combat Tab — Injuries {#combat-tab-injuries}

Injuries are listed as a sub-panel on the Combat tab. Click the **Details** button on any injury row to open the full injury record:

| Field | Meaning |
|---|---|
| **Location** | Body part affected |
| **Aspect** | Blunt, Edge, Point, Fire, or Frost |
| **IL (Injury Level)** | Minor, Serious, or Grievous |
| **HR (Healing Rate)** | Days per healing step |
| **Date** | In-game date the injury was received |
| **Notes** | Free-text notes |

The injury aspect and level determine the descriptive label automatically (e.g., Blunt + Minor = *Bruised*, Edge + Grievous = *Grievous Cut*).

- **Penalties**: Update automatically as injuries are added, removed, or healed.
- **Healing**: Update the **Healing Rate (HR)** field and advance the **Date** when a healing interval passes.
- **Bloodloss (Bleeders Option)**: When active, a Bleeders injury entry appears automatically for grievous wounds.
- **Amputations**: When enabled, severe hits can trigger amputation conditions.

---

### Combat Tab — Strike Locations {#combat-tab-strike-locations}

This tab shows the character's body map — all named strike locations with their armor values:

| Column | Meaning |
|---|---|
| **Strike Locations** | Body location name (Skull, Face, Neck, Thorax, etc.) |
| **B / E / P / F** | Armor protection at that location for Blunt, Edge, Point, and Fire |

During combat resolution, the system rolls on this table (or a High/Low sub-table when an aim zone is active) to determine where a hit lands.

---

### Actions Tab — Weapons {#actions-tab-weapons}

The Actions tab is the primary interface for combat rolls.

#### Weapon Row Controls

| Control | Function |
|---|---|
| **Name** | Weapon or attack name (underlined; click to rename) |
| **Attack (Sword icon)** | Click to make an attack roll; shows current **AML** |
| **Defend (Shield icon)** | Click to make a defense roll; shows current **DML** |
| **Damage (Fist icon)** | Click to roll damage; shows dice for the active aspect |
| **Damage Aspect** | Cycles between **Blunt**, **Edge**, and **Point** |
| **Aim Zone** | Cycles between **High**, **Mid** (default), and **Low** |
| **Range Bracket** | Current range band (*Short*, *Medium*, *Long*, *Extreme*) for ranged/thrown weapons |
| **Ammo Counter** | Tracks remaining ammunition with a pip display |

#### Weapon Editor (Detail Popup)

Click the **detail button** (grid icon, right side of each weapon row) to configure weapon stats:

| Field | Meaning |
|---|---|
| **Weapon** | Display name |
| **WQ / Current** | Base Weapon Quality and current condition rating |
| **Note** | Free-text notes (e.g. ammo type, special rules) |
| **Type** | *Melee*, *Ranged*, or *Thrown* |
| **Skill** | Base skill used for ML calculation |
| **A / D / HM** | Attack modifier, Defense modifier, and Handmode penalty |
| **B / E / P** | Base damage dice for Blunt, Edge, and Point aspects |
| **Range S/M/L/E** | Range thresholds in metres |
| **Properties** | Notes on special qualities or magical attributes |

#### Adding Attack Entries

Right-click in the weapon list and choose:

- **Add Melee** — Adds a melee weapon entry
- **Add Ranged** — Adds a ranged weapon entry
- **Add Throwing** — Adds a thrown weapon entry

---

### GM Tab — Background {#gm-tab-background}

The GM tab is visible only to the GM and tracks character background:

- **Birthdate**, **Sunsign**, **Sunsign (Cusp)**
- **Species**, **Gender**
- **Height**, **Frame**, **Weight**
- **Hair Color**, **Eye Color**, **Voice**
- **Culture**, **Social Class**
- **Speed** (calculated from MOV)

Sunsign affinities automatically grant bonuses to matching skills on the Skills tab.

---

## Making Rolls

All rolls in HarnMaster follow a percentile (d100) test compared against the target Mastery Level (ML):

| Result | Meaning |
|---|---|
| **Critical Success (CS)** | Roll ≤ ML ending in 5 or 0 |
| **Marginal Success (MS)** | Roll ≤ ML (or natural 01–05) |
| **Marginal Failure (MF)** | Roll > ML (or natural 96–00) |
| **Critical Failure (CF)** | Roll > ML ending in 5 or 0 |

How to roll:

- **Attribute check**: Click the roll button next to an attribute on the Skills tab
- **Skill check**: Click the roll button on the Skills tab
- **Attack**: Click the sword button on the Actions tab
- **Defense**: Click the shield button
- **Damage**: Click the damage button

### The Modifier Box

The **Modifier Box** is a floating desktop panel that applies situational modifiers to the next roll:

- **Numeric modifier**: Type any number to add a flat bonus or penalty.
- **SB Multipliers (×2 through ×7)**: Multiplies Skill Base for difficulty scaling:

| Preset | Target Difficulty |
|---|---|
| **×2** | Target = SB × 2 (Very Hard) |
| **×3** | Target = SB × 3 (Hard) |
| **×4** | Target = SB × 4 (Moderate) |
| **×5** | Target = SB × 5 — **Default** (Standard) |
| **×6** | Target = SB × 6 (Easy) |
| **×7** | Target = SB × 7 (Trivial) |

For **damage rolls**, multiplier buttons multiply the number of damage dice rolled together.

---

## Combat

Combat resolves in three distinct steps: **Attack → Defense → Damage**.

### Initiative

- Right-click a combatant in the **Combat Tracker** and select **Set Initiative**.
- Use **Set All Initiatives**, **Set NPC Initiatives**, or **Set PC Initiatives**.

### Attack

1. Click the **sword button** on the Actions tab.
2. The attack roll posts to chat with the AML, d100 roll, and outcome (CS/MS/MF/CF).
3. Set the **Aim Zone** (High, Mid, Low) prior to rolling if targeting specific body regions.

### Defense

The defender responds by choosing one of four tactical actions:

| Defense | Effect |
|---|---|
| **Block** | Uses weapon/shield defense ML to deflect the attack |
| **Counterstrike** | Attacks in return; both rolls resolve simultaneously |
| **Dodge** | Uses Agility-based dodge to evade |
| **Ignore** | Takes no action; attack resolves at maximum effectiveness |

### Damage

The attacker rolls damage via the **damage button** according to the active aspect (Blunt, Edge, Point).

### Shock Rolls

Taking an injury automatically triggers a Shock Roll:

| Current State | Roll Outcome | Resulting State |
|---|---|---|
| **Normal** | Fail | → **Unconscious** + **Prone** |
| **Unconscious** | Pass | → **Incapacitated** + immediate second check |
| **Incapacitated** | Fail | → **Shock** |
| **Incapacitated** | Pass | → Conditions removed (Recovered) |

---

## Game Master Guide

### The Combat Tracker

Key HarnMaster features on the Combat Tracker:

- **Locations**: Quick access to strike location tables and current armor values
- **Injuries**: Summary of active wounds and current penalty total
- **Fatigue (FT)**: Inline fatigue tracking

**Running combat from the Combat Tracker:**

- **Set initiative**: Set initiative and sort the tracker list.
- **Select active combatant**: Click their token or tracker entry to activate.
- **Target opponent**: Drag the target crosshair to link attacker to defender.
- **Roll directly**: Use weapon buttons on the CT entry to roll attack and damage directly without opening the full sheet.

---

### Combat Resolution

Combat interactions (attack vs. defense, hit location determination, armor mitigation, and injury generation) are resolved using the dedicated **Combat Resolution Window**.

👉 **For complete details and a step-by-step walkthrough, see the [Combat Resolution](combat-resolution.md) guide.**

### NPCs

Create NPCs from the **NPCs** sidebar menu:

- **Attributes**: Compact grid identical to PC sheets
- **Skills**: Free-text multi-roll field (e.g. `Sword 65, Riding 42`)
- **Actions**: Narrative actions and abilities list
- **Weapons**: Drag and drop weapon items directly into the Actions section
- **Hit Locations**: Click **Add default Strike Locations** to populate humanoid location tables
- **Armor Values**: Click **Refresh Armor Values** after equipping armor

### Encounters

Build encounters in the **Encounters** module and push them directly to the Combat Tracker when combat begins.

### GM Options

Under **Settings → Options → HarnMaster Rules**:

| Option | Effect |
|---|---|
| **Combat: Knockbacks** | Enables knockback rolls on heavy impact hits |
| **Combat: Limb injuries** | Tracks unusable limb conditions |
| **Combat: Amputations** | Enables amputation outcomes on grievous limb wounds |
| **Combat: Bleeders** | Adds blood-loss tracking for severe wounds |
