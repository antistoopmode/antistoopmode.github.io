---
title: Stats for Beginners
layout: default
nav_order: 1
---

# Stats for Beginners
## Attributes
You are able to allocate 4 Attribute Points per level (400 in total) into the following Attributes:

- Strength: +1% Strength, +1 Additive Physical Damage per point
- Dexterity: +0.25% Critical Strike Damage, +5 Attack Rating per point
- Energy: +4 Mana per point
- Armor: +5 Defense per point
- Vitality: +5 Life per point

## Offensive Stats

### (Attack) Damage

The amount of Attack Damage you deal with Attack or Hybrid Skills when you hit an enemy (per weapon). This value includes all Additive Damage stats as well as Enhanced Damage.

### Attack Rating
The chance of hitting an enemies with an Attack or Hybrid Skill.

{: .warning }
TODO: 
- EXPLAIN CALCULATION: % Chance to hit = clamp(2 * (_AR / (_AR + _DR)) * (_Alvl / (_Alvl + _Dlvl)), 0.05, 0.95) * 100
- CALCULATE REQUIRED ATTACK RATING TO HIT THE HIGHEST MONSTER LEVEL WHILE IGNORING THEIR DEFENSE (WITH A 95% CHANCE)
- CALCULATE REQUIRED ATTACK RATING TO HIT THE UBER OR WH BOSS WITH THE HIGHEST DEFENSE (WITH A 95% CHANCE)

Notes: 
- The chance is at least 5% and at most 95%.
- The Player's level is always +10 when attacking

### Increased Attack Rating
Increases the Attack Rating stat percentually.

### Attack Speed

Increases the amount of Attacks per Second you can perform. Attack Speed increases the Atacks per Second performed by 0.01 per percent.

Example:

```
// Gear
Weapon 1: 1.50 APS (includes no additional Attack Speed)  
Weapon 2: 1.64 APS (includes +9% Attack Speed)  
Armor: +10% Attack speed

// Total APS
Attacks per Second: 1.60 / 1.74
```

Notes:
- There are no diminishing returns
- There is no cap in Attack Speed or Attacks per Second 
- Attack Speed on a weapon only affects the speed of that specific weapon, while Attack Speed from other sources affects all equipped weapons. Attack Speed from the weapon and other sources are additive.
- Increases in Attacks per Second from Attack Speed are always calculated using 1 Attack per Second and therefore the scaling is linear.
- The Attacks per Second on the weapon tooltip already include any Attack Speed on the weapon itself

### Additive Damage

**Additive Physical Damage:**

The amount of Physical damage added to your Attacks. This stat is affected by the (Physical) Damage Reduction of the enemy.

{: .warning }
TODO: 
- Check if enemies have (Physical) Damage Reduction

**Additive [Magic/Cold/Fire/Poison/Lightning] Damage:**

The amount of [Magic/Cold/Fire/Poison/Lightning] damage added to your Attacks. This stat is affected by the [Magic/Cold/Fire/Poison/Lightning] Resistance of the enemy.

### Critical Strike Chance
The chance to deal a Critical Strike with Physical Attacks.

Notes:
- The base Critical Strike Chance is 5%

### Critical Strike Damage
The amount of Critical Strike Damage you deal when you trigger a Critical Strike with Physical Attacks.

Notes:
- The base Critical Strike Damage is 25%

{: .warning }
TODO: 
- CLARIFY IF THE CRITICAL STRIKE DAMAGE AFFECTS ALL OF THE ATTACK DAMAGE OR ONLY THE PHYSICAL PART


### Faster Cast Rate
Increases the amount of Spells per Second you can cast. Faster Cast Rate increases the Spells per Second by 0.01 per percent.

Notes:
- There are no diminishing returns
- There is no cap in Faster Cast Rate or Spells per Second 
- Increases in Spells per Second from Faster Cast Rate are always calculated using 1 Spell per Second and therefore the scaling is linear

### Skill Damage
Increases the the damage of all Spell Skills and the Spell part of all Hybrid Skills. 
The stat "[Magic/Cold/Fire/Poison/Lightning] Skill Damage" increases the the [Magic/Cold/Fire/Poison/Lightning] damage of Spell Skills and the Spell part of Hybrid Skills.

TODO: 
- CLARIFY IF SKILL DAMANGE AND [Damage Type] SKILL DAMAGE SCALES ADDITIVILY OR MULTIPLICATIVELY

### Target Defense Ignored
Ignores a percent of enemy defense rating when attacking, resulting in higher chance of hitting the enemy. 

Notes:
- 100% of Target Defense Ignored will result in completely ignoring the Defense Rating of the enemy. In that case, only the enemy level and your Attack Rating will determine if you are able to hit your target.

### Chance for a Deadly Blow
Chance to deal Double Damage when striking an enemy.

