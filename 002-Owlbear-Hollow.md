# Owlbear Hollow
## Aliases
### Town
```
!serveralias OwlbearHollow embed {{cc="Owlbear Hollow"}} 
-title "Owlbear Hollow"
-desc "Friendliness: ❄ 
Services: ❄
Comfort: ❄"
-f "Available Quest|The Orb's Owner"
-f "Population|8"
-f "Leader|None. Old Man Roberts, the previous leader of the town, recently died from a tragic accident caused by this endless winter."
-f "Militia|None."
-f "Heraldry|A left facing Owlbear stands over four diamonds, each representing the 4 founding families of the small town, along with the letters O and H, representing the town's namesake."
-f "Sacrifice to Auril|Warmth"
-f "Rivals|All 10 Towns"
-f "Overland Travel|While closely connected to the main road entering Icewind Dale, travel to other towns is best taken by the main road, as other routes are snow covered and filled with danger."
-thumb "https://i.imgur.com/ckpClwK.png"
-image "https://i.imgur.com/ibAgX9A.jpg"
-footer "Source: https://www.worldanvil.com/w/owlbear-hollow-jasarole"
```

### Encounters
#### Fanatic Cultists
_As you return to the town, something feels... off. The air is stale and a crackling static puts your arm hairs on end. You hear voices up ahead in the town square chanting monotonously._

_Approaching the square, you see three figures dressed in black flowing garb wearing bizarre masks. They are gathered around a large pile of corpses, most of them partly decayed, and all of them covered in various amounts of fresh dirt. You recognize all of the corpses. These are the remains of the villagers that you buried in town just before heading into the portal. The cultists voices mix in an intermingled chant that is part pleasure, part pain. The chant crescendos with a deafening yelp from the trio that mixes with a wailing scream coming from inside the pile of rotting flesh. You watch in horror as the head of Hagatha rips from within the pile of bodies. Two leathery wings flap wildly from where her ears once were. Her face twists into a demonic snarl as she glides into the air with a deafening screech. The cultists all frown at the severed flying head, clearly disappointed at not summoning the right creature, before taking up their chant once again. Hagatha sniffs at the air tentatively before turning her gaze your way... Two more cultists step from behind The Winged Bear, another corpse in tow between them. They drop their quarry quickly when they see you and unsheathe long ritualistic scimitars. The other cultists continue their chant, paying you no mind at all._

##### Images
```
!monimage Cultist
!monster Cultist
!monimage Vargouille
!monster Vargouille
```

##### Combat Start
```
!multiline
!i begin
!i madd "Cultist" -n 2 -name "Cultist #"
!i madd "Vargouille" -n 1 -name "Demon #"
!i add 5 "The Ritual Strengthens" -p
```
Wait for everyone to join the combat, then:
```
!i next
```

##### Monster Attacks

**Cultist**
Scimitar: Attack: +3 to hit. Hit: 1d6 + 1 [slashing] damage.
```
!i attack scimitar -t <target> 
```

**Vargouille**
Bite: Attack: +4 to hit. Hit: 1d6 + 2 [piercing] + 3d6 [poison] damage.
```
!i attack bite -t <target> 
```

Kiss: DC 12 CHA Save. Fail: Cursed.
```
!i attack kiss -t <target> 
!i effect <target> "Vargouille's Kiss" -desc "The cursed target loses 1 point of Charisma after each hour, as its head takes on fiendish aspects. The curse doesn't advance while the target is in sunlight or the area of a daylight spell; don't count that time. When the cursed target's Charisma becomes 2, it dies, and its head tears from its body and becomes a new vargouille. Casting remove curse, greater restoration, or a similar spell on the target before the transformation is complete can end the curse. Doing so undoes the changes made to the target by the curse."
```

Stunning Shriek: DC 12 WIS Save. Fail: Frightened (Stunned).
```
!i attack Stunning Shriek -t <target> -t <target> -t <target>
!status frightened
```

#### Rewards

1x Scroll of Summon Abyssal Familiar - _This scroll speaks of summoning and binding a ferocious demonic familiar to help you in your travels. A crude drawing, likely scrawled by the hand of the cultist you just killed shows a ferocious thousand tooth lined maw and dark soulless eye_

1x Assassination Contract - _Brothers and Sisters, word has reached us of a grave undertaker and his family travelling from the south to disturb our stranglehold on the dead in Icewind. We cannot let anyone interfere with our affairs. Find Bhulin Puhi and insure the only graves he'll tend in these icy realms are his own!_

2x Black Velvet Mask - _An ornate black velvet mask sitched with silver thread. The word or name Umôrdhoth is repeated several times in crude deep speech across a spiral pattern.
