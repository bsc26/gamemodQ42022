# gamemodQ42022
IT 266 Quake 4 game mod project

A txt copy of this readme is in the dndMod folder

==============INTRUCTIONS=============

==Commands==
attributes: shows current attribute stats and how many attribute increases you have. 
class (class name): gives you a class. 
increase (attribute) (amount): increases attribute. can only use if you've leveled up. 
cheatincrease (attribute) (amount): increases attribute. no limit.  


==Walkthrough==
Start a new game

You start with a useless weapon. Give yourself a class using the console and the "class" command. Each class alters stats and gives you a weapon. 

The options are fighter, wizard, and ranger. 
Fighter starts you off with just the melee weapon but you get higher health and armor. 
Wizard gives you the magic weapon that uses "mana" ammo that constantly regens. But your armor is much lowered. 
Ranger gives you the bow weapon and the melee weapon. You reload the bow with each shot and the projectile has gravity. You also get increased Dexterity.

You can only have one class so you must start a new game if you wnat a different class.

Kill enemies to gain experience. Levels and experience are kept track in the bottom right of the hud. The number denotes your level and bar fills as you gain experience.
the first enemy killed levels you up. It require more and more enemies to level up each time.

Each time you level up you may increase an attribute. Use the "increase" command to do so. If you leveled up multiple times you can increase an attribute by a higher ammount. 
You can use the "cheatincrease" command to test the attributes without fighting. The attributes are listed below. 

Lastly there is a randomness to your attacks that simulate a dice roll. If the roll is higher than or equal to the enemies Armor Class (default 13) then the attack hits. 
Otherwise it misses and deal no damamge. A modifier is added to the roll depedent on the weapons appropriate attribute. You can see the rolls in the console. 


==Attributes==
str: Strength. Increases your maximum armor by 10 and melee damage by 20% for each point above 10.
dex: Deterity. Increases your speed by 10% and ranged weapon damage by 10% per point above 10. (not with the magic weapon).
con: Constitution. Increases maximum health by 10 per point above 10. 
int: Intelligence. Increase your maximum mana by 10 and mana regeneration rate is lowered by 0.1 seconds per point above 10.  

Having less than 10 reduces all those values. 


==Weapons==
Melee Weapon: Modified gauntlet. Does a single burst of damage to the monster aimed at every time the fist extends. 
Bow Weapon: Modified machine gun. Shoots a single projectile, that has garvity and needs to be reloaded each shot. (I guess its more like a crossbow?)
Magic Weapon: Modified blaster. Primary fire shoots a hitscan lightning bolt. Charged alt fire shoots a fireball. Both use the mana ammo that constantly regens.
Lightning bolt uses 10 mana and fireball 25. Mana also halts if you hold fireball. 


==Testing==
To test classes use the "class" command in the console with "fighter", "wizard", or "ranger" as the argument. You have to start a new game to chooe another class

Each class will allow you to test each of the three new weapons respecively. 

To test the level up system, simply kill enemies. First enemy will level you. A you kill more the bar exp bar in the bottom right will fill. 

To test attributes you use the "increase" command if you gained levels or simply use the "cheatincrease" command with "str", "dex", "con", or "int" as the first argument and
optionally a number as the second argument. 
The cheatincrease command will allow you to more easily see the effects of an attribute like with dex and speed if you make the value high. 

To test the random attack rolls look at the console to ee your roll. If you rolled lower than 13 the attack should have missed, dealing no damage. 
This is more eaily see with the fireball as it does the most damage and should one shot enemies if the attack doesn't miss. 


=============Changes That Were Made=================

Out of the weapons the gauntlet and the blaster saw the most change. I had to alter the gauntlet code so it punches once instead of holding it out.
The blasters ammo had to be modified so it constantly regens at a configurable rate, as well as altering the def files to fire lightning and fire.
The machinegun also had it's def file changed to shoot the nailgun projectile that has gravity and to only have one bullet.
Each weapon also has the code that handles the attack rolls. 

The attributes are stats for the player like health and armor that effect the various things. There is code that changes the player depending on the attributes.
Some of the code alters the PowerUpModifier function that is always called say when damamge is done.

Several commands were added each with their own code that changes the player along with changing the attributes. 

The player has an exp and level stats now. Whenever an enemy dies the function is called that handles that. It reuires more and more exp to level up each time.
Whenever the level is increased a counter increases that denotes how many times the playercan increase their attributes. 

As for guis the main menu and hud were changed. The title logo was changed as well as the removal of the multiplayer button. 
Since it shares the same button with the "quit current game", it wasn't actually removed, just made hidden inthe main opening menu screen. 

An experience/level bar was added to the Hud. Code was edited with the gui scripts and added code that handles the gui states. 
Whenever the experience bar fills up the player gains a level and then is depleted.

A function was created the attack rolls and is called with every attack. If the attack rolls above a set threshold the attack hits and deals damage. 





