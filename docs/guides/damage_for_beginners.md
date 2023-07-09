---
title: Damage for Beginners
layout: default
parent: Guides
---

# Damage for Beginners
Dealing Damage in Hero Siege is roughly half of the game (maybe more if you're playing Softcore). The main source of damage are your Active Skills. This chapter will explain how to scale their damage.

Active the Skills scale with: 
- **Attributes**: You can spend 4 Attribute Points per Level.
- **Stats**: Certain stats scale your Active Ability depending on the Skill type (more on that in the "Damage Skill Types" section). You gain stats from items, Passive Skills, Auras and Mercenary Skills.
- **Skill levels**: Most Skill levels increase the damage of your Active Skill. You get one Skill point per level and can spend a maximum of 20 Skill points per Skill. You can gain additional Skill levels from items.
- **The Skill levels of certain other Skills**: In HS2 Active Skills gain bonus damage from certain other Active Skills, which are mentioned at the bottom of the Skill tooltip.
- **Auras**: Auras that increase a relevant Stat for your Active Skills, will boost their damage. You can only use one Aura at a time.
- **Passives**: Passives that increase a relevant Stat for your Active Skills, will boost their damage.

## Damage Skill Types
There are three types of damage Skills in Hero Siege 2: Attack Skills, Spell Skills and Hybrid Skills. The following chapters explain how to identify each Skill type with an example, how to scale it's damage and what to look out for.

### Attack Skills
Attack Skills utilize your weapon(s) to deal damage and scale heavily off of Attack Damage. Some of them require a specific weapon type in order to be used. Your Attack Rating determines the chance for Attack Skills to hit.

**How to identify this Skill type:**

- doesn't have any damage type tags
- deals increased Attack Damage (except for the default Skill "Attack")
- is an Active Skill

**Examples of this Skill type:**

- The most basic example of this Skill type is the Skill "Attack":
![Image](../assets/images/attack.png "(default) Attack")

- Another Attack Skill would be "Explosive Bullets":
![Image](../assets/images/explosive_bullets.png "Explosive Bullets (Pirate)")


**This Skill type makes use of the following Stats:**

- [Attack Damage]
- [Strength]
- [Dexterity]
- [Enhanced Damage]
- [Attack Rating]
- [Increased Attack Rating]
- [Target Defense Ignored]
- [Attack Speed]
- [Additive Damage]
- [Critical Strike Chance]
- [Critical Strike Damage]
- [Chance for a Crushing Blow]
- [Chance to a Deadly Blow]
- [Chance to Open Wounds]
- [Life stolen per Hit]
- [Mana stolen per Hit]
- [Energy] (except the default Skill "Attack")
- [Mana] (except the default Skill "Attack")
- [Skill levels] (except the default Skill "Attack")
- [Enemy Resistance] (only applies to the Non-Physical part of the Attack)


Notes: 
- Attack Skills do **not** scale with Skill Damage

### Spell Skills
Spell Skills always hit and deal either Physical, Magic, Cold, Fire, Poison or Lightning damage. Some of them have a cooldown and/or duration.

**How to identify this Skill type:**

- always has a damage type tag of either Physical, Magic, Cold, Fire, Poison or Lightning
- deals a certain amount of flat damage of the same type as the damage type tag
- does **not** deal additional Attack Damage (if it does, then it's a Hybrid Skill and not a Spell Skill)
- is an Active Skill

**Examples of this Skill type:**

The Fire Spell Skill "Fireball" which scales with Faster Cast Rate:
![Image](../assets/images/fireball.png "Fireball (Pyromancer)")

The Physical Spell Skill "Bouncing Grenade" which scales with Faster Cast Rate:
![Image](../assets/images/bouncing_grenade.png "Bouncing Grenade (Marauder)")

The Fire Spell Skill "Tire Fire" which scales with Attack Speed.
![Image](../assets/images/tire_fire.png "Tire Fire (Redneck)")


**This Skill type makes use of the following Stats:**

- [Faster Cast Rate] (if the skill has the purple flame icon on the top right of the tooltip)
- [Attack Speed] (if the skill has the orange sword icon on the top right of the tooltip)
- [Skill Damage]
- [Energy]
- [Mana]
- [Skills levels] 
- [Enemy Resistance] (only applies to Non-Physical Spells)


### Hybrid Skills
Hybrid Skills are part Attack Skill and part Spell Skill. Each part scales separately according to the Attack Skill and Spell Skill section. 

**How to identify this Skill type:**

- always has a damage type tag of either Physical, Magic, Cold, Fire, Poison or Lightning
- deals additional Attack Damage
- is an Active Skill

**Examples of this Skill type:**

The Hybrid Skill "Thunder Fury" which performs an Attack with increased Attack Damage as well as a Spell which deals Lightning damage:
![Image](../assets/images/thunder_fury.png "Thunder Fury (Amazon)")

The Hybrid Skill "Rend Flesh" which performs Attack with increased Attack Damage as well as a Spell which deals Bleeding Damage over time:
![Image](../assets/images/rend_flesh.png "Rend Flesh (Marauder)")

**This Skill type makes use of the following Stats:**

- (Please refer to the Attack Skills section for the Attack part of the skill)
- (Please refer to the Spell Skills section for the Spell part of the skill)

<!---  TODO: 
- SECTION ABOUT DOTS LIKE BLEED AND POISON. WHAT'S THEIR DEFAULT DURATION? --->

[Test]
----

[Attack Damage]: ../mechanics/stats.html#attack-damage
[Strength]: ../mechanics/stats.html#attributes
[Dexterity]: ../mechanics/stats.html#attributes
[Enhanced Damage]: ../mechanics/stats.html#enhanced-damage
[Attack Rating]: ../mechanics/stats.html#attack-rating
[Increased Attack Rating]: ../mechanics/stats.html#increased-attack-rating
[Target Defense Ignored]: ../mechanics/stats.html#target-defense-ignored
[Attack Speed]: ../mechanics/stats.html#attack-speed
[Additive Damage]: ../mechanics/stats.html#additive-damage
[Critical Strike Chance]: ../mechanics/stats.html#critical-strike-chance
[Critical Strike Damage]: ../mechanics/stats.html#critical-strike-damage
[Chance for a Crushing Blow]: ../mechanics/stats.html#chance-for-a-crushing-blow
[Chance to a Deadly Blow]: ../mechanics/stats.html#chance-for-a-deadly-blow
[Chance to Open Wounds]: ../mechanics/stats.html#chance-to-open-wounds
[Life stolen per Hit]: ../mechanics/stats.html#life-stolen-per-hit
[Mana stolen per Hit]: ../mechanics/stats.html#mana-stolen-per-hit
[Energy]: ../mechanics/stats.html#attributes
[Mana]: ../mechanics/stats.html#mana
[Skill levels]: ../mechanics/stats.html#all-skills
[Enemy Resistance]: ../mechanics/stats.html#enemy-resistance
[Faster Cast Rate]: ../mechanics/stats.html#faster-cast-rate 
[Skill Damage]: ../mechanics/stats.html#skill-damage