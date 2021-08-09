# Dokumentation Quest/Mission System #


## Quest Bundles

Ein Quest Bundle ist eine Sammlung von einzelnen Quests.
Aus diesem Pool können einzelne Quests ausgewählt werden oder nacheinander bearbeitet werden.

Für jede Quest Bundle wird ein Ordner mit Quests geben.

## Quest Model ##

Das Quest Model ist das Hauptskelett einer Quest.
Diese beschreibt den Aufbau der Quest und enthält alle Voraussetzungen, Aufgaben und Belohnungen.

Der Name wird intern benutzt und **muss einzigartig** sein innerhalb eines Bundles

Die Quest wird als `.json` Datei in dem QuestBundle Ordner platziert.

Eine Quest ist wie folgt aufgebaut:
```json
{
  "id": "exampleQuest1",
  "displayName": "Beispiel Quest 1",
  "description": "Farme 20 Stein Blöcke",
  "stages": [
     //Siehe Stufen
  ],
  "requirements": [
    //Siehe Vorraussetzungen
  ],
  "rewards": [
    //Siehe Belohnugen
  ]
}
```

##  Quest Stufen

Die Quest Stufen werden in der definierten Reihenfolge abgearbeitet.
Jede Stufe kann aus beliebig vielen Objectives bestehen.

Eine Stage ist wie folgt aufgebaut:

```json
{
  "objectives": [
    //Siehe Objectives
  ] 
}
```

## Quest Objectives

Ein Objective beschreibt eine konkrete Aufgabe/Ziel, welches erreicht werden soll.
Ein Ziel hat einen Namen und einen Wert der erreicht werden soll.

Mit der angabe des Types, wird festgelegt, wie der Spieler die Aufgabe beenden soll.
Jedes Objective kann dazu Options haben, die z.B die Blöcke für das Ziel festlegt.

Eine Übersicht über alle Typen und deren Options findest du hier: [Objectives Übersicht](docs/objectives.md)

Ein Objective ist wie folgt ausgebaut:
 ```json
{
  "id": "break1",
  "displayName": "Baue 20 Steinblöcke ab.",
  "goal": 20,
  "type": "BreakBlockObjective",
  "options": {
    "blocks" : [
      "minecraft:stone"
    ]
  }
}
```

## Quest Voraussetzung

Um eine Quest beginnen zu können, muss ein Spieler Voraussetzungen erfüllen.
Diese Voraussetzungen können in einer Quest definiert werden.

Das Vorgehen ist Analog zu den Objectives.

Durch die Angabe eines Types wird die Voraussetzungen spezifiziert und mittels Options konfiguriert werden.

Weitere Felder:
-  checkOnlyAtStart: Die Voraussetzung wird nur beim start der Quest validiert.

Eine Übersicht über alle Typen und deren Options findest du hier: [Übersicht Voraussetzung](docs/requirements.md)

Eine Voraussetzung ist wie folgt ausgebaut:

```json
{
  "id": "requirement1",
  "displayName": "Premium Quest",
  "type": "GroupRequirement",
  "checkOnlyAtStart": true,
  "options" : {
    "rank": "PREMIUM"
  }
}
```

## Quest Belohnungen

Für eine abgeschlossene Quest, kann ein Spieler eine Belohnung erhalten.
Die Belohnungen können in einer Quest definiert werden.

Das Vorgehen ist analog zu den Objectives,

Durch die Angabe eines Types wird die Belohnung spezifiziert und mittels Options konfiguriert.

Eine Übersicht über alle Typen und deren Options findest du hier: [Übersicht Belohnungen](docs/rewards.md)

Eine Belohnung ist wie folgt ausgebaut:
````json
{
  "id": "reward1",
  "displayName": "1x Diamant",
  "type": "ItemStackReward",
  "options": {
    "items": [
      "{DataVersion:2586,id:\"minecraft:diamond\",Count:1b}"
    ]
  }
}
````

