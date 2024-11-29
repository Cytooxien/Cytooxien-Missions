# Dokumentation des Missionssystem

Wir haben für unsere Themenserver ein flexibles Missionssystem entwickelt, um Missionen in Minecraft zu erstellen und zu
verwalten.
Hier findest du die Dokumentation unseres Missionssystem über den Aufbau und Funktionsweise.

![68747470733a2f2f692e696d6775722e636f6d2f484830556e4a6c2e706e67](https://user-images.githubusercontent.com/51920026/193283398-635594c0-872d-4fd8-b2c4-9fe74d549e54.png)
![image](https://user-images.githubusercontent.com/51920026/193283832-27d0421c-2875-4524-83f8-a6cab95a1bf7.png)

## Unterstützung

Möchtest du uns bei der Erstellung neuer Mission unterstützen und aktiv neuen Content für unsere Spielmodi entwickeln
kannst du dich als Content bei uns [im Forum](https://cxn.link/quest-content) bewerben.

Weitere Informationen findest du hier: [Contributing](CONTRIBUTING.md)

## Quest Bundles

Ein Quest Bundle ist eine Sammlung von einzelnen Quests.
Aus diesem Pool können einzelne Quests ausgewählt werden oder nacheinander bearbeitet werden.

Für jede Quest Bundle wird ein Ordner mit Quests geben.

## Quest Model

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

## Quest Stufen

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
Jedes Objective kann dazu Options haben, die z.B. die Blöcke für das Ziel festlegt.

Weitere Felder:

- abortQuestOnCompletion: Sollte das Objective erfüllt werden, bricht die Quest ab.

Eine Übersicht über alle Typen und deren Options findest du hier: [Objectives Übersicht](docs/objectives.md)

Ein Objective ist wie folgt ausgebaut:

 ```json
{
  "id": "break1",
  "displayName": "Baue 20 Steinblöcke ab.",
  "goal": 20,
  "abortQuestOnCompletion": false,
  "type": "BreakBlockObjective",
  "options": {
    "blocks": [
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

- checkOnlyAtStart: Die Voraussetzung wird nur beim start der Quest validiert.

Eine Übersicht über alle Typen und deren Options findest du hier: [Übersicht Voraussetzung](docs/requirements.md)

Eine Voraussetzung ist wie folgt ausgebaut:

```json
{
  "id": "requirement1",
  "displayName": "Premium Quest",
  "type": "GroupRequirement",
  "checkOnlyAtStart": true,
  "options": {
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

## Licence

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a><br />
Dieses Werk ist lizenziert unter einer <a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">
Creative Commons Namensnennung - Nicht kommerziell - Keine Bearbeitungen 4.0 International Lizenz</a>.

