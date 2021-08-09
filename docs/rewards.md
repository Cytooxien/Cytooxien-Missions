# Belohnungen

***

### ItemStackReward

- Beschreibung: Der Spieler erhält Gegenstände in sein Inventar.
- Options:
    - items: ItemStack List als Json String Array

In der ItemStack Liste können folgende Elemente enthalten sein:

- ItemStack im Mongang NBT String Format (Mit DataVersion)
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
