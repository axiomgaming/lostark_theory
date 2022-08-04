# Notes on Lost Ark Theorycrafting

## Attack Affixes

1. **Front Attack**: Inflicts 20% more damage and 10% increased stagger/weak point damage when hitting from the front arc of the enemy. Master Brawler engraving increases this by +5/12/25%.
2. **Back Attack**: Inflicts 5% more damage with a 10% increased crit rate when hitting from the rear arc of the enemy. Ambush Master engraving increases this by +5/12/25%.
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
a knockdown (e.g., Argos landing) with spacebar.

## Info about combat stats, caps, character sheet details

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
 - **Crit Damage**: 200% baseline (i.e., +100%). Assume a theoretical hit that does 100 damage. With default baseline crit damage, Keen Blunt 3 and 60% crit rate, your expected damage increase is 16.375% (over no KBW), which implies that the odds of a hit's damage being nerfed by KBW are 10% and the expected baseline damage is (100 - 0.2x0.1) = 98. See: [https://www.reddit.com/r/lostarkgame/comments/spt8zp/keen_blunt_weapon_efficiency_table/] [https://lostark.fandom.com/wiki/Keen_Blunt_Weapon]
 - **Move Speed**: Caps at 140% (equivalent to approx raw swiftness of 2329; obviously this is not reachable, instead you need move speed buffs like Mayhem's 15% which reduces the swiftness to cap to a more reasonable 1456). This cap implies Raid Captain caps at 18% increased damage.
 - **Movement Skill**: Space bar dash. Cooldown is class-dependent. Separately there is the Stand Up ability, which is also triggered with space bar when knocked down and has its own separate cooldown.

---

## Defense
 - Survivability depends on total HP and damage mitigation. Raw incoming damage is mitigated (reduced) then subtracted
   from your HP. If your HP goes to 0 you get to observe.
 - Damage mitigation is a function of Armor Coefficient $a$:    
   $f(a) = 1 - {1 \over (1 + (0.0001535 \times 5000a))} = 1 - (1 + (0.7675a))^{-1} = {0.7675a \over 0.7675a + 1}$
 - HP is a function of HP coefficient $h$ and ability stone vitality $v$: $f(h,v) = hv$
 - Actual damage taken is a function of mitigation $m$ and raw damage $d$: $f(m,d) = (1-m)d$
 - Putting it all together we get damage taken as a function of armor coefficient $a$ and raw damage $d$:    
   $d_{taken}(a,d) = d(1 - {0.7675a \over 0.7675a + 1})$
 - This table translated from: [https://docs.google.com/spreadsheets/d/10NC1mgY8HQKmaU_IryqGfPM7dJUwaJPfw2G2kPGOFs8/edit#gid=0] found via [https://infolao.tistory.com/entry/Lostark-guide-Class-HP-Armor-Coefficient]

| Class         | HP Coefficient  | HP from 20k Vitality Ability Stone | Armor Coefficient | Damage mitigated ratio | Max incoming damage |
|:--------------|:---------------:|:----------------------------------:|:-----------------:|:----------------------:|:-------------------:|
| Gunlancer     |       2.6       |               52000                |        1.3        |      0.4994368665      |       103883        |
| Destroyer     |       2.3       |               46000                |       1.15        |      0.4688267711      |      86600.75       |
| Scrapper      |       2.3       |               46000                |        1.1        |      0.4577741629      |       84835.5       |
| Berzerker     |       2.2       |               44000                |        1.1        |      0.4577741629      |        81147        |
| Glaivier      |       2.2       |               44000                |       1.05        |      0.446251817       |       79458.5       |
| Wardancer     |       2.2       |               44000                |       1.05        |      0.446251817       |       79458.5       |
| Paladin       |       2.1       |               42000                |        1.1        |      0.4577741629      |       77458.5       |
| Soulfist      |       2.1       |               42000                |       1.05        |      0.446251817       |      75846.75       |
| Deathblade    |       2.2       |               44000                |        0.9        |      0.408546503       |        74393        |
| Artillerist   |       2.1       |               42000                |        0.9        |      0.408546503       |       71011.5       |
| Shadowhunter  |        2        |               40000                |       0.85        |       0.3948105        |        66095        |
| Summoner      |        2        |               40000                |        0.8        |      0.3804213135      |        64560        |
| Arcana        |        2        |               40000                |        0.8        |      0.3804213135      |        64560        |
| Sharpshooter  |        2        |               40000                |        0.8        |      0.3804213135      |        64560        |
| Machinist     |        2        |               40000                |       0.75        |      0.3653312178      |        63025        |
| Reaper        |        2        |               40000                |       0.75        |      0.3653312178      |        63025        |
| Bard          |       1.9       |               38000                |       0.75        |      0.3653312178      |      59873.75       |
| Deadeye       |       1.8       |               36000                |        0.7        |      0.3494877216      |        55341        |
 
---

## Additive vs Multiplicative Effects

Broadly, effects that increase damage are multiplicative while effects that increase attack power are multiplicative. When min-maxing, if possible you want to avoid using multiple additive effects when multiplicative effects are available, since additive effects don't scale together as well.

As an example, imagine a hypothetical Artillerist with 1000 attack power as a baseline. Consider level 3 of the following engravings: **Cursed Doll** (Atk Power +16%), **Mass Increase** (Atk Power + 18%), **Hit Master** (Damage +18%). Also, for the sake of apples-to-apples comparison, imagine that **Grudge** level 3 gives 18% damage (in reality it's 20%, but since Mass Increase and Hit Master are both 18% we're going to use this substitute). Then: 

 - With Cursed Doll, attack power is $1000(1 + 0.16) = 1160$
 - With Mass Increase, attack power is $1000(1 + 0.18) = 1180$
 - With Cursed Doll + Mass Increase, attack power is $1000(1 + 0.16 + 0.18) = 1340$
 - With Cursed Doll + Hit Master, attack power is $(1000(1 + 0.16)) \times 1.18 = 1368$ (2.1% better than the previous combination)
 - With Cursed Doll + Mass Increase + Hit Master (2 additive, one multiplicative), attack power is $(1000(1 + 0.16 + 0.18)) \times 1.18 = 1581$
 - With Cursed Doll + Hit Master + 18% Grudge (1 additive, 2 multiplicative), attack power is $(1000 * (1 + 0.16)) \times 1.18 \times 1.18 = 1615$ (2.2% better than the previous combination)

---

## Combat Engravings

~~Strikethrough~~ indicates the engraving is a budget or low-tier/suboptimal choice for that class. This is judged off rank on the class build list and educated guessing, please correct if you see an error.

### Damage

1. **All-Out Attack**: (+4/10/20%) Damage, (+5/10/15%) Holding and Casting Skill Speed)
    - Classes: Sorceress (Igniter, ~~Reflux~~)
2. **Ambush Master**:	(+5/12/25%) Damage for successful back attacks
    - Classes: Berzerker (Technique, ~~Mayhem~~), Striker, Soulfist (Robust Spirit), Scrapper, Wardancer, Glaivier (Control), Deadeye, Deathblade, Shadowhunter (Perfect Suppression)
3. **Barricade**: (+3/8/16%) Damage to foes while shielded
    - Classes: Gunlancer (Blue), Destroyer (Gravity Training), Artillerist (Budget), Arcanist (Empress's Grace)
4. **Grudge**: (+4/10/20%) Damage to Boss and above level monsters, Incoming Damage +20%
    - Classes: All DPS
5. **Hit Master**: (+3/8/16%) damage to attacks other than Front and Back Attack. Does not apply to Awakening skills.
    - Classes: Sharpshooter, Artillerist, Gunslinger, Shadowhunter (Demonic Impulse), Sorceress, Arcanist
6. **Master Brawler**: (+5/12/25%) Damage to Head Attack skills.
    - Classes: Gunlancer (Red), Destroyer
7. **Master's Tenacity**: (+3/8/16%) Outgoing damage when you are at or below 50% HP
    - Classes: Berzerker (Mayhem)
8. **Raid Captain**: Outgoing Damage (+10/22/45%) of basic Move Speed bonus percentage
    - Wording is a little misleading; effects such as Mayhem's +15% move speed bonus also count for Raid Captain.
    - Classes: Berzerker, Paladin (Judgment), Soulfist (Energy Overflow), Wardancer (First Intention), Glavier (Control), ~~Gunslinger~~, ~~Sharpshooter~~, ~~Shadowhunter~~, Arcanist (Order)
9. **Stabilized Status**: (+3/8/16%) damage when your HP is above 80%
    - Classes: Gunlancer (Blue), Paladin (~~Judgment~~)
10. **Super Charge**: Charge skills' charging speed (+8/20/40%). Damage (+4/10/20%).
    - Classes: Berzerker (Technique), Gunlancer (Red), Destroyer (Hammer), Deathblade

### Attack Power

1. **Cursed Doll**: +3/18/16% Attack power, -25% healing (natural recovery excluded)
    - Classes: All DPS
2. **Mass Increase**: (+4/10/18%) Attack power. Attack speed -10%
    - Classes: Berzerker (~~Mayhem~~), Striker (~~Esoteric Flurry~~), Soulfist (~~Robust Spirit~~), ~~Wardancer~~, Glavier (Pinnacle)
3. **Adrenaline**:  (+0.3/0.6/1%) Attack Power for 6s after using skills. Stacks up to 6x. (+5/10/15%) Crit Rate when max stacks reached.
    - Classes: ~~~Gunlancer~~~, Paladin (Judgment), Striker, Soulfist, Scrapper, Wardancer (Esoteric), Deadeye, Artillerist (Firepower), Gunslinger (Peacemaker), Deathblade, Shadowhunter, Bard (True Courage), Sorceress, Glavier (Control)

### Crit Damage

1. **Keen Blunt Weapon**: (+10/25/50%) Crit Damage, chance of -20% damage on all attacks
    - Testing indicates chance of damage reduction to be 10%. [https://lostark.fandom.com/wiki/Keen_Blunt_Weapon]
    - Expected damage drawback is therefore -2%.
    - Need 60% crit rate to be efficient [https://www.reddit.com/r/lostarkgame/comments/spt8zp/keen_blunt_weapon_efficiency_table/]
    - At level 3, increased damage as a function of crit rate $x$ is $f(x) = 0.98(1.5x + 1)$
    - Comparing $f(x)$ to baseline damage (e.g, KBW is how much additional damage?):  
    $g(x) = { 0.98(1.5x + 1) \over (1x + 1) }$
    - In this table, column headings are your crit rate and row headings are your pre-KBW crit rate (200% for basic
    characters with no other effects applied). You want to be in the blue-shaded area, otherwise a different engraving 
    offers a higher damage increase.
    ![Keen Blunt Efficiency from /u/ekdud](https://preview.redd.it/auxheckzl5h81.png?width=1738&format=png&auto=webp&s=5fd0391d31ef3bdae9b00c1fe08835324e68449d)
    - Classes: Berzerker, Gunlancer (Red), ~~Paladin (Judgment)~~, Destroyer (Hammer), Striker, Soulfist (Energy Overflow), ~~Scrapper~~, Wardancer, Glaivier, Deadeye, Sharpshooter, Artillerist, Gunslinger, ~~Deathblade~~, Shadowhunter, Bard (True Courage), Arcanist

### Crit Rate

1. **Adrenaline**:  (+0.3/0.6/1%) Attack Power for 6s after using skills. Stacks up to 6x. (+5/10/15%) Crit Rate when max stacks reached.
    - Classes: ~~Gunlancer~~, Paladin (Judgment), Striker, Soulfist, Scrapper, Wardancer (Esoteric), Glavier (Control), Deadeye, Artillerist (Swiftness-based Firepower Enhancement),  Gunslinger, Deathblade, Shadowhunter, Bard (~~True Courage~~), Sorceress, Arcanist
2. **Precise Dagger**: (+4/10/20%) Crit Rate. Crit Damage -12%
    - As a function of pre-Precise Dagger crit rate, this formula defines the expected damage increase (assuming basic crit damage of 200%) of
    a level 3 engraving. Here $x$ is a value between 0 and 1 (e.g., using $x = 0.27$ for a 27% sheet crit rate gives a 
    damage increase of roughly 11.3%):  
    $g(x) = {0.88(x + 0.2) + 1 \over (1x + 1)}$ 
    - Classes: Gunlancer (Red), Soulfist (Energy Overflow), Deadeye (Pistoleer), Shadowhunter (Perfect Suppression), Sorceress

### Attack Speed

1. **Spirit Absorption**: (+3/8/15%) Attack/Move Speed
    - Classes: Berzerker (Technique), Gunlancer, Paladin (Aura), Destroyer, Striker, Soulfist (Robust Spirit), Scrapper (Shock), Deadeye (Enhanced Weapon), Gunslinger (~~Peacemaker~~), Shadowhunter, Bard (True Courage, Spec-based Desperate Salvation)

### Support

1. **Expert**: (+6/14/24%) Shield and Healing effectiveness on all Party Members. If target's HP is 50% or lower, (+3/7/12%) effectiveness
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
2. **Heavy Armor**: (+20/50/100%) to All Defense. This additional defense is immune to defense reduction effects.
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
3. **Drops of Ether**: (Cooldown: 60/30/10s) Attack have a chance to create an Ether within 8 meters.
    - Classes: Paladin (Aura), Bard (Desperate Salvation)
4. **Max MP Increase**: (+5/15/30%) Max MP
    - Classes: Bard (Swiftness-based Desperate Salvation)
5. **Vital Point Hit**: Stagger attack effectiveness (+6/18/36%).
    - Classes: Paladin (Aura), Bard (Desperate Salvation)

### Other

1. **Awakening**: (-10/25/50%) Awakening Skill Cooldown.  (+1/2/3) maximum uses.
    - Classes: Berzerker (Technique), Gunlancer (Blue), Paladin, Soulfist (Robust Spirit), Glavier (Pinnacle), Bard (Desperate Salvation), Arcanist (Order)
2. **Preemptive Strike**: (+30/80/160%) damage and guaranteed crit when attacking Challenge or lower monsters with full HP. Used on Chaos Dungeon builds to speed things up.
    - Classes: Any.
3. **Sight Focus**: Gain (+8/16/28%) damage for 6s when "!!!!!" is entered into normal chat. Does not apply to basic attacks, and only half as effective on Awakening skills. Cooldown 30s.
    - Usable by bursty DPS classes, but kind of a meme engraving since better choices are typically available.
  
  ---

### Examples Used to Calculate the Stat Rates:

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

#### Berzerker

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

### Random stuff

1. A series of reddit posts about stat calculations, no idea if they're accurate:
    - [https://www.reddit.com/r/lostarkgame/comments/swkw21/how_some_stats_are_calculated_attack_power_damage/]
    - [https://www.reddit.com/r/lostarkgame/comments/vaq858/how_some_stats_are_calculated_pt_ii/]
    - [https://www.reddit.com/r/lostarkgame/comments/w26xpq/how_some_stats_are_calculated_pt_iii_item_level/]
2. Ability stone calculators:
    - [http://lostarktoolkit.com]
    - [https://lostark.meta-game.gg/ability-stone-calculator]
    - [https://lostarkfoundry.com/ability-stone-calc/]