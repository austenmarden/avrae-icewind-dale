# Gale Cheat Sheet
## Attacks

### Quarterstaff
`!attack Quarterstaff -t `
### 2-Handed Quarterstaff
`!attack "2-Handed Quarterstaff" -t `
### Unarmed Strike
`!attack "Unarmed Strike" -t `

## Spellbook
### Cantrips
#### Chill Touch
`!cast "Chill Touch" -t `

#### Mage Hand
`!cast "Mage Hand" -t `

#### Mending
`!cast Mending`

#### Mind Sliver
`!cast "Mind Sliver" -t `

#### Toll the Dead
`!cast "Toll the Dead" -t `

### 1st Level
#### Cause Fear
`!cast "Cause Fear" -t `

#### False Life
`!cast "False Life"`

#### Ray of Sickness
`!cast "Ray of Sickness" -t `

#### Tasha's Caustic Brew
`!cast "Tasha's Caustic Brew" -t `

## Wizard Specific

### Arcane Recovery
#### Recover a 1st level spell
`!arcane-recovery-1st-level`
<details>
  <summary>Alias Code</summary>
   
```
!serveralias arcane-recovery-1st-level embed {{cc="Arcane Recovery - 1st Level"}} 
<drac2>
recoveredAmount = 1
if character().cc_exists("Arcane Recovery"):
    if character().get_cc("Arcane Recovery") >= recoveredAmount:
        currentSlots = character().spellbook.get_slots(1)
        maxSlots = character().spellbook.get_max_slots(1)
        if (currentSlots != maxSlots):
            character().mod_cc("Arcane Recovery", (-1 * recoveredAmount), strict=True)
            character().spellbook.set_slots(1, character().spellbook.get_slots(1) + recoveredAmount)
            result = f"{name} recovers {recoveredAmount} 1st level spell slot"
        else:
            result = f"{name} already has the maximum amount of 1st level spells"
    else:
        result = f"{name} does not have enough arcane recovery at the moment. These charges can be recharged with a short or long rest."
else:
    result = f"{name} does not have the Arcane Recovery feature."
</drac2>
-f "Result|{{result}}"
-desc "You have learned to regain some of your magical energy by studying your spellbook. Once per day when you finish a short rest, you can choose expended spell slots to recover. The spell slots can have a combined level that is equal to or less than half your wizard level (rounded up), and none of the slots can be 6th level or higher."
-thumb https://i.pinimg.com/236x/26/df/54/26df5434448341bcd2c72bb9391849b9.jpg
-title "Arcane Recovery - 1st Level"
```
</details>
