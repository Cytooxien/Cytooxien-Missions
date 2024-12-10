# Belohnungen

***

### ItemStackReward

- Beschreibung: Der Spieler erhält Gegenstände in sein Inventar.
- Options:
    - items: ItemStack List als Json String Array

In der ItemStack Liste können folgende Elemente enthalten sein:

- ItemStack im Mojang NBT String Format (Mit DataVersion)
- Minecraft Namespaced Types
  oder [Bukkit Material Types](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html)

**Wichtig:**
Die Liste muss gegensatz zu der ItemList explizite Gegenstände enthalten. Deswegen ist die verwendung von Tags **nicht**
möglich!


*** 

### TransactionReward

- Beschreibung: Der Spieler erhält Geld.
- Options:
    - amount: 10.0 (double)

***

### OnlyUpTrophyReward

- Beschreibung: Der Spieler erhält Trophäen auf einer Map.
- Options
    - world: Name/UUID der Welt
    - trophies: Anzahl der Trophäen

***

### CosmeticReward

- Beschreibung: Der Spieler erhält ein Cosmetic.
- Options
    - cosmetic: CosmeticKey des Cosmetic

***

### CrystalReward

- Beschreibung: Der Spieler erhält Kristalle.
- Options
    - amount: Anzahl an Kristallen
