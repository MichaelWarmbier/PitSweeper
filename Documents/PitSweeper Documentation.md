# <p align="center"> Full Documentation for PitSweeper </p>

**IF THIS LABEL IS PRESENT, THIS DOCUMENT IS CURRENTLY WORK IN PROGRESS!**

&emsp;&emsp;PitSweeper, a game released by an seemingly now-defunct _Kinsman Games_, was released in April of 2009 on various websites, including _Kongregate_ and _Newgrounds_. It was developed on _Adobe Flash_ by Sean Givan, and served as a unique interpretation of _Microsoft_'s _Minesweeper_, combining its unique puzzle mechanics with typical ones discovered in the dungeon crawler genre.

This document serves as a collection of information about the design, implementation and known history of _PitSweeper_.

<p align="center"><strong> Written by Michael Warmbier </strong></p>

## Table of Contents

## History

&emsp;&emsp;Not much is confirmed about the development of _PitSweeper_. From what can be found, PitSweeper was an original game developed sometime prior to its release in April of 2009. Following its release and apparent then-popularity, a sequel was developed as mentioned on the [official website of Kinsman Games](https://kinsmangames.wordpress.com/). Unfortunately, below is the only known image of this sequel.

<p align="center"><img src="https://kinsmangames.files.wordpress.com/2012/07/pitsweeper2.png?w=300&h=225"></p>

_PitSweeper_ received a relevantly significant amount of attention initially, gaining thousands of impressions on both _Newgrounds_ and _Kongregate_, and seeings its game released on similar Flash game hosting platforms. Though, whether these releases were sanctioned or not, is unclear.

## Gameplay (STUB)

&emsp;&emsp;The gameplay of _PitSweeper_ consists of revealing hidden spaces, while also exploring the then-charted territory in search of **treasures** and **weapons** to deal with the various monsters the player, referred to as **Sweeper**, will encounter throughout the game. The final goal is to defeat the Tyrant, located on the ninth level.

## Beastiary

&emsp;&emsp;The **beastiary** (referred to as such internally) is a the collection of enemies present throughout the game that the player may encounter. Each of them has different specifics and statistics associated with them:

|Beast            |HP |Strength|Agility|Armor|Description                                                                                                  |Color Code|Symbol|Highest Hit|
|-----------------|---|--------|-------|-----|-------------------------------------------------------------------------------------------------------------|----------|------|-----------|
|Ancestor         |12 |0       |1      |0    |This ancestor is angered that Sweeper abused the Ancestor Sword.                                             |#AA7700   |A     |6          |
|Bat              |4  |-2      |2      |0    |Bats flutter about in dark places, in a mostly harmless manner.                                              |#996633   |b     |1          |
|Beast            |28 |3       |3      |1    |A rampaging, lunging whirlwind of thick fur and sharp teeth and red, red eyes.                               |#660000   |B     |11         |
|Behemoth         |36 |4       |-2     |2    |A massive creature of scales, muscle, and sharp glaring eyes.                                                |#00CC33   |B     |12         |
|Cat              |3  |-2      |4      |0    |How'd you get down here?  Go away, kitty                                                                     |#AA5511   |c     |1          |
|Cultist          |9  |0       |0      |0    |Cultists are crazed humans, sworn to protect and serve the Tyrant.                                           |#AA0000   |C     |4          |
|CultistLeader    |15 |2       |2      |0    |This cultist has struggled to the top of the Tyrant's dire ladder, and gained the strength necessary to lead.|#AAAA00   |C     |8          |
|Enlarged Badger  |8  |0       |2      |0    |A badger is a fierce little animal - oh, wait.  Maybe not that little.                                       |#EEEEEE   |b     |4          |
|Enlarged Rat     |5  |-1      |1      |0    |Rats have thrived down here, and grown large and strong.                                                     |#BB7700   |r     |2          |
|Enlarged Serpent |11 |1       |2      |0    |These underground snakes have somehow grown to the size of humans.                                           |#00CC00   |S     |5          |
|Ghoul            |18 |1       |-1     |0    |Ghouls are lost humans, on the very threshold of the undead world.                                           |#33AA00   |G     |7          |
|Grunt            |6  |0       |-1     |0    |Grunts are dull-witted monsters that trod towards the nearest enemy, then thump away.                        |#AA0000   |G     |4          |
|Invisible Stalker|18 |1       |3      |0    |It's not as big an advantage as you'd think.                                                                 |#000000   |      |5          |
|Iron Golem       |25 |5       |-2     |2    |A giant mechanical stomper of a creature - slow, but unstoppable.                                            |#DDDDDD   |I     |11         |
|Mosquito         |1  |-2      |2      |0    |A tiny insect, mostly harmless; but sometimes it carries disease.                                            |#DD0000   |m     |0          |
|Reaper           |999|7       |7      |0    |The Reaper is a powerful, relentless spirit, who chases the dawdling and idling.                             |#555555   |R     |19         |
|Sentry           |10 |2       |0      |1    |A sentry doesn\'t move, but protects its space aggressively from any passers-by.                             |#EEEEEE   |S     |10         |
|Skeleton         |12 |1       |0      |2    |Being nothing but bones, a rattling old skeleton is its own armor.                                           |#FFFFCC   |S     |5          |
|Slime            |12 |-1      |-1     |5    |A liquid body shrugs off swords, and energy blasts - humble, but difficult to kill.                          |#00FF00   |s     |3          |
|Spectre          |21 |-1      |3      |0    |Spectres are powerful ghosts, turned bitter and evil from loneliness.                                        |#6666AA   |S     |3          |
|Tyrant           |50 |7       |5      |0    |THE TYRANT OF THE PIT ABSOLUTELY HAS TO DIE                                                                  |#CC0000   |T     |15         |
|Whirling Sword   |12 |2       |2      |3    |The whirling, animated sword advances - slowly, but surely.                                                  |#3333FF   |S     |8          |
|Zombie           |4  |-1      |-3     |0    |Zombies are slow, shuffling, and weak.. but they are almost never alone.                                     |#338800   |Z     |2          |

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
