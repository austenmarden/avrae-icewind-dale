### Note
_This encounter was the final part of the Portal Under The Stars DCC funnel that our group did as part of character building for Icewind Dale. It is not part of the normal Icewind Dale Encounters_

# Departing the Portal
[DnD Beyond Encounter](https://www.dndbeyond.com/encounters/09240fa1-8e96-4b6e-94d4-95518aa5011e)


> As you each think upon your wishes you find the stars around you fading and the darkness of the abyssal void brightening. You blink your eyes several times to adjust to the new light and find yourselves standing in the main room with the large statue looming over you, it's damage repaired and its countenance taking on a striking similarity to your own. Each of you now sees the statue as your own ideal self, the hero of renown that your heart desired, a champion for whatever this unknown being may have been.

Take a few moments to describe the changes that you have undergone. Describe why you chose what you did and how you are different from the villager you once were.

> As you turn to leave the portal you pass through the room with with statues that killed one of the villagers. You notice that their body is gone, no longer pinned to the door... and the statues are missing as well. You hear an unmistakable _scrape scrape_ sound coming from the corner of the room and notice that the 2 large statues have animated and are moving to attack you!

> "Those who wish to free the herald must die in this place!" a metallic gutteral scraping sound echoes from the helmet of one of the constructs as it hefts its weight in your direction.

> You feel the air slowly starting to get sucked from the room as a gust of wind slams the door towards the portal closed. The ground rumbles beneath your feet. There's no mistaking that this place is going to crash down around you, trapping you here for eternity!

## Commands

### Monster Images
```
!monimage Animated Armor
!monster Animated Armor
```

### Combat Start
```
!multiline
!i begin
!i madd "Animated Armor" -n 2 -name "Animated Armor #"
!i add 15 "The Portal Quakes" -p
```
Wait for everyone to join the combat, then:
```
!i next
```

### Monster Attacks

```
!i attack slam -t <target> 
    -phrase "The animated armor swings its arms downward in a jerky overhead motion, slamming them towards you!"
    -phrase "A large metal encased foot stomps the ground in front of you, splintering the hard tiles and sending sharp shards cascading around you!"
    -phrase "The metal monstrosity contorts its upper body like a top and unleashes itself in a flurry of spinning fists!"
```

### Aliases
#### Portal Turn Alias

After creating this alias, have a user type `!000-portal-turn` to run it
```
!serveralias portal-turn embed {{cc="The Portal Quakes!"}} 
<drac2>
rollValue = roll("1d20")
combinedValue = rollValue + dexteritySave
rollResults = f"{name} passed the test!"
if combinedValue <= 10:
  damage = roll("1d3")
  character().modify_hp(-1 * damage)
  rollResults = f"{name} failed the test and took {damage} damage! {'' if character().hp > 0 else 'They have fallen unconcious!'}"
</drac2>
-f "Hazard|The ground shifts violently beneath {{name}}'s feet!"
-f "Dexterity Save|{{name}} rolled a dexterity saving throw and got ({rollValue} + {dexteritySave}) : {combinedValue}!"
-f "Results|{{rollResults}}"
-f "Health|{{character().hp_str()}}|inline"
-thumb {{image}}
-image "https://www.tribality.com/wp-content/uploads/2020/06/5d060c09e2dee2bd088f7494924d84091.jpg"
-title "The Portal Quakes"
```

## Conclusion
If the players defeat both animated armors, the group receives a total of 400 XP (split evently amongst the players)

_You crash to the snowy ground as you leap through the quickly dwindling portal. The cold harsh darkness of night assaults your lungs and you feel the ache of frost invade your bones. Standing back up you look back to the standing stones, the once shimmering portal gone from view, and the Empty Star no where in sight. You notice a half dozen pairs of large heavy tracks heading in the opposite direction of the town. From this vantage point, looking down the hill, you can see the village. A large fire has been lit in the townsquare, and your keen eyes can make out several people moving about._  
