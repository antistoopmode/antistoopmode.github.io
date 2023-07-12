---
title: Save File Editing
layout: default
parent: Guides
---

# How to edit Hero Siege 2 save files
In certain scenarios it might be useful to test certain items, builds or other interactions on local before you spend resource in the online mode. This is where save file editing comes in handy. It lets you add gold, crafting resources , equipment and other items to your inventory, stash or equipment slots.

The save files can be found at the following location:
- Windows: %localappdata%\Hero_Siege\hs2saves

There you can find the following files:
- herosiege[slot].pas: the character save file
- inventory_order_[slot].pas: the character inventory save file
- shop.ini: the account wide save file
- stash.pas: the account wide stash save file

([slot] refers to the character slot number which starts at 0)

## Level up
To set your character Level, change the "level" value in the character save file "herosiege[slot].pas" to the desired level (1-100).
```
level="100.000000"
```

The Hero Level can be adjusted in the character save file "herosiege[slot].pas" with the "herolevel" value (1-100).
```
herolevel="100.000000"
```

## Unlock all difficulties and waypoints
Setting the act and zone values in the character save file "herosiege[slot].pas" to 1/2/3 will unlock the zones and waypoints for for Normal/Nightmare/Hell respectively. Lastly set "act_previous" to the desired act number of the town you wanna spawn in.

```
act_1="3.000000"
zone1,0="3.000000"
zone1,1="3.000000"
zone1,2="3.000000"
zone1,3="3.000000"
zone1,4="3.000000"
act_2="3.000000"
zone2,0="3.000000"
zone2,1="3.000000"
zone2,2="3.000000"
zone2,3="3.000000"
zone2,4="3.000000"
act_3="3.000000"
zone3,0="3.000000"
zone3,1="3.000000"
zone3,2="3.000000"
zone3,3="3.000000"
zone3,4="3.000000"
act_4="3.000000"
zone4,0="3.000000"
zone4,1="3.000000"
zone4,2="3.000000"
zone4,3="3.000000"
zone4,4="3.000000"
act_5="3.000000"
zone5,0="3.000000"
zone5,1="3.000000"
zone5,2="3.000000"
zone5,3="3.000000"
zone5,4="3.000000"
act_6="3.000000"
zone6,0="3.000000"
zone6,1="3.000000"
zone6,2="3.000000"
zone6,3="3.000000"
zone6,4="3.000000"
act_7="3.000000"
zone7,0="3.000000"
zone7,1="3.000000"
zone7,2="3.000000"
zone7,3="3.000000"
zone7,4="3.000000"
act_8="3.000000"
zone8,0="3.000000"
zone8,1="3.000000"
zone8,2="3.000000"
zone8,3="3.000000"
zone8,4="3.000000"
act_previous="1.000000"
```
## Add gold
In order to change the account wide gold, modify the "gold" and/or "gold_hc" value in the account wide save file "shop.ini".

```
gold="999699999.000000"
gold_hc="999699999.000000"
```

## Mining Level
In order to change the account wide Mining Level, modify the "mining" and/or "mining_hc" value (1-5000) in the [mining] section of the account wide save file "shop.ini".

```
[mining]
mining="5000.000000"
mining_hc="5000.000000"
```

## Jewelcrafting Level
In order to change the account wide Jewelcrafting Level, modify the "jewelcrafting" and/or "jewelcrafting_hc" value (1-250) in the [jewelcrafting] section of the account wide save file "shop.ini".

```
[jewelcrafting]
jewelcrafting="250.000000"
jewelcrafting_hc="250.000000"
```

## Creating Items
The structure of an item in the save file looks like this:

```js
{
    "id": 1,
    "rarity": 6,
    "token_level": 0,
    "timestamp": "0.00",
    "mf_drop": 0,
    "amount": 1,
    "market_id": 0,
    "drop_quality": 0,
    "token": 0,
    "tier": 4,
    "weapon_type": 0,
    "type": 0,
    "account": "1-0",
    "seed": 18186.0
}
```

