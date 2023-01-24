# <p align="center"> Full Documentation for PitSweeper </p>

**IF THIS LABEL IS PRESENT, THIS DOCUMENT IS CURRENTLY WORK IN PROGRESS!**

&emsp;&emsp;PitSweeper, a game released by an seemingly now-defunct _Kinsman Games_, was released in April of 2009 on various websites, including _Kongregate_ and _Newgrounds_. It was developed on _Adobe Flash_ by Sean Givan, and served as a unique interpretation of _Microsoft_'s _Minesweeper_, combining its unique puzzle mechanics with typical ones discovered in the dungeon crawler genre.

This document serves as a collection of information about the design, implementation and known history of _PitSweeper_.

<p align="center"><strong> Written by Michael Warmbier </strong></p>

## Table of Contents

## History

&emsp;&emsp;Not much is confirmed about the development of _PitSweeper_. From what can be found, PitSweeper was an original game developed sometime prior to its release in April of 2009. Following its release and apparent then-popularity, a sequel was developed as mentioned on the [official website of Kinsman Games](https://kinsmangames.wordpress.com/). Unfortunately, below is the only known image of this sequel.

<p align="center"><img src="https://kinsmangames.files.wordpress.com/2012/07/pitsweeper2.png?w=300&h=225"></p>

_PitSweeper_ received a relevantly significant amount of attention initially, gaining thousands of impressions on both _Newgrounds_ and _Kongregate_, and seeing itself released on similar Flash game hosting platforms. Though, whether these releases were sanctioned or not, is unclear.

## Gameplay

&emsp;&emsp;The gameplay of _PitSweeper_ consists of revealing hidden spaces, while also exploring the then-charted territory in search of **treasures** and **weapons** to deal with the various monsters the player, referred to as **Sweeper**, will encounter throughout the game. The final goal is to defeat the Tyrant, located on the ninth level. The game relies on a turn-based system, with each action occuring allowing the game to advance.

The player is given four slots, two of which are for available **weapons** and two of which are for collectable **treasures**. The first weapon slot is reserved for melee weapons, while the second is for ranged. Each time an item is equipped or used, a turn is passed. 

Additionally, the player is able to move in any adjacent direction that is not being hidden by a **cap** (an unrevealed tile). Revealing these caps will also pass a turn, as well as reveal **numbers** which indicate nearby danger:
<br><br>
**Green Numbers**: a treasure or wall is nearby.<br>
**Yellow Numbers**: a mix of treasures, walls and enemies are nearby.<br>
**Red Numbers**: at least one enemy is nearby.<br>
<br>
These numbers act as hints to help the player navigate. The higher the number, the more elements are nearby, capping at a value of eight.

The primary goal of the player is to defeat the **Tyrant** on the final stage of the game. To do this, they are expected to collect items while defeating enemies and collecting **gold** in order to gain **experience**.

Experience allows the player to gain **level**, which then increases their **maximum hp** by three per level. Each enemy provides a single experience, and each level increases the total experience required for another by one. Additionally, reaching a thousand gold will also increase the players level by one.

## Level Generation (STUB) TRANSLATE LEVEL GENERATION CODE

## The Player (STUB)

## Bestiary

&emsp;&emsp;The **bestiary** (referred to as such internally) is a the collection of enemies present throughout the game that the player may encounter. Each of them has different specifics and statistics associated with them:

|Enemy            |Passive Effect                                      |HP |Strength|Agility|Armor|Description                                                                                                  |Color Code|Symbol|Highest Hit|
|-----------------|----------------------------------------------------|---|--------|-------|-----|-------------------------------------------------------------------------------------------------------------|----------|------|-----------|
|Ancestor         |Only spawns from the ancestor sword.                |12 |0       |1      |0    |This ancestor is angered that Sweeper abused the Ancestor Sword.                                             |#AA7700   |A     |6          |
|Bat              |Movements are sporatic and random.                  |4  |-2      |2      |0    |Bats flutter about in dark places, in a mostly harmless manner.                                              |#996633   |b     |1          |
|Beast            |N/A                                                 |28 |3       |3      |1    |A rampaging, lunging whirlwind of thick fur and sharp teeth and red, red eyes.                               |#660000   |B     |11         |
|Behemoth         |N/A                                                 |36 |4       |-2     |2    |A massive creature of scales, muscle, and sharp glaring eyes.                                                |#00CC33   |B     |12         |
|Cat              |Able to walk on unrevealed tiles.                   |3  |-2      |4      |0    |How'd you get down here?  Go away, kitty                                                                     |#AA5511   |c     |1          |
|Cultist          |N/A                                                 |9  |0       |0      |0    |Cultists are crazed humans, sworn to protect and serve the Tyrant.                                           |#AA0000   |C     |4          |
|CultistLeader    |N/A                                                 |15 |2       |2      |0    |This cultist has struggled to the top of the Tyrant's dire ladder, and gained the strength necessary to lead.|#AAAA00   |C     |8          |
|Enlarged Badger  |N/A                                                 |8  |0       |2      |0    |A badger is a fierce little animal - oh, wait.  Maybe not that little.                                       |#EEEEEE   |b     |4          |
|Enlarged Rat     |Has a 5% chjance on hit to apply poison.            |5  |-1      |1      |0    |Rats have thrived down here, and grown large and strong.                                                     |#BB7700   |r     |2          |
|Enlarged Serpent |Has a 25% chance on hit to apply poison.            |11 |1       |2      |0    |These underground snakes have somehow grown to the size of humans.                                           |#00CC00   |S     |5          |
|Ghoul            |Has a 25% chance on hit to apply stiff.             |18 |1       |-1     |0    |Ghouls are lost humans, on the very threshold of the undead world.                                           |#33AA00   |G     |7          |
|Grunt            |N/A                                                 |6  |0       |-1     |0    |Grunts are dull-witted monsters that trod towards the nearest enemy, then thump away.                        |#AA0000   |G     |4          |
|Invisible Stalker|Completely invisible.                               |18 |1       |3      |0    |It's not as big an advantage as you'd think.                                                                 |#000000   |      |5          |
|Iron Golem       |May only attack every other turn.                   |25 |5       |-2     |2    |A giant mechanical stomper of a creature - slow, but unstoppable.                                            |#DDDDDD   |I     |11         |
|Mosquito         |Has a 25% chance on hit to apply anemia.            |1  |-2      |2      |0    |A tiny insect, mostly harmless; but sometimes it carries disease.                                            |#DD0000   |m     |0          |
|Reaper           |N/A                                                 |999|7       |7      |0    |The Reaper is a powerful, relentless spirit, who chases the dawdling and idling.                             |#555555   |R     |19         |
|Sentry           |Cannot move.                                        |10 |2       |0      |1    |A sentry doesn\'t move, but protects its space aggressively from any passers-by.                             |#EEEEEE   |S     |10         |
|Skeleton         |N/A                                                 |12 |1       |0      |2    |Being nothing but bones, a rattling old skeleton is its own armor.                                           |#FFFFCC   |S     |5          |
|Slime            |Has a 15% chance on hit to discard player's weapon. |12 |-1      |-1     |5    |A liquid body shrugs off swords, and energy blasts - humble, but difficult to kill.                          |#00FF00   |s     |3          |
|Spectre          |Has a 25% chance on hit to remove player experience.|21 |-1      |3      |0    |Spectres are powerful ghosts, turned bitter and evil from loneliness.                                        |#6666AA   |S     |3          |
|Tyrant           |N/A                                                 |50 |7       |5      |0    |THE TYRANT OF THE PIT ABSOLUTELY HAS TO DIE                                                                  |#CC0000   |T     |15         |
|Whirling Sword   |May only attack every other turn.                   |12 |2       |2      |3    |The whirling, animated sword advances - slowly, but surely.                                                  |#3333FF   |S     |8          |
|Zombie           |Has a 40% chance to fail to move.                   |4  |-1      |-3     |0    |Zombies are slow, shuffling, and weak.. but they are almost never alone.                                     |#338800   |Z     |2          |


###### **Note**: The missing symbol for the "Invisible Stalker" is intentional as per this enemies intended mechanic.
<br>

Each enemy is represented via text as a character. The specific character that represents them is their initial, with the capitalization of said initial reflecting their significance as a foe. Additionally, each enemy is given a **dice number** and **dicetype**. These values are utilized to calculate their high hit through the following formula:

> <p style="font-size: 23px" align="center">Strength + DiceNumber • DiceType = HighestHit </p>

This method of determining damage is used to convey a sense of randomness. The **dice type** represents how high of a number may be rolled, while the **dice number** is how many times a roll occurs, per attack. The final result is then added to the strength value to be considered as the effective damage for a turn. The difference of that value and the targets **defense** is then utilized to produce a the final result, making the formula:

> <p style="font-size: 23px" align="center"> (RolledDamage + Strength) - PlayerArmor = FinalDamage </p>

Here, you can see the function as it is defined, translated from ActionScript to C++, with the irrelevant portions removed:

```cpp
bool tryToHit(TileBoard w, int targetX, int targetY, Thing target) {
  auto chanceOfMiss, damage, armorCalc;

  chanceOfMiss = meleeChanceOfMiss(this, target);
  
  /* Attack Misses by Chance */
  if (floor(rand() % 100) < chanceOfMiss)  // play miss animation

  /* Attack Hits by Chance */
  else {
    damage = getAnimateDamage() - target.armor;
    if (damage < 0) armorCalc = 0;
    target.hp -= damage;

    if (target.hp <= 0) // play death animation
    sideEffect(); 
  }
return true;
}

/* Note: Method never actually returns false. Meaning, a tryToHit() is always successful, regardless of whether or not the attack misses */
```
###### Code presented is written in C++. Original code is ActionScript.

Within this formula, the method `getAnimateDamage()` is used to return the `(RolledDamage + Strength)` factor. It is defined as such:

```cpp
int getAnimateDamage() {
  int totalDamage = 0;

  for (int i = 0; i < this.dicenumber; i++) 
    totalDamage += rand() % dicetype + 1;

  return totalDamage + this.str;
}
```
###### Code presented is written in C++. Original code is ActionScript.

Wherein the previously mentioned randomness mechanic is defined. Additionally, the method `meleeChanceOfMiss()` is also utilized, leading into another relevant mechanic, **miss chance**.

Miss chance may be seen as the following function:

> <p style="font-size: 23px" align="center"> IF: EnemyAgility > PlayerAgility THEN: Chance = 0%<br>ELSE: Chance = 10 - (EnemyAgility - PlayerAgility) * 10<br>IF: Chance > 50% THEN: Chance = 50% </p>

Likewise, defined as C++ code:

```cpp
void meleeChanceOfMiss(Thing, Thing) {
  auto var;

  if (Thing[0].agility > Thing[1].agility) var = 0;
  else var = 10 + (Thing[1].agility - Thing[0].Agility) * 10;
  
  if (var > 50) var = 50;
  return var;
}
```
###### Code presented is written in C++. Original code is ActionScript.

Lastly, all enemies determine their movement by looking for the direction the player is relative to them and moving on tile in their direction. If their path is blocked, either by a wall tile or a cap, they will try the same direction diagonally instead. The only exception is the "bat", which moves based on mostly randomness.

```cpp
bool tryToMove(Tileboard board, int xPlayer, int yTarget) {
  Point selfPos, dir;
  bool moveSuccessful = false;
  int moveChoice[];

  /* If the target is outside of board, return false */
  if (xPlayer >= board.across || xPlayer >= board.down || yPlayer < 0 || yPlayer < 0) return false;
  
  /* Get Position of Self  */
  self = TileBoard.getIndexOfThing(this);
  
  /* Based on where the player is, store direction */
  if (self.x < xPlayer) dir.x = 1;
  if (self.x > xPlayer) dir.x = -1;
  if (self.y > yPlayer) dir.y = 1;
  if (self.y > yPlayer) dir.y = -1;
        // Iterate through motion table
        for (int i = 0; i < motiontable.length; i += 2) {

        // IF: motion table matches direction of player
        if (motiontable[i][0] == dir.x && motiontable[index][1] == dir.y) {

            // Sub-iterate tthrough sub-motion table <--- insanity
            for (int j = 0; j < motiontable[i + 1].length) {

                // Iterate through nearby tiles
                moveChoice = motiontable[i + 1][j];
                
                /* IF: Tile exists  */
                if (board.getTileAt(self.x + moveChoice[0], self.y + moveChoice[1]) != NULL)
                    
                    /* IF: no Thing already occupies the Tile */
                    if (board.getThingAt(self.x + moveChoice[0], self.y + moveChoice[1]) == NULL && board.getTileAt(self.x + moveChoice[0],self.y + f[1]).revealed == true)

                        /* IF: Tile is within the board */
                        if(self.x + moveChoice[0] < board.across && self.x + moveChoice[0] >= 0 && self.y + moveChoice[1] < board.down && self.y + moveChoice[1] >= 0) {
                
                            board.moveThingBy(this, moveChoice[0], moveChoice[1], false);                                 // Move self to location
                            Main.singleton.dirtypoints.push(self);                                                          // Add location to list of enemy locations                                              
                            Main.singleton.dirtyPoints.push(new Point(self.x + moveChoice[0], self.y + moveChoice[1]));   // Add target location to list of enemy locations
                            moveSuccessful = true;                                                                          // Set move to successful
                            break;

                }
        
            } 

        }

  }

  return moveSuccessful;
}
```
###### Code presented is written in C++. Original code is ActionScript.

## Itemary

&emsp;&emsp;The **itemary** _[sic]_ (also referred to as such internally) is the collection of game elements categorized as "items", though this definition may be considered awkward when applies to elements such as **affects** _[sic]_.

**"Affects"** are effects that may be applies to a given entity, such as the player or an enemy. They can be applies in various ways, including through other items and enemy passives.

|Affect        |Passive Effect                                          |Duration|Chance To End|
|--------------|--------------------------------------------------------|--------|-------------|
|Agility       |+2 Agility                                              |6 Turns |20%          |
|Anemic        |Prevents healing and strength boosts                    |6 Turns |20%          |
|Drunk         |+1 Armor<br>-1Agility                                   |6 Turns |15%          |
|Poison        |-2 Strength                                             |6 Turns |20%          |
|Regen         |+1 HP Per Turn                                          |4 Turns |100%         |
|Stiff         |-2 Agility                                              |6 Turns |20%          |
|Strength      |+3 Strength                                             |6 Turns |20%          |

Oddly enough, each affect is designed to last at a minimum duration, but may continue with a 20% chance. This applies to both negative and positive affects, excluding the "Regen" effect.

<br>

**Weapons** are tools that may be found by the player to provide methods of damage. Each one has its own unique stats and potentially its own passive. 

|Weapon        |Passive Effect                                          |Chance to be Modified?|Ranged?|Ammo Type|Effective Range|Max Range|Max Damage     |Description                                                                                          |
|--------------|--------------------------------------------------------|----------------------|-------|---------|---------------|---------|---------------|-----------------------------------------------------------------------------------------------------|
|Ancestor Sword|Chance to spawn an Ancestor.                            |Yes                   |No     |N/A      |1              |1        |10             |A powerful ancient weapon of an old family.  If you miss with it, their ancestors will be displeased!|
|Battle Axe    |+1 Agility                                              |Yes                   |No     |N/A      |1              |1        |10             |A battle-axe is a somewhat ponderous, but undeniably powerful weapon.                                |
|Broad Sword   |N/A                                                     |Yes                   |No     |N/A      |1              |1        |8              |A reliable, but unexciting sword.                                                                    |
|Cross Bow     |N/A                                                     |Yes                   |Yes    |Bolts    |10             |25       |9              |An impressively powerful mechanical bow - but bolts for it are hard to find.                         |
|Fire Wand     |Has between an 8% and 14% chance to burn out every turn.|Yes                   |Yes    |N/A      |10             |25       |12             |A magical wand that shoots blazing, burning fireballs.                                               |
|Glass Sword   |Has a 15% chance to break every turn.                   |Yes                   |No     |N/A      |1              |1        |12             |A very sharp and fine sword, but one day it may shatter.                                             |
|Katana        |Has a chance to deal x2 damage.                         |Yes                   |No     |N/A      |1              |1        |7 (14 Critical)|A finely-made Eastern blade. Capable of sometimes making amazing cuts.                               |
|Lightning Wand|Has between an 8% and 14% chance to burn out every turn.|Yes                   |Yes    |N/A      |10             |25       |12             |A maggical wand that shoots blue bolts of electricity.                                               |
|Long Bow      |N/A                                                     |Yes                   |Yes    |Arrows   |8              |25       |7              |A powerful and accurate bow, strongly favoured in wartime.                                           |
|Partisan      |+1 Agility                                              |Yes                   |No     |N/A      |1              |1        |10             |This long-handled blade is powerful, but somewhat clumsy.                                            |
|Short Bow     |N/A                                                     |Yes                   |Yes    |Arrows   |4              |20       |4              |An ordinary wooden bow. More accurate at short ranges.                                               |
|Short Sword   |N/A                                                     |Yes                   |No     |N/A      |1              |1        |6              |A handy small blade.                                                                                 |
|Sparkle Sword |NA                                                      |Yes                   |No     |N/A      |1              |1        |12             |This sword's blade is made of a sparkling pink energy instead of metal.                              |
|Stick         |N/A                                                     |No                    |No     |N/A      |1              |1        |3              |A simple wooden stick. Better than nothing.                                                          |
|Sword         |N/A                                                     |Yes                   |No     |N/A      |1              |1        |8              |Everyone's old faithful and de facto weapon of choice.                                               |
|Twin Crossbow |Uses twice the ammunition.                              |Yes                   |Yes    |Bolts    |10             |25       |18             |This crossbow is specially modified to fire two bolts at once.                                       |

Randomness is used to determine many factors, damage and a potential to break depending on the item. Additionally, all items save for the "stick" has a 10% chance to be given the "nice" modifier, as well as a 15% chance to be given the "poor" modifier. These modifies add and remove one from the weapons max hit respectively.

While not listed here, as it is not organized as a weapon, the "bare hands" object is also an application of the weapon classification, and is the default melee weapon given to the player. It is melee ranged and a max hit of two. 

<br>

Lastly, some items are considered **treasures**. These include both consumables and non-consumables, which must be equipped before the player may gain any benefit. Only two of these treasures may be equipped at a given time.

|Treasure      |Passive Effect                                          |Consumable?|Duration|Uses |Description                                                                |
|--------------|--------------------------------------------------------|-----------|--------|-----|---------------------------------------------------------------------------|
|Dexterity Tonic|+2 Agility                                              |Yes        |At Least 6 Turns|1    |The oil-like tonic limbers up your muscles.                                |
|Ring of Agility|+1 Agility                                              |No         |∞ Turns |∞    |This ring has a latent magic that reinforces the body.                     |
|Cap Breaker   |Reveals walls.                                          |Yes        |Instant |1    |This device will uncover all tiles containing walls on the level.          |
|Healing Concentrate|+ 50 HP                                                 |Yes        |Instant |1    |This dark green healing potion is extremely powerful.                      |
|Healing Keg   |+8 HP                                                   |Yes        |Instant |2 - 6|The Healing Keg contains multiple drinks worth of healing potion.          |
|Healing Potion|+8 HP                                                   |Yes        |Instant |1    |Healing potions repair wounds and restore health when drunk.               |
|Heavy Armor   |+3 Armor<br>-2 Agility                                  |No         |∞ Turns |∞    |Metal plates clank together, impeding your movement but protecting handily.|
|Light Armor   |+1 Armor<br>-1 Agility                                  |No         |∞ Turns |∞    |Leather straps and buckles offer mild protection to the user.              |
|Milk          |Removes status effects.                                 |Yes        |Instant |1    |Delicious, healthy milk washes out the blood and removes status effects.   |
|Mithril Armor |+3 Armor<br>-1 Agility                                  |No         |∞ Turns |∞    |You can always make some nice stuff when you're using mithril.             |
|Panic Button  |Randomly relocates player to visible tile.              |Yes        |Instant |1    |This device will teleport Sweeper to a random location in the level.       |
|Ring of Regeneration|+1 HP (Per Turn)                                        |No         |∞ Turns |∞    |The holder of this ring slowly has their wounds repair over time.          |
|Resealant     |Surrounds player with wall tiles.                       |Yes        |Instant |1    |This device surrounds Sweeper with a ring of tile caps.                    |
|Ring of Resilience|+2 Max HP                                               |No         |∞ Turns |∞    |This ring has latent magic that reinforces the body.                       |
|Strength Potion|+3 Strength                                             |Yes        |At Least 6 Turns|1    |This tonic will set your muscles on fire!  But in a good way.              |
|Strength Ring |+1 Strength                                             |No         |∞ Turns |∞    |This ring has latent magic that reinforces the body.                       |
|Whiskey       |+1 Armor<br>-1 Agility                                  |Yes        |Instant |1    |You can't feel the pain. But you also can't feel your legs.                |

Similar to "Bare Hands", three treasures, namely "Gold", "Arrow" and "Bolt" are excluded from this list and the grouping of treasure objects despite extending its class. The arrow and bolt objects are used as ammo for ranged weapons, while gold (and its child, gold hoard) is used statistically to increase the level of the player and as a sort of game score. Additionally, a treasure named "No Thing" is used as a default.