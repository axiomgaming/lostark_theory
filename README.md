# Notes on Lost Ark Theorycrafting

## Attack Affixes

1. **Front Attack**: Inflicts 20% more damage and 10% increased stagger/weak point damage when hitting from the front arc of the enemy. Master Brawler engraving increases damage by +5/12/25%.
2. **Back Attack**: Inflicts 5% more damage with a 10% increased crit rate when hitting from the rear arc of the enemy. Ambush Master engraving increases damage by +5/12/25%.
3. **Counter**: Land a Counter ability from the front arc of the enemy when they briefly glow blue to interrupt the enemy's attack.
4. **Stagger**: Inflicts stagger damage (the purple bar beneath a boss's health bar; during specific stagger checks, there is typically also a yellow-orange bar beneath the boss's feet). When the enemy stagger bar is depleted they will briefly stand still and stop attacking, providing a window for DPS. 6 levels:
    - Low
    - Medium-Low
    - Medium
    - Medium-High
    - High
    - Highest
5. **Weak Point**: Inflict weak point damage to a breakable part (highlighted with a green-blue circle) to gain a beneficial effect (deal more/receive less damage, disable special attacks, etc.).

## Skill Types

Shown below the skill name on tooltips, in the Combat Skill window (K), etc.
1. **Normal**: Press the button, the thing happens right where your character is facing.
2. **Point**: Press the button, the thing happens where your mouse pointer is (subject to range limits).
3. **Combo**: Press the button again in a short window after first activated, usually with different effects.
4. **Holding**: Press and hold the button (up to a limit) and the skill fires continuously. Some holding effects show a 'perfect zone' area of the on-screen bar; releasing the button in the perfect zone to activate a secondary effect or improve damage.
5. **Charging**: Press and hold the button to charge the skill up; release to fire. Typically the longer the skill is charged the stronger it is.

## Super Armor and Crowd Control

Three levels, each includes the effects of the previous:
1. **Paralysis Immunity**: Immunity to brief stagger effect from being hit, which interrupts skills and movement. (Crowd Control level 1)
2. **Push**: Immunity to knock-back/up/down. Using space bar to recover from this uses a separate timer from normal dash, referred to as the Stand Up Action Cooldown. (Crowd control level 2)
3. **All**: Immunity to stun/fear/sleep/pest/electrocute/freeze/etc. (Crowd control level 3)