{: .warning }
TODO: 
- GLOBAL CHANCE OR PER WEAPON?
- DOES THE STAT EXIST ON ARMOR? IF YES: DOES IT AFFECT BOTH WEAPONS?

### Chance for a Crushing Blow
Chance to deal [Melee: (normal enemy 1/4) (boss 1/8)] [Ranged: (normal enemy 1/8) (boss 1/16)] of remaining health as damage.

{: .warning }
TODO: 
- GLOBAL CHANCE OR PER WEAPON?
- DOES THE STAT EXIST ON ARMOR? IF YES: DOES IT AFFECT BOTH WEAPONS?

### Enhanced Damage
Increases your Physical damage percentually on weapons that have this stat.

{: .warning }
TODO: 
- DOES THE STAT EXIST ON ARMOR? IF YES: DOES IT AFFECT BOTH WEAPONS?

### Chance to Open Wounds
Chance to make the enemy bleed for a total of 40% of your Physical Damage over 8 seconds.

### Enemy Resistance
The stat "-% to Enemy [Magic/Cold/Fire/Poison/Lightning] Resistances" affects the amount of damage enemies take from your [Magic/Cold/Fire/Poison/Lightning] damage.

{: .warning }
TODO: CHECK WHAT THE ENEMY RESISTANCES IN NORMAL/NIGHTMARE/HELL ARE

### All Skills
Increases the level of all Skills by that amount.



## Defensive Stats
### Defense
Lowers the chance of getting hit by incoming Physical Attacks and Physical Projectiles.

{: .warning }
TODO: 
- EXPLAIN CALCULATION: % Chance to get hit = clamp(2 * (_AR / (_AR + _DR)) * (_Alvl / (_Alvl + _Dlvl)), 0.05, 0.95) * 100
- CALCULATE REQUIRED DR TO HIT THE HIGHEST MONSTER LEVEL WHILE IGNORING THEIR DEFENSE
- CALCULATE REQUIRED ATTACK RATING TO HIT THE UBER OR WH BOSS WITH THE HIGHEST DEFENSE

Notes: 
- The chance is at least 5% and at most 95%.

### Increased Defense
Increases the Defense stat percentually (global).

### Enhanced Defense
Increases the Defense value on the item with this particular stat. The Defense value on the tooltip of those items already include the additional Defense from this stat. 

Notes:
- This stat doesn't increase your Defense globally.

### Block Chance
The percent of chance to block incoming Physical attacks and Physical projectiles.

{: .warning }
TODO: 
- WHAT IS THE MAX BLOCK CHANCE?

### Life
The maximum amount of Life. It represents the amount of damage a character can take before they die.

### Life stolen per Hit
Replenishes Life when hitting an enemy with a Physical Attack. The amount of replenished Life is based on the Physical damage dealt.

### Replenish Life
Increases your base regeneration rate defined by the amount of Life you have by a percentage.

### Resistance
Resistances affect the amount of damage taken from Magic, Cold, Fire, Poison or Lightning damage.

The base resistances in each difficulty are the following:
- Normal: [1-5] [0%]
- Nightmare: [1-5] [-35%/-40%/-45%/-50%/-55%]
- Hell: [1-5] [-75%/-80%/-85%/-95%/-100%]

### Slow
{: .warning }
TODO: WHAT DOES SLOW DO? ONLY ENEMY MOVEMENT SPEED REUCTION OR ACTION SPEED?
CAN IT BE TRIGGERED WITH BOTH ATTACKS AND SPELLS?

### (Incoming) Poison Duration
Reduces the time of being poisoned. 

{: .warning }
TODO: 
- DOES THE REDUCTION STACK ADDITIVELY? 
- IS THERE A MIN DURATION?

### (Incoming) Freeze Duration
Reduces the time of being frozen.

There are currently two sources on items for this stat: 
- Half Freeze Duration
- Cannot be Frozen

{: .warning }
TODO: DO 2x items with "stat_half_freeze_duration" do the same thing as "stat_cannot_be_frozen"??

## Utility Stats
### Mana
The maximum amount of Mana. It can be consumed to use Skills.

### Mana stolen per Hit
Replenishes Mana when hitting an enemy with a Physical Attack. The amount of replenished Mana is based on the Physical damage dealt.

### Replenish Mana
Increases your base regeneration rate defined by the amount of Mana you have by a percentage.

### Extra Gold Dropped From Kills
Increases the percentage of Gold dropped from enemies killed.

### Increase Experience Gain
Increases your experience gained from killing enemies.

### Magic Find
Increases the chance of finding Satanic / Set / Angelic items by the amount of Magic Find.

{: .warning }
TODO: 
- DOES IT ALSO AFFECT CHASE ITEMS? 
- DOES IT AFFECT ANGELIC KEYS?