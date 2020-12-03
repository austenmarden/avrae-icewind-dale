# Beveren Cheat Sheet
## Attacks
### Pike
`!attack Pike <target>`

### Quarterstaff
`!attack Quarterstaff <target>`

### 2-Handed Quarterstaff
`!attack "2-Handed Quarterstaff" <target>`

### Unarmed Strike
`!attack "Unarmed Strike" <target>`

### Polearm Master - Bonus Attack
`!attack "Polearm Master - Bonus Attack" <target>`

### Polearm Master - Opportunity Attack
`!attack "Polearm Master - Opportunity Attack" <target>`

## Barbarian Specific
[Workshop Commands](https://avrae.io/dashboard/workshop/5f73c28d647bb0a416316d32)

### Rage
`!rage`

Will start a rage on your active character, using your Rage or Rages counter. If you're in initiative, will add an effect to you, granting resistances and damage bonus.

**Parameters** 

-i - Ignore requirements, does not use a counter.

-t <target> - Will start a rage on the target.

frenzy - Causes the Rage to be a frenzied rage.

-d <damage> - Overrides the damage bonus.

`!rage bear`

Sets your Totem Spirit to bear, applying the appropriate resistances.

`!rage nodmg`

Disables the -d damage on the init effect.

`!rage end`

Will end a rage on your active character.

`!surge`

Rolls on the Wild Surge table for the Path of the Wild Mage subclass from Tasha's book.

## Goliath Specific

### Stone's Endurance

#### Usage
`!stones-endurance`

#### Alias Code
```
!serveralias stones-endurance embed {{cc="Stone's Endurance"}} 
<drac2>
if character().cc_exists("Stone's Endurance") and character().get_cc("Stone's Endurance") > 0:
    character().mod_cc("Stone's Endurance", -1, strict=True)
    rollValue = roll("1d12")
    combinedValue = rollValue + constitutionMod
    result = f"{name} becomes as hard as stone, reducing the damage they just took by ({rollValue} +  {constitutionMod}) : {combinedValue}"
else:
    result = f"{name} has no more uses available for Stone's Endurance. They can be recharged with a short or long rest."
</drac2>
-f "Roll|{{result}}"
-desc "You can focus yourself to occasionally shrug off injury. When you take damage, you can use your reaction to roll a d12. Add your Constitution modifier to the number rolled, and reduce the damage by that total. After you use this trait, you can’t use it again until you finish a short or long rest."
-thumb https://i.imgur.com/9yPkSh9.png
-title "Stone's Endurance"
```