A short explanation of the key/value pairs:
- "id": The ID of the item is unique per type and is numbered according to the [Hero Siege 2 Roadmap - Satanic Item Reworks sheet](https://docs.google.com/spreadsheets/d/1QWjl6lITbMkjptYPIRwnIVUs7JQkqfEqAILlCgp1zAM/edit#gid=957743150)
- "rarity": The rarity represents the item rarity
    - 1: Common (also used for relics)
    - 2: Superior
    - 3: Rare
    - 6: Satanic
    - 7: Angelic
    - 9: Heroic
- "timestamp": The UNIX timestamp of when the item dropped
- "amount": The stack size
- "type": The item type
    - 0: Helmet
    - 1: Body Armor
    - 2: Boots
    - 3: Weapon
    - 4: Gloves
    - 5: Amulet
    - 6: Shield
    - 7: Ring
    - 8: Belt
    - 15: Rune
    - 16: Relic
- "weapon_type": The armor or weapon base type
    - 0: Armor (or Shield)
    - 1: Sword
    - 2: Dagger
    - 3: Mace
    - 4: Axe
    - 5: Claw
    - 6: Polearm
    - 7: Chainsaw
    - 8: Staff
    - 9: Cane
    - 10: Wand
    - 11: Book
    - 12: Spellblade
    - 13: Bow
    - 14: Gun
    - 15: Flask
    - 16: Throwing
    - 17: Novelty
- "seed": Seed value to determine the individual stat rolls

### Example
Let's say we wanna create the Satanic item "Death's Mirror". We can see on the [sheet](https://docs.google.com/spreadsheets/d/1QWjl6lITbMkjptYPIRwnIVUs7JQkqfEqAILlCgp1zAM/edit#gid=957743150) that it's in the 1st position of the Dagger column. This indicates that the id is most likely 0 (not all lists are sorted by id). It's an dagger weapon, thus "weapon_type" 2 and "type" 3.

```js
{
    "id": 0,
    "rarity": 6,
    "token_level": 0,
    "timestamp": "0.00",
    "mf_drop": 0,
    "amount": 1,
    "market_id": 0,
    "drop_quality": 0,
    "token": 0,
    "tier": 4,
    "weapon_type": 2,
    "type": 3,
    "account": "1-0",
    "seed": 18186.0
}
```

## Equipping an item
In order to assign an item to the desired equipment slot , set the desired inventory[slot] value (where [slot] is the equipment slot number from the table below) in the character save file to the item ([encoded in Base64](https://www.base64encode.org/)) you want. The encoding is only required for the equipment slots, but not for the stash or inventory file.

| Slot | Type                    |
|------|-------------------------|
| 0    | Helmet                  |
| 1    | Body Armor              |
| 2    | Boots                   |
| 3    | Weapon (left)           |
| 4    | Gloves                  |
| 5    | Amulet                  |
| 6    | Weapon / Shield (right) |
| 7    | Ring (left)             |
| 8    | Belt                    |
| 9    | Ring (right)            |
| 10   | Relic Slot 1            |
| 11   | Relic Slot 2            |
| 12   | Relic Slot 3            |
| 13   | Relic Slot 4            |


### Example
Let's use the "Death's Mirror" that we created in the [previous example](#example). Since we wanna equip it, we convert it to Base64 and assign it to the first weapon slot, which is slot #3 according to the table above.
```
inventory3="ewogICAgImlkIjogMCwKICAgICJyYXJpdHkiOiA2LAogICAgInRva2VuX2xldmVsIjogMCwKICAgICJ0aW1lc3RhbXAiOiAiMC4wMCIsCiAgICAibWZfZHJvcCI6IDAsCiAgICAiYW1vdW50IjogMSwKICAgICJtYXJrZXRfaWQiOiAwLAogICAgImRyb3BfcXVhbGl0eSI6IDAsCiAgICAidG9rZW4iOiAwLAogICAgInRpZXIiOiA0LAogICAgIndlYXBvbl90eXBlIjogMiwKICAgICJ0eXBlIjogMywKICAgICJhY2NvdW50IjogIjEtMCIsCiAgICAic2VlZCI6IDE4MTg2LjAKfQ=="
```

## Store an item in the stash or inventory
Items in the stash or inventory file have two additional keys/value pairs (X and Y) to determine their position in the grid. Use the character inventory save file "inventory_order_[slot].pas" (where [slot] refers to the character slot number which starts at 0) or the account wide stash save file "stash.pas" to store an item.

### Example
Let's use the "Death's Mirror" again that we created in the [previous example](#example). We want to store it in the first stash space (0/0), so we set the X and Y value, which determine the grid position, to 0 and put it in the first stash tab object.

```js
{
    "stash_reset": 0.0,
    "stash_tab_0": [
        {
            "id": 0,
            "rarity": 6,
            "token_level": 0,
            "timestamp": "0.00",
            "mf_drop": 0,
            "amount": 1,
            "market_id": 0,
            "drop_quality": 0,
            "token": 0,
            "tier": 4,
            "weapon_type": 2,
            "type": 3,
            "account": "1-0",
            "seed": 18186.0,
            "x": 0.0,
            "y": 0.0
        }
    ],
    "stash_tab_1": [],
    "stash_tab_2": [],
    "stash_tab_3": [],
    "stash_tab_4": [],
    "stash_tab_5": []
}
```