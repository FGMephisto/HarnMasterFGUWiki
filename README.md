# HarnMaster 3.5E for Fantasy Grounds — User Manual

## Table of Contents

1. [Introduction](#introduction)
2. [The Character Sheet](#the-character-sheet)
   - [Skills Tab](#skills-tab)
   - [Mystic Tab — Magic & Powers](#mystic-tab--magic--powers)
   - [Inventory Tab](#inventory-tab)
   - [Combat Tab — Armor & Penalties](#combat-tab--armor--penalties)
   - [Combat Tab — Injuries](#combat-tab--injuries)
   - [Combat Tab — Strike Locations](#combat-tab--strike-locations)
   - [Actions Tab — Weapons](#actions-tab--weapons)
   - [GM Tab — Background](#gm-tab--background)
3. [Making Rolls](#making-rolls)
4. [Combat](#combat)
   - [Initiative](#initiative)
   - [Attack](#attack)
   - [Defense](#defense)
   - [Damage](#damage)
   - [The Combat Resolution Window](#the-combat-resolution-window)
5. [Magic (Mystic Tab)](#magic-mystic-tab)
6. [Game Master Guide](#game-master-guide)
   - [The Combat Tracker](#the-combat-tracker)
   - [NPCs](#npcs)
   - [Encounters](#encounters)
   - [Party Sheet & XP](#party-sheet--xp)
   - [GM Options](#gm-options)
7. [Reference](#reference)
   - [Attribute Quick Reference](#attribute-quick-reference)
   - [Skill Groups](#skill-groups)
   - [Damage Types](#damage-types)

---

## Introduction

This manual covers the Fantasy Grounds Unity implementation of **HarnMaster 3.5E**. It focuses on how to use the software — what each button does, how the roll sequence works, and how data is laid out — rather than repeating the tabletop rules. Keep your HarnMaster rulebook handy for the underlying mechanics.

---

## The Character Sheet

The character sheet has six tabs:

| Tab | Contents |
|-----|----------|
| **Skills** | All attributes and skills, ML, SB, development |
| **Actions** | Weapons and their attack/defense/damage actions |
| **Combat** | Armor worn, penalty summary |
| **Locations** | Strike location table with armor per location |
| **Mystic** | Convocation spells and rituals |
| **Inventory** | Carried items, encumbrance |
| **GM** | Biographical data (GM-only) |

---

### Skills Tab — Attributes

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

### Skills Tab

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

| Column | Meaning |On the skil
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

### Mystic Tab — Magic & Powers

**This is still under development**

The Mystic tab (labelled **Mystic** in the tab bar) contains the character's magical abilities. HarnMaster magic is convocation-based; the six convocations are:

| Convocation | Element |
|---|---|
| Fyvria | Earth / Nature |
| Jmorvi | Metal / Craft |
| Lyahvi | Light / Illusion |
| Odivshe | Water / Cold |
| Peleahn | Fire / Energy |
| Savorya | Mind / Spirit |

Each spell entry shows:
- **Name**
- **Convocation**
- **Complexity Level**
- **Casting Time**
- **Range / Area**
- **Duration**
- **Summary** — short description
- **Description** / **Bonus Effects** — full text

Click a spell to cast it (rolls the appropriate convocation skill). Fatigue cost is tracked automatically.

---

### Inventory Tab

The Inventory tab lists all items carried. Key columns:
- **WT** — item weight
- **WQ** — weapon quality (for weapons in inventory)
- Encumbrance totals at the bottom update the **Penalty** field, which feeds into the Universal Penalty.

Drag an item into the list to add it. Check the **Equipped** box to mark worn armor — equipped armor feeds its protection values into the strike location armor table automatically.

---

### Combat Tab — Armor & Penalties

The Combat tab summarizes three things:

**Strike location armor** — the strike location table showing B/E/P/F protection values per body location. See [Combat Tab — Strike Locations](#combat-tab--strike-locations) below for the full reference.

**Penalties list** — a summary of active injury penalties feeding into Universal Penalty and Physical Penalty on the main tab.

**Injury list** — all current injuries. See [Combat Tab — Injuries](#combat-tab--injuries) below for the full field reference.

---

### Combat Tab — Injuries

Injuries are listed as a sub-panel on the Combat tab. Click the **Details** button on any injury row to open a popup window with the full injury record. Each injury row records:

| Field | Meaning |
|---|---|
| **Location** | Body part affected |
| **Aspect** | Blunt, Edge, Point, Fire, or Frost |
| **IL (Injury Level)** | Minor, Serious, or Grievous |
| **HR (Healing Rate)** | Days per healing step |
| **Date** | In-game date the injury was received |
| **Infection** | Not infected / Infected |
| **Treatment** | Treated / Untreated |
| **Physician** | Name of treating physician |
| **Bonus** | Physician's bonus to healing |
| **Notes** | Free text |

The injury aspect and level determine the flavour text automatically (e.g., Blunt + Minor = *Bruised*, Edge + Grievous = *Grievous Cut*). Amputations are tracked separately with their own label.

**Bloodloss** appears as a special injury entry when a bleeding wound is active (requires the Bleeders GM option).

Penalties update automatically as injuries are added, removed, or healed. The **Universal Penalty** and **Physical Penalty** on the main tab reflect the current total.

**Healing:** Update the **Healing Rate (HR)** field and advance the **Date** when a healing interval passes. Mark **Treated** once a physician has treated the wound. Infected wounds do not heal until treated.

**Bloodloss (Bleeders option):** When active, a Bleeders injury entry appears automatically for grievous wounds. This must also be treated.

**Amputations:** When the GM option is enabled, certain wound results can trigger amputation. The location is marked **severed** or **unusable** and a condition note is added.

---

### Combat Tab — Strike Locations

This tab shows the character's body map — all named strike locations with their armor values.

| Column | Meaning |
|---|---|
| **Strike Locations** | Body location name (Skull, Face, Neck, Thorax, etc.) |
| **B / E / P / F** | Armor protection at that location by damage type |

During combat resolution, the system rolls on this table (or a High/Low sub-table when an aim zone is active) to determine where a successful hit lands.

---

### Actions Tab — Weapons

The Actions tab is the primary interface for combat. Each weapon entry shows its attack and defense actions.

#### Weapon List

Each weapon entry displays:
- **Name** — weapon or attack name (underlined; click to rename)
- **Attack (sword icon)** — click to make an attack roll; shows current **AML**
- **Defend (shield icon)** — click to make a defense roll; shows current **DML**
- **Damage (fist icon)** — click to roll damage; shows the **B/E/P** dice for the active aspect
- **Damage Aspect icon** — cycles between Blunt, Edge, and Point to select which damage column is active
- **Aim Zone toggle** — cycles between **High**, **Mid** (default), and **Low** to set where the attack is aimed

For ranged and thrown weapons, the row also shows:
- **Range bracket** — current range band (Short / Medium / Long / Extreme)
- **Ammo counter** — tracks remaining ammunition with a pip display; set maximum ammo in the field next to it

#### Weapon Editor

Click the **detail button** (grid icon, right side of each weapon row) to open the weapon editor. This is where you configure a weapon's statistics:

**Stats section**
- **Weapon** — display name
- **WQ / Current** — weapon quality (base) and current condition
- **Note** — free-text note about this attack entry. Can be usd to denote ammo etc..
- **Type** — Melee, Ranged, or Thrown
- **Skill** — the skill name this weapon uses for ML calculation (type to autocomplete from the skill list)
- **A/D/HM** — three fields: Attack modifier, Defense modifier, Handmode penalty. These are added to the base skill ML to compute AML and DML
- **B/E/P** — damage dice for Blunt, Edge, and Point aspects
- **Range S/M/L/E** — range band values in metres (appears for Ranged and Thrown types)

**Properties** — free-text field for notes (special qualities, magical properties, etc.)

#### Adding Attack Entries

Right-click in the weapon list and choose:
- **Add Melee** — adds a melee attack entry
- **Add Ranged** — adds a ranged attack entry
- **Add Throwing** — adds a thrown weapon entry

---

### GM Tab — Background

The GM tab is visible only to the GM and contains biographical information:
- Birthdate, Sunsign, Sunsign (Cusp)
- Species, Gender
- Height, Frame, Weight
- Hair Color, Eye Color, Voice
- Culture, Social Class
- Speed (calculated from MOV)

The **Sunsign** fields matter mechanically — sunsign bonuses appear in the Skills tab against skills that have sunsign affinity.

---

## Making Rolls

All rolls in this ruleset follow the same pattern: roll percentile (d100) and compare to the target number. The system reports one of four outcomes:

| Result | Meaning |
|---|---|
| **Critical Success (CS)** | Roll ≤ ML ending with a five (5) or zero
| **Marginal Success (MS)** | Roll ≤ ML or Roll ≤ 5 |
| **Marginal Failure (MF)** | Roll > ML or Roll > 96 |
| **Critical Failure (CF)** | Roll > ML or Roll > 96, ending with a five (5) or zero |

To roll:
- **Attribute check:** click the roll button next to an attribute on the Skills tab
- **Skill check:** click the roll button on the Skills tab
- **Attack:** click the sword button on the Actions tab (or drag it to a target)
- **Defense:** click the shield button (or use the prompt that appears after an incoming attack)
- **Damage:** click the fist/damage button

The **chat window** shows the full breakdown: the roll, the target (ML), any modifiers, and the outcome label.

### The Modifier Box

The **Modifier Box** is a floating panel on the FGU desktop (bottom-centre by default). It lets you stack bonuses and presets onto the next roll before you click anything on the character sheet. Modifiers clear automatically after each roll.

**Numeric modifier:** Type a positive or negative number into the box to add a flat bonus or penalty to the roll target.

**Preset buttons — SB Multiplier (×2 through ×7):**

HarnMaster skill and attribute checks are resolved by comparing a d100 roll against a target derived from the character's Skill Base. The default multiplier is **×5** (ML = SB × 5 + development). Activate one of the MULT presets *before* rolling to change this:

| Preset | Effect on skill/attribute check |
|---|---|
| **×2** | Target = SB × 2 (very hard task) |
| **×3** | Target = SB × 3 (hard task) |
| **×4** | Target = SB × 4 (moderate task) |
| **×5** | Target = SB × 5 — **default** (standard task) |
| **×6** | Target = SB × 6 (easy task) |
| **×7** | Target = SB × 7 (trivial task) |

For **damage rolls**, the same MULT presets multiply the number of dice in the roll: ×2 adds a second set of the weapon's damage dice to the pool (e.g., a 1d6 weapon rolls 2d6), ×3 adds a third set, and so on. All dice are rolled together in a single roll. Use this for mounted charges, special manoeuvres, or other rules that call for multiplied damage.

---

## Combat

HarnMaster combat in Fantasy Grounds is a three-step sequence per exchange: **Attack → Defense → Damage**. The results of all three are held and then resolved together in the **Combat Resolution Window**.

### Initiative

Before combat begins, set initiative for all participants.

- Right-click a combatant in the **Combat Tracker** and choose **Set Initiative**.
- **Set All Initiatives** rolls initiative for everyone at once.
- **Set NPC Initiatives** / **Set PC Initiatives** roll only for the selected group.

Initiative is derived from the character's initiative skill and relevant modifiers.
Initiative can also be set manually per combatant in the Initiative field.

### Attack

1. On the attacker's Actions tab, click the **sword button** next to the weapon to use.
2. The roll is sent to chat showing the AML, the d100 result, and the outcome (CS/MS/MF/CF).
3. If an attack target is set in the Combat Tracker, the result is automatically associated with that defender.

**Aim Zone:** Before attacking, click the aim zone toggle on the weapon row to choose **High**, **Mid**, or **Low**. This shifts the hit location table used during resolution.

### Defense

After an attack lands, the defender is prompted to choose a defense action:

| Defense | Effect |
|---|---|
| **Block** | Roll DML; success reduces or cancels the attacker's success |
| **Counterstrike** | Roll an attack in return; both results are compared simultaneously |
| **Dodge** | Roll AGL-based dodge skill; success avoids the attack |
| **Ignore** | No defense roll; attack resolves at full effectiveness |

The defense roll result (CS/MS/MF/CF) is held alongside the attack result.

### Damage

After the defense resolves, the attacker rolls damage by clicking the **damage button**. Damage is rolled according to the active aspect (B/E/P) displayed on the weapon row.

---

## Game Master Guide

### The Combat Tracker

Open the Combat Tracker from the toolbar. Key HarnMaster additions:

- **Locations** — each combatant's strike location table is accessible from their CT entry
- **Injuries** — a compact injury list is visible without opening the full character sheet
- **FT (Fatigue)** — shown inline for quick reference

**Running combat from the CT:**
- Set initiative and sort the list.
- Click a combatant's token to select them as the active attacker.
- Right-click a target token and choose **Target** to link attacker to defender.
- Use the weapon buttons on the CT entry to roll attack and damage directly without opening the full sheet.

### The Combat Resolution Window

The **Combat Resolution Window** opens for the GM as soon as the attack roll resolves, targeting the defender. It updates progressively as the defense roll and then the damage roll come in. Players see a running summary in chat.

The window shows:
- **Attack Outcome** — the attacker's success level
- **Defense Action** and **Defender Test** — what the defender chose and their roll result
- **Result** — the final outcome from the attack/defense matrix (e.g., attacker CS vs. defender Block MF = attacker wins decisively)
- **Total Impact** — effective damage after armor at the struck location is subtracted
- **Effective Impact** and **Injury Level** — the resulting IL (Minor / Serious / Grievous / Amputation)
- **Strike Location** — the location roll result; click to override

The injury is applied to the defender's injury list automatically. Penalties update immediately.

### NPCs

Create NPCs from **NPCs** in the sidebar. The NPC main tab is divided into four panels stacked vertically: a summary header, an attributes grid, a skills field, and an actions list.

**Attributes:** Displayed as a compact grid, identical in structure to the PC sheet. Each row shows the attribute abbreviation and score. Click the roll button to make an attribute check.

**Skills:** A single free-text field labelled **Skills**. Type skill names and their ML values directly (e.g. `Sword 65, Riding 42`). The field supports multi-roll — clicking a skill name or value in the rendered text opens a roll prompt for that skill, so the GM can roll directly from the field without opening a separate window.

**Actions:** A list of free-text action entries under the **ACTIONS** header. Each entry has a bold **name** line and a free-text **description** block below it. Use the **+** button (top-right of the header) to add a new entry; use the edit (pencil) button to enter delete mode. Actions are narrative — they do not link to the structured weapon system used by PCs. For weapon attacks on NPCs, add weapon entries via drag-and-drop as described below.

**Adding weapons:** Drag a weapon item from the library or an inventory list onto the NPC's Actions to add a weapon entry. After dropping, some auto-filled fields may need tidying — right-click a weapon row for options to clean up or remove entries.

**Hit Locations:** Click **Add default Strike Locations** on the NPC's Locations tab to populate a standard humanoid hit-location table. The button warns before overwriting any existing custom data.

**Armor refresh:** After equipping armor items, click **Refresh Armor Values** to push the armor stats into the Strike Location table.

**Shorthand IDs:** Each location row has a short **Loc** code which is used to apply worn armor correctly. You can also enable **Manual Override** per row to lock a value against global refreshes.

**Importing NPC data:** NPC stat blocks can be imported from HarnMaster source modules. Be aware that HarnMaster source files do not use a consistent format across products, so imported values may land in the wrong fields or be missing entirely. Always review an imported NPC's attributes, skills, and weapon entries before use and correct any discrepancies manually.

### Encounters

Build encounters from the **Encounters** module. Drag NPC entries into an encounter, then push the encounter to the Combat Tracker with one click when the players engage.

### Party Sheet & XP

Open the Party Sheet from the toolbar. It shows all PCs in the campaign with their key derived stats. The GM can award XP from here; individual EXP values on each PC sheet update accordingly.

### GM Options

Under **Settings → Options → HarnMaster Rules**, several optional rules can be toggled:

| Option | Effect |
|---|---|
| **Combat: Knockbacks** | Enables knockback rolls on high-impact hits |
| **Combat: Limb injuries** | Tracks limb-specific injury effects (unusable limbs) |
| **Combat: Amputations** | Enables amputation outcomes for grievous limb hits |
| **Combat: Bleeders** | Adds ongoing blood-loss tracking for grievous wounds |

These options are off by default. Enable them at campaign start for a grittier game.

---

## Reference

### Attribute Quick Reference

| Abbr. | Full Name | Primary Uses |
|---|---|---|
| AGL | Agility | Physical skills, dodge, initiative |
| AUR | Aura | Convocation magic, piety |
| CML | Comeliness | Social interactions |
| DEX | Dexterity | Fine motor skills, craft |
| END | Endurance | Fatigue resistance, condition |
| EYE | Eyesight | Awareness, ranged combat |
| HRG | Hearing | Awareness |
| INT | Intelligence | Lore, languages, mental skills |
| MOR | Morality | Piety, religion skills |
| MOV | Move | Speed, travel rate |
| SML | Smell | Awareness |
| STA | Stamina | Health, shock resistance |
| STR | Strength | Melee damage, carry weight |
| VOI | Voice | Communication skills |
| WIL | Will | Mental conflict, magic resistance |

### Skill Groups

| Group | Example Skills |
|---|---|
| Physical | Acrobatics, Climbing, Dodge, Stealth, Swimming |
| Communication | Acting, Intrigue, Oratory, Rhetoric, Singing |
| Language | Harnic, Ivinian, Jarinese, Orbaalese, and 20+ others |
| Religion | Piety skills per deity |
| Combat | Axe, Bow, Dagger, Shield, Sword, Unarmed, and others |
| Crafts & Lore | Cookery, Drawing, Fishing, Folklore, Physician |
| Convocation | Fyvria, Jmorvi, Lyahvi, Odivshe, Peleahn, Savorya |
| Generic | Miscellaneous custom skills |

### Damage Types

| Code | Full Name | Injury Labels (Minor / Serious / Grievous) |
|---|---|---|
| B | Blunt | Bruised / Fractured / Crushed |
| E | Edge | Minor Cut / Serious Cut / Grievous Cut |
| P | Point | Minor Stab / Serious Stab / Grievous Stab |
| F | Fire | Minor Burn / Serious Burn / Grievous Burn |
| *(Frost)* | Frost | Minor Frost / Serious Frost / Grievous Frost |
