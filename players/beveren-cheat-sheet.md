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

## Goliath Specific

### Stone's Endurance
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
