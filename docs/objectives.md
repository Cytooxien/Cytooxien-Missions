# Objectives

___

## Abstrakte Objectives

Abstrakte Ziele können nicht instanziiert werden. Sie stellen nur Optionen für die mehr spezifischeren Objectives dar.

Alle Optionen von den abstrakten Objectives sind auch in den unter Objektives verfügbar.

### AbstractBlockObjective

- Options:
    - blocks : [BlockList](types.md) Json String Array

### AbstractEntityObjective

- Options:
    - entities : [EntityTypeList](types.md) Json String Array

### AbstractItemObjective

- Options:
    - items : [ItemList](types.md) Json String Array

___

## Objectives Implementationen

***

### BreakBlockObjective

- Beschreibung: Blöcke abbauen
- Kinder:
    - AbstractBlockObjective
- Options:

***

### PlaceBlockObjective

- Beschreibung: Blöcke platzieren
- Kinder:
    - AbstractBlockObjective
- Options:

***

### KillEntityObjective

- Beschreibung: Tiere töten
- Kinder:
    - AbstractEntityObjective
- Options:

***

### BreedEntityObjective

- Beschreibung: Tiere züchten
- Kinder:
    - AbstractEntityObjective
- Options:

***

### FishItemObjective

- Beschreibung: Gegenstand mit der Angel gefangen
- Kinder:
    - AbstractItemObjective
- Options:

***

### HandInItemObjective

- Beschreibung: Gegenstände mit /abgabe eingereicht
- Kinder:
    - AbstractItemObjective
- Options:

***

### TalkToNPCObjective

- Beschreibung: NPC erscheint an der Position und kann Nachrichten sprechen
- Messages Key: quest.talktonpc." bundleName "." + questId + "." objectiveId
- Weiter Befehl: /talktonpc accept
- Zurück Befehl: /talktonpc decline
- Options:

```json
{
  "location": {
    "x": -7,
    "y": 31,
    "z": -19,
    "world": "3a45829e-6ab6-422a-9119-47ffc774c12d",
    "yaw": -42.5,
    "pitch": 0,
    "server": "cbspawn-1"
  },
  "npc": {
    "skinValue": "value",
    "skinSignature": "sig",
    "name": "NPC Name"
  }
}
```

***

### ActionEventObjective

- Beschreibung: Reagiere auf feste Events (action)
- Options:
    - action: "slum_teleport"

Übersicht der Action findest du hier: [Übersicht Actions](actions.md)

***

### CraftItemObjective

- Beschreibung: Gegenstand hergestellt
- Kinder:
    - AbstractItemObjective
- Options:

***

### ActivateQuestObjective

- Beschreibung: Der Spieler startet eine Quest
- Options:

```json
{
  "quest": {
    "bundle": "tutorial",
    "id": "beginner"
  }
}
```

***

### FurnaceExtractItemObjective

- Beschreibung: Ein Gegenstand/Gegenstände wird/werden aus dem Ofen Inventar entnommen
- Kinder:
    - AbstractItemObjective
- Options:

***

### EnchantItemObjective

- Beschreibung: Ein Gegenstand/Gegenstände wird/werden aus dem Ofen Inventar entnommen
- Kinder:
    - AbstractItemObjective
- Options:
    - enchantments: String Array mit Namespaced Enchantments (Optional)

Beispiel:
```json
{
  "options": {
    "items": [
      "stone_sword"
    ],
    "enchantments": [
      "minecraft:protection"
    ]
  }
}
```

***
