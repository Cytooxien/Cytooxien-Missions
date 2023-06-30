# Voraussetzungen

***

### QuestCompletedRequirement

- Beschreibung: Erfordert, dass die Liste von Quests abgeschlossen wurde
- Options:
    - quests: Liste von QuestId als Json String Array. Die Quest-Ids müssen innerhalb eines Bundles liegen.

***

### AccessLevelRequirement

- Beschreibung: Erforderliches AccessLevel/Rang um eine Quest zu beginnen.
- Options:
    - accessLevel: Zahlen Wert des Ranges, den der Spieler haben muss, um die Quests zu beginnen

Aktuelle AccessLevel der Ränge:
``
SPIELER(1), PREMIUM(10), PREMIUM_PLUS(40), VIP(50), ARCHITEKT(60), CONTENT(70), SUPPORTER(70), SR_SUPPORTER(75), MODERATOR(80), JR_DEVELOPER(85), DEVELOPER(90), SR_DEVELOPER(92), ADMIN(95), OWNER(100);
``

***

### QuestBundleCompletedRequirement

- Beschreibung: Erfordert, dass ein Spieler alle Quests aus einem Quest Bundle abgeschlossen hat.
- Options:
  - bundle: Name/Id des Quest Bundles

***

### SupplyItemStackRequirement

- Beschreibung: Der Spieler erhält beim Start der Mission einige Gegenstände. Analog zum ItemStackReward.
- Options:
  - items: ItemStack List als Json String Array

Für weitere Informationen siehe `ItemStackReward`