Spacebar and Awakening skills typically provide level 3 Super Armor. This means that with good timing you can avoid
a knockdown or crowd control (e.g., Argos landing, Saydon's birds) with spacebar.

## Combat and Character Sheet Stats

 - **Crit**: Provides crit rate (approx 0.035785% per pt)
 - **Spec**: Provides
    1. Awakening skill damage (approx 0.054644% per)
    2. Identity gain (varies by class)
    3. Class-specific damage/healing buffs (varies)
 - **Domination**: Provides
    1. Damage to pushed/debuffed foes (approx 0.061315% per)
    2. Damage to staggered foes (approx 0.071321% per)
 - **Swiftness**: Provides
    1. Atk/Move Speed (0.017175% per)
    2. Cooldown Reduction (approx 0.0214655% per)
 - **Endurance**: Provides
    1. Phy/Mag Defense (approx 0.081714% per)
    2. Shield bonus (approx 0.025429% per)
    3. Healing bonus (approx 0.0357143% per)
 - **Expertise**: Provides
    1. Increase enemy debuff duration (approx 0.042889% per)
    2. Decreased self debuff duration (approx 0.035778% per)
    3. Increase stagger damage (approx 0.028444% per)
 - **Crit Damage**: 200% baseline (i.e., +100%). Assume a theoretical hit that does 100 damage. With default baseline crit damage, 
   Keen Blunt 3 and 60% crit rate, your expected damage increase is 16.375% (over no KBW), which implies that the odds of a 
   hit's damage being nerfed by KBW are 10% and the expected baseline damage is (100 - 0.2x0.1) = 98. 
   See: [https://www.reddit.com/r/lostarkgame/comments/spt8zp/keen_blunt_weapon_efficiency_table/] [https://lostark.fandom.com/wiki/Keen_Blunt_Weapon]
 - **Move Speed**: Caps at 140% (equivalent to approx raw swiftness of 2329; obviously this is not reachable, instead you need
   move speed buffs like Mayhem's 15% which reduces the swiftness to cap to a more reasonable 1456). This cap implies 
   Raid Captain caps at 18% increased damage.
 - **Movement Skill**: Space bar dash. Cooldown is class-dependent (see below). Separately there is the Stand Up ability, 
   which is also triggered with space bar when knocked down and has its own separate cooldown.
 
 | Class        | Dash Skill      | Cooldown      |
|--------------|-----------------|---------------|
| Berserker    | Tumbling        | 7s            |
| Destroyer    | Run             | 8s            |
| Gunlancer    | Back Step       | 5s            |
| Paladin      | Sprint          | 8s            |
 | Glaivier     | Mirage Dash     | 6s            |
 | Scrapper     | Duck            | 5s\* (7s/10s) |
 | Soulfist     | Nebulous Step   | 9s            |
 | Striker      | Charging Steps  | 6s            |
 | Wardancer    | Pleasant Sprint | 8s            |
 | Artillerist  | Roll            | 10s           |
 | Deadeye      | Tumbling        | 8s            |
 | Gunslinger   | Stampede        | 8s            |
 | Sharpshooter | Slide           | 9s            |
 | Machinist    | Tremors         | 9s            |
 | Arcanist     | Vanish          | 9s            |
 | Bard         | Sound Illusion  | 10s           |
 | Sorceress    | Phase Leap      | 8s            |
 | Summoner     | Elemental Wings | 10s           |
 | Deathblade   | High-Speed Move | 6s            |
 | Shadowhunter | Rush            | 9s            |
 | Reaper       | Shadow Step     | 7s            |
| Artist       | Stroke: Spill   | 7s            |

\* Scrapper has two dashes, you can opt to either use one and expend only one 5s cooldown (total actual time roughly 7s, because
 there is a delay before the 5s timer starts while you are given the opportunity to use the 2nd dash), or use both 
(total time around 10s if you immediately use both dashes)

---

## Defense
 - Survivability depends on total HP and damage mitigation. Raw incoming damage is mitigated (reduced) then subtracted
   from your HP. If your HP goes to 0 you get to observe.
 - Damage mitigation as a function of Armor Coefficient $a$:    
   $m(a) = 1 - {1 \over (1 + (0.0001535 \times 5000a))} = 1 - {1 \over (0.7675a + 1)} = {0.7675a \over 0.7675a + 1}$
 - HP is a function of HP coefficient $h$ and ability stone vitality $v$: $f(h,v) = hv$
 - Actual damage taken is a function of mitigation $m$ and raw damage $d_{raw}$: $f(m,d) = d_{raw}(1-m)$
 - Putting it all together we get damage taken as a function of armor coefficient $a$ and raw damage $d_{raw}$:    
   $d_{taken}(a,d_{raw}) = d_{raw}(1 - {0.7675a \over 0.7675a + 1}) = d_{raw}({1.30293 \over a + 1.30293})$
 - Max incoming damage is a function of hit points $p$ and armor coefficent $a$:
   $dmg(a,p) = {p \over {1 \over (0.7675a + 1)}}$
 - Original version of this table at (out of date): [https://docs.google.com/spreadsheets/d/10NC1mgY8HQKmaU_IryqGfPM7dJUwaJPfw2G2kPGOFs8/edit#gid=0] found via [https://infolao.tistory.com/entry/Lostark-guide-Class-HP-Armor-Coefficient]

| Rank | Class        | HP Coefficient | HP from 20k Stone | Armor Coefficient | Damage mitigated | Max incoming damage |
|:-----|:-------------|:--------------:|:-----------------:|:-----------------:|:----------------:|:-------------------:|
| 1    | Gunlancer    |      2.5       |       50000       |        1.3        |   0.4994368665   |       99887.5       |
| 2    | Destroyer    |      2.3       |       46000       |       1.15        |   0.4688267711   |      86600.75       |
| 3    | Scrapper     |      2.3       |       46000       |        1.1        |   0.4577741629   |       84835.5       |
| 4    | Berserker    |      2.2       |       44000       |        1.1        |   0.4577741629   |        81147        |
| 5    | Glaivier     |      2.2       |       44000       |       1.05        |   0.446251817    |       79458.5       |
| 6    | Wardancer    |      2.2       |       44000       |       1.05        |   0.446251817    |       79458.5       |
| 7    | Striker      |      2.2       |       44000       |       1.05        |   0.446251817    |       79458.5       |
| 8    | Paladin      |      2.1       |       42000       |        1.1        |   0.4577741629   |       77458.5       |
| 9    | Soulfist     |      2.1       |       42000       |       1.05        |   0.446251817    |      75846.75       |
| 10   | Deathblade   |      2.2       |       44000       |        0.9        |   0.408546503    |        74393        |
| 11   | Artillerist  |      2.1       |       42000       |       0.95        |   0.421672811    |      72623.25       |
| 12   | Sorceress    |       2        |       40000       |       0.95        |   0.421672811    |        69165        |
| 13   | Gunslinger   |       2        |       40000       |        0.9        |   0.408546503    |        67630        |
| 14   | Shadowhunter |       2        |       40000       |       0.85        |   0.394810500    |        66095        |
| 15   | Summoner     |       2        |       40000       |        0.8        |   0.3804213135   |        64560        |
| 16   | Arcanist     |       2        |       40000       |        0.8        |   0.3804213135   |        64560        |
| 17   | Sharpshooter |       2        |       40000       |        0.8        |   0.3804213135   |        64560        |
| 18   | Artist       |      1.9       |       38000       |        0.9        |   0.408546503    |       64248.5       |
| 19   | Machinist    |       2        |       40000       |       0.75        |   0.3653312178   |        63025        |
| 20   | Reaper       |       2        |       40000       |       0.75        |   0.3653312178   |        63025        |
| 21   | Bard         |      1.9       |       38000       |       0.75        |   0.3653312178   |      59873.75       |
| 22   | Deadeye      |      1.8       |       36000       |        0.7        |   0.3494877216   |        55341        |

---

## Additive vs Multiplicative Effects

Broadly, effects that increase damage are multiplicative while effects that increase attack power are additive.
When min-maxing, if possible you want to avoid using multiple additive effects when multiplicative effects are available, 
since additive effects don't scale together as well.

As an example, imagine a hypothetical Artillerist with 1000 attack power as a baseline. Consider level 3 of the following engravings: 
**Cursed Doll** (Atk Power +16%), **Mass Increase** (Atk Power + 18%), Raid Captain (Damage +18% at movement speed 140%). \
For the sake of clarity in showing how additive vs multiplicative works, imagine that **Grudge** level 3 gives 18% Damage (in reality it's 20%). Then: 

 - With Cursed Doll, attack power is $1000(1 + 0.16) = 1160$
 - With Mass Increase, attack power is $1000(1 + 0.18) = 1180$
 - With Cursed Doll + Mass Increase, attack power is $1000(1 + 0.16 + 0.18) = 1340$
 - With Cursed Doll + Raid Captain, attack power is $(1000(1 + 0.16)) \times 1.18 = 1368$ (2.1% better than the previous combination)
 - With Cursed Doll + Mass Increase + Raid Captain (2 additive, one multiplicative), attack power is $(1000(1 + 0.16 + 0.18)) \times 1.18 = 1581$
 - With Cursed Doll + Raid Captain + 18% Grudge (1 additive, 2 multiplicative), attack power is $(1000 * (1 + 0.16)) \times 1.18 \times 1.18 = 1615$ (2.2% better than the previous combination)

---

## Combat Engravings

There are 43 Combat Engravings currently available but this section will only discuss some of them. Not all combat engravings
are useful. ~~Strikethrough~~ indicates the engraving is a budget or low-tier/suboptimal choice for that class. This is judged off rank on the class build list and educated guessing, please correct if you see an error.

### Damage

1. **All-Out Attack**: (+4/10/20%) Damage, (+5/10/15%) Holding and Casting Skill Speed)
    - Classes: Sorceress (Igniter, ~~Reflux~~)
2. **Ambush Master**:	(+5/12/25%) Damage for successful back attacks
    - Classes: Berserker (Technique, ~~Mayhem~~), Striker, Soulfist (Robust Spirit), Scrapper, Wardancer, Glaivier (Control), Deadeye, Deathblade, Shadowhunter (Perfect Suppression)
3. **Barricade**: (+3/8/16%) Damage to foes while shielded
    - Classes: Gunlancer (Blue), Destroyer (Gravity Training), Artillerist (Budget), Arcanist (Empress's Grace)
4. **Grudge**: (+4/10/20%) Damage to Boss and above level monsters, Incoming Damage +20%
    - Classes: All DPS
5. **Hit Master**: (+3/8/16%) damage to attacks other than Front and Back Attack. Does not apply to Awakening skills.
    - Classes: Sharpshooter, Artillerist, Gunslinger, Shadowhunter (Demonic Impulse), Sorceress, Arcanist
6. **Master Brawler**: (+5/12/25%) Damage to Head Attack skills.
    - Classes: Gunlancer (Red), Destroyer
7. **Master's Tenacity**: (+3/8/16%) Outgoing damage when you are at or below 50% HP
    - Classes: Berserker (Mayhem)
8. **Raid Captain**: Outgoing Damage (+10/22/45%) of basic Move Speed bonus percentage
    - Wording is a little misleading; effects such as Mayhem's +15% move speed bonus also count for Raid Captain.
    - Move speed cap of 140% means this is an 18% damage buff at the cap.
    - Classes: Berserker, Paladin (Judgment), Soulfist (Energy Overflow), Wardancer (First Intention), Glavier (Control), ~~Gunslinger~~, ~~Sharpshooter~~, ~~Shadowhunter~~, Arcanist (Order)
9. **Stabilized Status**: (+3/8/16%) damage when your HP is above 80%
    - Classes: Gunlancer (Blue), Paladin (~~Judgment~~)
10. **Super Charge**: Charge skills' charging speed (+8/20/40%). Damage (+4/10/20%).
    - Classes: Berserker (Technique), Gunlancer (Red), Destroyer (Hammer), Deathblade

### Attack Power

1. **Cursed Doll**: +3/18/16% Attack power, -25% healing (natural recovery excluded)
    - Classes: All DPS
2. **Mass Increase**: (+4/10/18%) Attack power. Attack speed -10%
    - Classes: Berserker (~~Mayhem~~), Striker (~~Esoteric Flurry~~), Soulfist (~~Robust Spirit~~), ~~Wardancer~~, Glavier (Pinnacle)

### Crit Damage

1. **Keen Blunt Weapon**: (+10/25/50%) Crit Damage, chance of -20% damage on all attacks
    - Classes: Berserker, Gunlancer (Red), ~~Paladin (Judgment)~~, Destroyer (Hammer), Striker, Soulfist (Energy Overflow), ~~Scrapper~~, Wardancer, Glaivier, Deadeye, Sharpshooter, Artillerist, Gunslinger, ~~Deathblade~~, Shadowhunter, Bard (True Courage), Arcanist
    - Testing indicates chance of damage reduction to be 10%. [https://lostark.fandom.com/wiki/Keen_Blunt_Weapon]
    - Expected damage drawback is therefore -2%.
    - Need 60% crit rate at 200% crit damage to be efficient [https://www.reddit.com/r/lostarkgame/comments/spt8zp/keen_blunt_weapon_efficiency_table/]
    - At level 3, increased damage as a function of crit rate $x$ and crit damage $y$ is:    
      $f(x,y) = 0.98((0.5+y)x + 1)$
    - To calculate the increased damage (versus no KBW) as a function of crit rate $x$ and crit damage $y$:    
      $g(x,y) = { 0.98((0.5 + y)x + 1) \over (yx + 1) }$ 
    - Therefore for basic 200% crit damage we have $y = 1$ and this simplifies to:  
      $f(x) = 0.98(1.5x + 1)$
    - Damage increase percentage:  
      $g(x) = { 0.98(1.5x + 1) \over (1x + 1) }$
    - In this table, column headings are your crit rate and row headings are your pre-KBW crit damage bonus (100% for basic
      characters with no other effects applied). You want to be at or above 16%, or roughly the same as Cursed Doll, 
      otherwise a different engraving likely offers a higher damage increase.

| $g(x,y)$ |     40    |     45    |     50    |     55    |     60    |     65    |     70    |     75    |     80    |     85    |     90    |     95    |    100    |
|----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| 100      |     12    |   13.21   |   14.33   |   15.39   | **16.37** |  **17.3** | **18.18** |   **19**  | **19.78** | **20.51** | **21.21** | **21.87** |  **22.5** |
| 105      |    11.8   |   12.97   |   14.07   |   15.08   | **16.04** | **16.93** | **17.77** | **18.56** |  **19.3** | **20.01** | **20.67** |  **21.3** |  **21.9** |
| 110      |   11.61   |   12.75   |   13.81   |   14.79   |   15.71   | **16.57** | **17.38** | **18.14** | **18.85** | **19.52** | **20.16** | **20.76** | **21.33** |
| 115      |   11.42   |   12.53   |   13.56   |   14.51   |    15.4   | **16.23** |   **17**  | **17.73** | **18.42** | **19.06** | **19.67** | **20.25** | **20.79** |
| 120      |   11.24   |   12.32   |   13.31   |   14.23   |   15.09   |   15.89   | **16.64** | **17.34** |   **18**  | **18.62** |  **19.2** | **19.75** | **20.27** |
| 125      |   11.07   |   12.11   |   13.08   |   13.97   |    14.8   |   15.57   | **16.29** | **16.97** |  **17.6** | **18.19** | **18.75** | **19.28** | **19.78** |
| 130      |   10.89   |   11.91   |   12.85   |   13.71   |   14.52   |   15.26   |   15.96   | **16.61** | **17.22** | **17.79** | **18.32** | **18.83** |  **19.3** |
| 135      |   10.73   |   11.72   |   12.63   |   13.47   |   14.24   |   14.96   |   15.63   | **16.26** | **16.85** | **17.39** | **17.91** | **18.39** | **18.85** |
| 140      |   10.56   |   11.53   |   12.41   |   13.23   |   13.98   |   14.68   |   15.32   |   15.93   | **16.49** | **17.02** | **17.51** | **17.98** | **18.42** |
| 145      |   10.41   |   11.34   |    12.2   |   12.99   |   13.72   |    14.4   |   15.02   |    15.6   | **16.15** | **16.66** | **17.13** | **17.58** |   **18**  |
| 150      |   10.25   |   11.16   |     12    |   12.77   |   13.47   |   14.13   |   14.73   |   15.29   |   15.82   | **16.31** | **16.77** |  **17.2** |  **17.6** |
| 155      |    10.1   |   10.99   |    11.8   |   12.55   |   13.23   |   13.87   |   14.45   |   14.99   |    15.5   |   15.97   | **16.41** | **16.83** | **17.22** |
| **160**  |    9.95   |   10.82   |   11.61   |   12.34   |     13    |   13.61   |   14.18   |    14.7   |   15.19   |   15.65   | **16.07** | **16.47** | **16.85** |
| 165      |    9.81   |   10.65   |   11.42   |   12.13   |   12.77   |   13.37   |   13.92   |   14.42   |    14.9   |   15.34   |   15.75   | **16.13** | **16.49** |
| 170      |    9.67   |   10.49   |   11.24   |   11.93   |   12.55   |   13.13   |   13.66   |   14.15   |   14.61   |   15.03   |   15.43   |    15.8   | **16.15** |
| 175      |    9.53   |   10.34   |   11.07   |   11.73   |   12.34   |    12.9   |   13.42   |   13.89   |   14.33   |   14.74   |   15.13   |   15.48   |   15.82   |
| 180      |    9.4    |   10.18   |   10.89   |   11.54   |   12.13   |   12.68   |   13.18   |   13.64   |   14.07   |   14.46   |   14.83   |   15.18   |    15.5   |
| 185      |    9.26   |   10.03   |   10.73   |   11.36   |   11.93   |   12.46   |   12.95   |   13.39   |   13.81   |   14.19   |   14.55   |   14.88   |   15.19   |
| 190      |    9.14   |    9.89   |   10.56   |   11.18   |   11.74   |   12.25   |   12.72   |   13.15   |   13.56   |   13.93   |   14.27   |    14.6   |    14.9   |
| 195      |    9.01   |    9.74   |   10.41   |     11    |   11.55   |   12.05   |    12.5   |   12.92   |   13.31   |   13.67   |   14.01   |   14.32   |   14.61   |
| 200      |    8.89   |    9.61   |   10.25   |   10.83   |   11.36   |   11.85   |   12.29   |    12.7   |   13.08   |   13.43   |   13.75   |   14.05   |   14.33   |
      
    

### Crit Rate

1. **Adrenaline**:  (+0.3/0.6/1%) Attack Power for 6s after using skills. Stacks up to 6x. (+5/10/15%) Crit Rate when max stacks reached.
    - Classes: Gunlancer, Paladin (Judgment), Striker, Soulfist, Scrapper, Wardancer (Esoteric), Glavier (Control), Deadeye, Artillerist (Swiftness-based Firepower Enhancement),  Gunslinger, Deathblade, Shadowhunter, Bard (~~True Courage~~), Sorceress, Arcanist
2. **Precise Dagger**: (+4/10/20%) Crit Rate. Crit Damage -12%
    - Classes: Gunlancer (Red), Soulfist (Energy Overflow), Deadeye (Pistoleer), Shadowhunter (Perfect Suppression), Sorceress
    - As a function of your crit rate $x$ and crit damage $y$ without Precise Dagger, this formula defines the expected damage increase of
    a level 3 engraving. (e.g., using $x = 0.27$ and $y = 1$ for a 27% sheet crit rate and baseline crit damage gives a 
    damage increase of roughly 11.3%):  
    $g(x,y) = {(x + 0.2)(y - 0.12) + 1 \over (xy + 1)}$ 
    - Simplified for baseline crit damage as a function of crit rate $x$:    
    $f(x) = {0.88(x + 0.2) + 1 \over x + 1}$
    - The above implies that for baseline crit damage you need at least 14.7% crit rate for Precise Dagger to be a benefit.
    
### Attack Speed

1. **Spirit Absorption**: (+3/8/15%) Attack/Move Speed
    - Classes: Berserker (Technique), Gunlancer, Paladin (Aura), Destroyer, Striker, Soulfist (Robust Spirit), Scrapper (Shock), Deadeye (Enhanced Weapon), Gunslinger (~~Peacemaker~~), Shadowhunter, Bard (True Courage, Spec-based Desperate Salvation)

### Support

1. **Expert**: (+6/14/24%) Shield and Healing effectiveness on all Party Members. If target's HP is 50% or lower, (+3/7/12%) effectiveness
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
2. **Heavy Armor**: (+20/50/100%) to All Defense. This additional defense is immune to defense reduction effects.
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
3. **Drops of Ether**: (Cooldown: 60/30/10s) Attack have a chance to create an Ether within 8 meters.
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
    - Buffs last 30s.
    - Orbs disappear after about 25s.
    - Orbs: MP (??? Mana), Flash (15% Crit Rate), Strength (10% Atk Power), Wind (10% Movement Speed), Defense (10% All Defenses)
    - Chance to drop unknown, but it's high enough that the cooldown is more the limiting factor.
5. **Max MP Increase**: (+5/15/30%) Max MP
    - Classes: Bard (Swiftness-based Desperate Salvation)
6. **Vital Point Hit**: Stagger attack effectiveness (+6/18/36%).
    - Classes: Paladin (Aura), Bard (Desperate Salvation)

### Other

1. **Awakening**: (-10/25/50%) Awakening Skill Cooldown.  (+1/2/3) maximum uses.
    - Classes: Berserker (Technique), Gunlancer (Blue), Paladin, Soulfist (Robust Spirit), Glavier (Pinnacle), Bard (Desperate Salvation), Arcanist (Order)
2. **Preemptive Strike**: (+30/80/160%) damage and guaranteed crit when attacking Challenge or lower monsters with full HP. 
    - Classes: Any.
    - Used on Chaos Dungeon builds to speed things up.
4. **Sight Focus**: Gain (+8/16/28%) damage for 6s when "!!!!!" is entered into normal chat. Does not apply to basic attacks, and only half as effective on Awakening skills. Cooldown 30s.
    - Usable by bursty DPS classes, but kind of a meme engraving since better choices are typically available.
5. **Ether Predator**: Attacking a foe creates an Ether that only you can collect. On collecting the Ether, 
   Atk. Power (+0.2/0.3/0.5%) for 90s and All Defense (+0.3/0.6/1%). Stacks up to 30 times. Chance on Ether collection 
   to increases the stack by 3. (Cooldown: 10s)
    - Balanced on both sides of the ball, adding 15% attack power with 30% defense at max stacks.
    - Slow to build to max (5m).
<!-- todo: contender for chaos dung? -->
    
---

## Class Engravings

Each class has 2 engravings for a total of 46.

### Warrior

#### Berserker
1. **Berserker's Technique**: While bursting, Crit Damage (+35/50/70%). Negates Exhaustion after Burst ends.
2. **Mayhem**:
   - Fury meter remains at max and turns into Burst mode with the power of darkness.
   - Outgoing Damage (+4/9/18%)
   - Atk. and Move Speed +15%.
   - All incoming Damage -65% in Burst mode.
   - When turning into Burst mode, converts into 25% Max HP, and it cannot be exceed even when Healing is applied. Can only receive 25% of shield's effect.
   - Press the X key to cancel Burst mode to recover 25% of Max HP, but cannot Burst for 30s.
   
#### Destroyer
1. **Gravity Training**:
   - During combat, the Gravity Meter recovers (1/1.5/2%) every 1s.
   - Basic Attack and Vortex Gravity Crit Rate +(10/20/30%) and (+4/10/20%) Attack Damage to foes during Hypergravity Mode.
2. **Rage Hammer**: When using a Gravity Release Skill, Crit Rate (+3/4/5%) and Crit Damage (+5/10/15%) based on the amount of Cores used.

#### Gunlancer
1. **Combat Readiness**: Normal skills Damage +20%. Shield Amount (+30/40/50%) in Defensive Stance. Damage (+4/5/6%) for 10s when hit while in Defensive Stance (stacked up to 3 times, once every 1s).
    - Efficient with level 1 engraving.
2. **Lone Knight**: Gunlance skill Crit Rate (+5/10/15%). Crit Damage (+30/40/50%). Battlefield Shield cannot be used. Shield Meter consumption during Defense Stance +100%.

#### Paladin
1. **Blessed Aura**: With Holy Aura, Damage received (-10/15/20%) and 2% of Max HP restored every (2.5/2/1.5s) for all party members.
2. **Judgment**: Punishment Damage (+15/20/25%). When Punishment skill hits. Piety Meter gain +100%. Duration of Sacred Executioner +100%.

#### Slayer
1. **Predator**: Fury Meter (+3/6/10%) and MP (+1/2/3%) when hitting and enemy and absorbing their vigor. (Cooldown: 1s) In Burst
Mode, Crit Damage (+10/25/40%) and gain Fatigue every 3s, and cannot use Bloodlust. When Burst Mode ends, the duration of Exhaustion
will be reduced according to the stacks of Fatigue. The Fury Meter is fully recovered when Exhaustion ends.
2. **Punisher**: Damage (+7/15/25%) while in Burst Mode and Bloodlust Crit Rate (+5/10/20%). Fury gain -25% and Burst
duration -50%. When Burst Ends, Exhaustion does not occur.

### Martial Artist

#### Glaivier
1. **Control**: Cannot use Focus stance. Flurry skills Damage (+18/27/36%).
2. **Pinnacle**: Adds Pinnacle: Flurry/Focus (I/II/III) instead of the Flurry/Focus Stage 3 effect added upon changing stances while the Dual Meter is maxed at Level 3.
    - Pinnacle: Flurry (I/II/III): Atk. Speed (+12.5/13.8/15%), Damage (+12.5/13.8/15%), Crit Rate (+20/22.5/25%)
    - Pinnacle: Focus (I/II/III): Move Speed +15%, Damage (+15/17.5/20%), Crit Damage (+37.5/43.8/50%)

#### Scrapper
1. **Shock Training**: Shock skill Damage (+10/15/20%). (2/3/4%) of max Shock Energy recovered every 1s.
2. **Ultimate Skill: Taijutsu**: Natural recovery speed of Stamina Energy (+300/450/600%). Stamina skill damage (+30/45/60%). Shock skill damage -30%.

#### Soulfist
1. **Energy Overflow**: Energy does not go below 1, but the additional Energy recovery effect is not applied during Hype. If Energy is below 30%, Damage (+5/10/15%) to foes.
2. **Robust Spirit**: When using Hype, enters level 3 immediately. While in Hype Mode, Energy recovery speed +200%. Damage (+10/20/30%).
 
#### Striker
1. **Deathblow**: Max number of Esoteric Orbs +1. Esoteric skills consume all Esoteric Orbs and inflict (+17/26/35%) Damage per Esoteric Orb consumed.
2. **Esoteric Flurry**: Only 1 Esoteric Orb is used when using Esoteric Skill, and Esoteric Skill Damage (+8/13/18%).

#### Wardancer
1. **Esoteric Skill Enhancement**:  Max number of Esoteric Orbs +1. Esoteric skill inflict (+8/10/12%) Damage per Esoteric Orb you have.
2. **First Intention**: Damage to foes (+15/20/25%), but you can no longer gain Esoteric Meter.

### Gunner

#### Artillerist
1. **Barrage Enhancement**: Barrage Skill Damage (+5/12/20%). Barrage Skill Crit Rate (+20/30/40%). Barrage Meter Gain +30%. Does not enter in cooling state.
2. **Firepower Enhancement**: When the firepower meter is full, Overheat effect is triggered. Normal Skill Damage (+4/10/20%) and Firepower Meter Duration (+8/10/12s). When not in Barrage Mode, Incoming Damage (-5/10/15%).

#### Deadeye
1. **Enhanced Weapon**: Changing stances enhances your weapon. Crit Rate (+20/25/30%) for 9s.
2. **Pistoleer**: Can only use Handgun Stance, Handgun Skill Damage (+30/50/70%). Stagger Damage +40%. Awakening Skill Damage (+15/22/30%).

#### Gunslinger
1. **Peacemaker**: Atk. Speed in Handgun Stance (+8/12/16%). Crit Rate in Shotgun Stance (+15/20/25%). Damage to foes +10% and additional Damage (+10/20/30%) to targets with 50% or lower HP for 9s while in Rifle Stance.
2. **Time to Hunt**: Crit Rate (+20/30/40%) for Handgun and Rifle skills. Unable to use Shotgun Stance.

#### Machinist
1. **Arthetinean Skill**: Increases damage of Drone and Join skills by (15/20/25%) and increases Battery Max by (10/15/20%). Increase Move Speed by 10% when a Drone is attached to a Machinist.
2. **Evolutionary Legacy**: During Hypersync Mode, on hit, Sync skills inflict Damage (+2/4/6%) (Max. 3 stacks) and Cooldown -0.5s. Also, Hypersync Mode returns 40% of its Core Energy cost when canceled.

#### Sharpshooter
1. **Death Strike**: When using Last Rush, recover 50% of the remaining Hawk Meter. Hit foe Damage taken (+20/30/40%) for 8s.
2. **Loyal Companion**: 
    - Summons Silverhawk MK-II, allowing Move Speed +4%, Silver Hawk's Basic AoE Radius +60%, Silverhawk's Basic Attack Damage (+100/200/300%), and Silverhawk's summon duration (+30/60/100%). 
    - On basic attack or Wings of Storm hit, foes get a Mark of Death. Foe incoming Damange (+4/9/14%). 
    - Additionally, Hawk Meter Natural Recovery (+10/20/30%) during combat.



### Mage 

#### Arcanist
1. **Empress's Grace**: 4-stack Ruin Damage (+20/25/30%). When Ruin hits, recover 30% of consumed MP.
2. **Order of the Emperor**: Normal Skills Deck Meter gain +50%. Damage (+10/20/30%) and an Emperor Card is added to the
  deck. The Emperor Card deals great Damage in the surrounding area when used.

#### Bard
1. **Desperate Salvation**: When the recovery effect ends, an additional recovery effect is activated, recovering (8/16/24%) of your Max HP.
2. **True Courage**: Your outgoing Damage from Serenade of Courage (+10/15/20%) and Crit Rate +10%.

#### Sorceress
1. **Igniter**: When Magick Amplification is triggered, normal skills' Cooldown -50%. During Magick Amplification, Crit 
   Rate (+10/17/25%) and Crit Damage (+20/35/50%).
3. **Reflux**: Disables Arcane Rupture, but Damage of skills (except Awakening and Movement skills) (+8/12/16%) and Cooldown (-3/6/10%).

#### Summoner
1. **Communication Overflow:** Summon duration (+5/10/20%). Damage (+10/17/25%). Atk Speed and Move Speed (+3/6/10%).
Command Skill Cooldown (-3/6/10%) for Maririn, Pauru, Elcid, Shurdi, and Kelsion.
2. **Master Summoner**: Enhances the Ancient Elemental Skill. Elemental Orb cost -1. Normal Skill Damage and Ancient
Elemental Skill Damage (+2/5/10%) and Crit Rate (+3/8/16%).

### Assassin

#### Deathblade
1. **Remaining Energy**: Art does not consume Art Meter for 2s when activated. 
   Atk./Move Speed (+6/9/12%) on Surge. Atk. Power (+8/10/12%), (+16/20/24%), (+25/30/36%) depending on your Surge level, for 30s.
2. **Surge**:  
    - Deathblade Surge is cast at the max level of Surge Zero form, regardless of the number of Death Orbs you have. 
    - Current Deathblade Surge does not activate the effect of Remaining Energy. 
    - When Arts is activated and skills other than Basic Attacks and Awakening Skills hit, the Surge Enhancement effect stacks every 0.4 seconds to a max of 20 stacks. 
    - This effect causes Deathblade Surge Damage to increase up to (100/110/120%), Damage increases even more with larger stacks.
    - Each stack increases Atk. Power additionally by (+0/0.5/1%).
    - When Death Trance ends, gain up to 100% Death Orb Meter for each Surge Enhancement effect you have (5% each).

#### Reaper
1. **Hunger**: Chaos Meter +30%. Atk Power (+12/18/25%) when the Chaos Meter is full.
2. **Lunar Voice**:  Swoop Damage (+120/140/160%) instead of the Swoop Enhancement effect that stacks every 1s upon switching to Persona Mode.

#### Shadowhunter
1. **Demonic Impulse**: The Composure effect does not activate when Demonize ends. Upon Demonize, Demonic Skill Cooldown is reset, and Crit Rate (+0/15/30%) while Demonic Mode is active.
2. **Perfect Suppression**: Normal Skill Damage (+20/25/30%). Shadowburst Meter +50% for all skills. Disables Demonize.

### Specialist

#### Artist
1. **Full Bloom**: When casting Sunrise, the energy spreads to recover HP of Party Members within 24m of the Artist and
   Sun Marble. It recovers up to (7/11/15%) of the Artist's Max HP.
2. **Recurrence**: Upon using Moonfall or Sunrise, gain an effect that increases the Artist's Crit Rate by (6/9/12%) and
   Crit Damage by (20/30/40%) for 60s.

---

## Engraving Drop Rates

### Ability Stones
Ability stones can only have battle engravings thus there are ${43 \choose 2} = 903$ possibilities for ability stone
(positive engravings only). If you need a specific negative engraving, multiply by four to figure that 1 out of every 3612
stone drops is the one you want.

### Accessories
*Assuming* all engravings are equally likely to appear on a given relic accessory, there are $43 + 2 = 45$ 
possible engravings for every drop (43 combat, 2 class). This means there are ${45 \choose 2} - 1 = 989$ possible 
configurations of positive engravings alone (subtract 1 because you cannot have both class engravings on the same piece). 
For rings and earrings, this means that a piece with your ideal stats and 
engravings (say, Specialization with Ambush Master and Remaining Energy) will drop one out of every 
$989 \times 6 = 5934$ times. Multiply by $3$ again for a specific engraving bonus configuration (i.e., relic gear can 
be +3/+3, +3/+4, or +3/+5; therefore to get a +3/+5 with the desired combat stat it's 1 in every $5934 \times 3 = 17802$, ancient
is $23736$). Necklaces are rarer since each you need 2 combat stats to line up, reducing the ideal drop to one out of 
every $17802 \times 6 = 106812$ times ($142416$ for a 6/3 ancient necklace).

---

## Gem Conversion Table

| Level | Level 1 Gems | Number of Boss Rushes | Level 3 Gems | Number of Ebony Cubes (3rd Forb.) |
|-------|--------------|-----------------------|--------------|-----------------------------------|
| 1     | 1            | 0.02                  | 1/9          | 0.02                              |
| 2     | 3            | 0.05                  | 1/3          | 0.055                             |
| 3     | 9            | 0.1                   | 1            | 0.17                              |
| 4     | 27           | 0.4                   | 3            | 0.5                               |         
| 5     | 81           | 1.3                   | 9            | 1.5                               |
| 6     | 243          | 3.0                   | 27           | 4.5                               | 
| 7     | 729          | 11.6                  | 81           | 13.5                              |
| 8     | 2187         | 34.7                  | 243          | 40.5                              |
| 9     | 6561         | 104.1                 | 729          | 121.5                             |
| 10    | 19683        | 312.4                 | 19683        | 364.5                             |

---

## Rewards

### Boss Rush
Total Rewards:
 - 7 Level 3 Gems
 - 18 Honor Leapstones
 - 18 Great Honor Leapstones
 - Chance for Masterpieces #15, 25, 35, 41, 46 from Chests IV-VI
 
#### By Wave
| Wave  | Reward                                      | Bonus                              |
|-------|---------------------------------------------|------------------------------------|
| 1-5   | Hall of the Sun \[Normal\] Reward Chest I   | 1 Honor Leap Stone (Bound)         |
| 6-8   | Hall of the Sun \[Normal\] Reward Chest II  | 1 Honor Leap Stone (Bound)         | 
| 9-10  | Hall of the Sun \[Normal\] Reward Chest III | 1 Great Honor Leap Stone (Bound)   | 
| 11    | Hall of the Sun \[Normal\] Reward Chest IV  | 1 Great Honor Leap Stone (Bound)   | 
| 12-14 | Hall of the Sun \[Normal\] Reward Chest V   | 1 Great Honor Leap Stone (Bound)   | 
| 15    | Hall of the Sun \[Normal\] Reward Chest VI  | 1 Great Honor Leap Stone (Bound)   | 

### Ebony Cube
Typical rewards:
 - 3rd Forbiddance: 6 Level 3 Gems, 4 Epic Creation Fragments, 1 Epic Book, 25 Marvelous Leaps, 11 Solar Grace, 6 Solar Blessing, 2 Solar Protection, 110k silver
 - 2nd Forbiddance: 4 Level 3 Gems, 3 Epic Creation Fragments, 1 Epic Book, 14 Marvelous Leaps, 8 Solar Grace, 4 Solar Blessing, 2 Solar Protection, 105k Silver
 - 1st Forbiddance: 7 Level 2 Gems, 1 Epic Creation Fragment, 1 Epic Book, 20 Great Honor Leaps, 6 Solar Grace, 3 Solar Blessing, 1 Solar Protection

---

## MVP Titles

### Damage
 - Fighter: &lt; 29%
 - Upright Fighter: 30 - 39%
 - Cruel Fighter: 40%+

### Defeated Foe
- Slayer: &lt; 29%
- Cold Blooded Slayer: 30 - 39%
- Ruthless Slayer: 40%+

### Stagger
- Annihilator: &lt; 29%
- Cruel Annihilator: 30 - 39%
- Advancing Annihilator: 40%+

### Party Recovery
 - Healer:  ??? &lt; 21%
 - Gentle Healer: 21 - 23%
 - Noble Healer: 24% - 100%

### Party Defense
 - Guardian: 15 - 19%
 - Moon's Guardian: 20 - 24%
 - Sun's Guardian: 26 - 57%

### Solo Defense
 - Commander: 15 - 18%
 - Reliable Commander: 20 - 22%
 - Seraphic Commander: 27 - 39%

### Battle Item Contribution
 - Tactician: 28 - 40%
 - Cool-headed Tactician: 42 - 55%
 - Outstanding Tactician: 65 - 73%

### Supporter
## 4 Man
 - Supporter: 19%
 - Noble Supporter: 20 - 24%
 - Radiant Supporter: 25%+
## 8 Man
 - Supporter: 9%
 - Noble Supporter: 10 - 12%
 - Radiant Supporter: 12%+

Sources: [https://www.reddit.com/r/lostarkgame/comments/tiaenl/mvp_percentages_again/], [https://www.reddit.com/r/lostarkgame/comments/11xbjr8/what_are_the_support_mvp_titles_and_percentages/]

---

## Examples Used to Calculate the Stat Rates

#### Deathblade

 - Crit: 591 gives 21.15% crit rate (0.0357868% per)
 - Spec: 1441 gives +164.92% surge skill dmg (0.114448% per), +82.46% blade art meter recovery through attacks (approx 0.0572241% per), +41.23% skill cooldown reduction by blade art (approx 0.0286121% per), +78.74% awakening skill dmg (0.0546426% per)
 - Domination: 53 gives 3.25% damage to pushed/debuffed foes (approx 0.0613207% per), 3.78% dmg to staggered foes (approx 0.0713207% per)
 - Swift: 41 gives +0.70% atk/move spd (0.0170732% per), -0.88% skill cooldown (0.0214634% per)
 - Endurance: 35 gives +2.86% phy/mag defense (0.0817143% per), +0.89% shields (0.02542857% per), +1.25% healing (0.0357143% per)
 - Expertise: 45 gives +1.93% debuff duration to foes (approx 0.042889% per), -1.61% debuff duration to self (0.0357778% per), stagger damage +1.28% (approx 0.0284444% per)

#### Bard

 - Crit: 42 gives 1.50% crit rate (0.0357143% per)
 - Spec: 464 gives +13.27% serenade of salvation skill recovery amt, +23.23% serenade of courage buff efficiency, +18.58% serenade meter, +25.35% awakening skill dmg (0.0546336% per)
 - Domination: Same as DB
 - Swift: 1356 gives +23.29% atk/move speed (0.0171755% per), -29.11% skill cooldown (0.0214676% per)
 - Endurance: Same as DB
 - Expertise: Same as DB

#### Berserker

 - Crit: 807 gives 28.88% crit rate (0.0357868% per)
 - Spec: 45 gives 2.57% fury gain, 8.04% burst duration, 7.72% bloody rush damage, 2.45% awakening skill damage (0.054444444 per)
 - Domination: Same as DB
 - Swift: 955 gives +16.40% atk/move speed (0.0171728% per), -20.50% skill cooldown (0.0214659% per)
 - Endurance: Same as DB
 - Expertise: Sames as DB

#### Gunlancer

 - Crit: 474 gives 16.96% crit rate (0.0357805% per)
 - Spec: 1421 gives  142.30% shield meter recovery (approx 0.1001407 per), 101.64% battlefield shield skill's shield amt, 223.61% basic skill dmg, 77.65% awakening skill dmg (0.0546446% per)
 - Domination: Same as DB
 - Swift: Same as DB
 - Endurance: Same as DB
 - Expertise: Same as DB

#### Artillerist

 - Crit: 487 gives 17.43% crit
 - Spec: 1343 gives +96.06% bombard skill dmg (0.0715264% per), +134.49% firepower skill effectiveness (0.10014147% per), 73.39% awakening dmg (0.0546463% per)
 - Domination: Same as DB
 - Swift: Same as DB
 - Endurance: Same as DB
 - Expertise: Same as DB

#### Scrapper

 - Crit: 888 gives  31.78% crit rate (0.0357883% per)
 - Spec: 45 gives 2.57% shock skill dmg (0.0571111% per), +1.60% stamina gained with shock skills (0.0355555% per), 2.45% awakening skill dmg (0.054444444 per)
 - Domination: Same as DB
 - Swift: 491 gives  +8.43% atk/move speed (0.0171690% per), -10.54% skill cooldown (0.0214664% per)
 - Endurance: Same as DB
 - Expertise: Same as DB

#### Sharpshooter

 - Crit: 1448 gives 58.82% crit rate
 - Spec: 494 gives +35.33% hawk meter gained (0.0715182% per), +53.00% silverhawk skill dmg 
  (0.1072874% per), +26.99% awakening skill dmg (0.0546356% per)
 - Domination: 153 gives 9.38% dmg to pushed/debuffed foes (0.0613072% per), 10.92% dmg to staggered foes (0.0713725% per)
 - Swift: 457 gives +7.85% atk.move speed (0.0171772% per), -9.81% skill cooldown (0.0214661% per)
 - Endurance: Same as DB
 - Expertise: Same as DB

---

## Random stuff

1. A series of reddit posts about stat calculations, no idea if they're accurate:
    - [https://www.reddit.com/r/lostarkgame/comments/swkw21/how_some_stats_are_calculated_attack_power_damage/]
    - [https://www.reddit.com/r/lostarkgame/comments/vaq858/how_some_stats_are_calculated_pt_ii/]
    - [https://www.reddit.com/r/lostarkgame/comments/w26xpq/how_some_stats_are_calculated_pt_iii_item_level/]
2. Ability stone calculators:
    - [http://lostarktoolkit.com]
    - [https://lostark.meta-game.gg/ability-stone-calculator]
    - [https://lostarkfoundry.com/ability-stone-calc/]