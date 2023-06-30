# Objectives

___

### Globale Objective Options:

- Options:
  - server-regex: Ein Objective wird nur aktiviert, wenn das Regex zur ServerId des server matched. Dies kann verwendet werden um die Auf gabe nur auf bestimmten Servern zu aktivieren bzw. zu deaktivieren.


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
    "name": "NPC Name",
	"visibleHologram": true,
	"toHologramY": 0.0
  }
}
```

visibleHologram und toHologramY sind optional. Defaultwerte wie oben eingetragen.

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

### BucketEntityObjective

- Beschreibung: Der Spieler fängt ein Entity mit einem Eimer ein. In der Regel: Fische!
- Kinder:
  - AbstractEntityObjective
- Options:

***

### ConsumeItemObjective

- Beschreibung: Der Spieler hat einen Gegenstand konsumiert (food, potion, milk bucket).
- Kinder:
  - AbstractItemObjective
- Options:

***

### BlastBlockObjective

- Beschreibung: Blöcke mit TNT zersprengen
- Kinder:
  - AbstractBlockObjective
- Options:

***

### MoveIntoBiomeObjective

- Beschreibung: Der Spieler bewegt sich in ein Biom
- Kinder:
- Options:
  - biomes: List von Minecraft Biomen

***

### EffectObjective

- Beschreibung: Der Spieler bekommt einen Effekt
- Kinder:
- Options:
  - effects: List von Effekten (https://i.imgur.com/CdMV3hg.png)

***

### BucketFillObjective

- Beschreibung: Der Spieler füllt einen Eimer mit einer Flüssigkeit
- Kinder:
  - AbstractItemObjective

***

### EntityInteractObjective

- Beschreibung: Der Spieler interagiert mit einem Entity
- Options:
  - entities (Entity Predicate)
  - items: Items die der Spieler in der Hand halten muss

***

### BreakSpawnerBlockObjective

- Beschreibung: Der Spieler baut einen Spawner Block ab
- Options:
  - entityTypes: List von Bukkit EntityTypes (optional)

***

### HarvestBlockObjective

- Beschreibung: Der Spieler ernte Items von einem Block
- Kinder:
  - AbstractItemObjective

***

### ComposterItemObjective

- Beschreibung: Der Spieler ändert das Level eines Komposters
- Options:
  - action: Filter für die vom Spieler durchgeführte Aktion am Komposter (Werte: ADD_ITEM, EMPTY) (optional)
  - trackCompostingChange: Wenn true wird die Level Änderung als Fortschritt erfasst, sonst die elementare Aktion (default true).

***

### TransactionExecutedObjective

- Beschreibung: Für den Spieler wurde eine Transaktion ausgeführt.
- Options:
  - transactionName: Interner Klassenname der hinzugefügten Transaktion
  - mode: Berechnungsmodus für den Fortschritt (Werte: SUM, COUNT) SUM => Transaktionswert Fortschritt, COUNT => Transaktionsanzahl Fortschritt

***

### BlockInteractObjective

- Beschreibung: Der Spieler interagiert mit einem Item auf einen Block.
- Options:
  - blocks: Filter für die interagierten Blöcken (Darf nicht leer sein)
  - items: Filter für den bei der Interaktion verwendeten Gegenstand.

***

### DisenchantItemObjective

- Beschreibung: Der Spieler repariert oder entzaubert einen Gegenstand aus dem Schleifstein/Grindstone
- Kinder:
  - AbstractItemObjective
- Options:
  - items: Ausgangsgegenstand der entzaubert oder repariert werden soll (vorher)

***

### VillagerTradeObjective

- Beschreibung: Der Spieler handelt einen Gegenstand mit einem Villager
- Kinder:
  - AbstractItemObjective
***

### AdvancementObjective

- Beschreibung: Der Spieler erreicht ein Minecraft Advancement
- Kinder:
  - AbstractItemObjective
- Options:
  - advancement: Minecraft Advancement Daten Wert [Siehe Minecraft Wiki](https://minecraft.fandom.com/de/wiki/Fortschritte)
***

### HitTargetBlockObjective

- Beschreibung: Der Spieler trifft einen Zielblock/TargetBlock (Nur auf Paper verfügbar)
- Options:
  - entities (EntityTypeList): Verwendetes Entity Projektil
  - signalStrength (int): Minimum Signalstärke (Optional)
***

### SmithItemObjective

- Beschreibung: Der Spieler wertet im Schmiedetisch einen Gegenstand aus Diamant mit einem Netheritbarren zu einem Gegenstand aus Netherit auf.
- Kinder:
  - AbstractItemObjective
- Options:
  - items: Der aufgewertete Gegenstand (Result)

***

### GameEventObjective

- Beschreibung: Der Spieler löst ein GameEvent aus
- Kinder:
  - AbstractOptionalBlockObjective
- Options:
  - event: Minecraft Id des ausgelösten Events
  - block: Block an der Position des ausgelösten Events (Optional)

***

### BlockDropItemObjective

- Beschreibung: Der Spieler erhält einen Gegenstand aus einem Block. Beispielsweise, wenn der Spieler einen Block mit einem Pinsel behandelt. Aus einem Block können mehrere Gegenstände erzeugt werden.
- Kinder:
  - AbstractBlockObjective
- Options:
  - items: Filter für den erhaltenen Gegenstand.
  - block: Block, aus dem der Gegenstand erzeugt wird

***
