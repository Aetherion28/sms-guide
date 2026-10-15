---
layout: default 
title: Sirena 5
permalink: /shines/sirena/episode5/
parent: Sirena Beach
grand_parent: Shines
---

# Sirena 5  
*( guide by **Zeldocto** )*  
Sirena 5 is another notorious level, since you only have a 34.3% chance of getting perfect RNG.  

1. [Explanation](/sms-guide/shines/sirena/episode5/#video-explanation)
2. [Entry](/sms-guide/shines/sirena/episode5/#entering-the-fight)
3. [The Fight](/sms-guide/shines/sirena/episode5/#the-fight)
4. [Cycle Skips](/sms-guide/shines/sirena/episode5/#cycle-skips)

#### Video Explanation
{% include yt.html id="0_WZhr2ByyQ" %}  
*( video by **Samura1Man** )*  

Perfect cycles are: Fruit🍍, Not Fruit❌, Fruit🍍, Not Fruit❌, Fruit🍍. (if not going for [Cycle Skips](#cycle-skips))  

<details markdown="block">
  <summary markdown="span">
    Slot Statistics - Click for Details
  </summary>
{: .text-gamma}
### Slot Statistics  

**# of extras or "n"** | **exactly n extras** | **n extras or fewer** | **more than n extras**
0 | 34.3% | 34.3% | 65.7%
1 | 30.87% | 65.17% | 34.83%
2 | 18.522% | 83.692% | 16.308%
3 | 9.261% | 92.953% | 7.047%
4 | 4.16745% | 97.12045% | 2.87955%
5 | 1.750329% | 98.870779% | 1.129221%
6 | 0.7001316% | 99.5709106% | 0.4290894%
7 | 0.27005076% | 99.84096136% | 0.15903864%
8 | 0.10126904% | 99.9422304% | 0.05776961%
9 | 0.03713198% | 99.97936237% | 0.02063763%
10 | 0.01336751% | 99.99272989% | 0.00727011%
11 | 0.00473939% | 99.99746928% | 0.00253072%
12 | 0.00165879% | 99.99912806% | 0.00087194%
13 | 0.0005742% | 99.99970226% | 0.00029774%
14 | 0.00019687% | 99.99989913% | 0.00010087%

Chance of getting a fruit cycle is 70% until going down to 3 health or below.  

### Slot Chances Based on Health
- Row = *What was last spawned*  
- Column = *What will be spawned next*

Key takeaway is fruit cycle is 70% until going to 3 health or below.

<img src="/sms-guide/assets/shines/sirena/episode5/slothealthstats.png">  
</details>  

#### Entering the Fight  
{% include yt.html id="xURSkskvXWk" %}  
*( video by **FoundYourGun** )*  

<details markdown="block">
  <summary markdown="span">
    Instant Elevator Trigger - Click for Details
  </summary>
{: .text-gamma}
There is a small area you are able to get a ground pound that instantly triggers the elevator as shown in the video.  
<img src="/sms-guide/assets/shines/sirena/episode5/kbgptrigger.png">  
*( screenshot by **inkstar** )*  
</details>  

#### The Fight  
{% include yt.html id="Db7NxthMMOY" %}  
*( video by **FoundYourGun** )*  

The second the fight starts and you gain control of Mario, you notice FoundYourGun do a backflip dive into the center of the arena. This is a trick called **laugh skip** and saves ~2 seconds. This also makes the hitboxes for the purple buttons much larger (for some reason).  

- Once you take control of Mario, backflip dive into the center of the arena to activate laugh skip.
- You can optionally ground pound the purple squares to stop the rotation of the roulette wheels to make grabbing the fruit easier.
- Spray King Boo the second he comes out of the ground.
  1. If you get a Fruit🍍 cycle for the first roll, this is optimal.
  2. If you get a Not Fruit❌ for the first roll, *or when you should optimally get a Fruit🍍 cycle*, this is an extra **NON-MANDATORY** cycle and you can cancel it the moment you notice the slot not stopping on fruit.
  3. If you get a Fruit🍍 cycle, then a Not Fruit❌ cycle after, this is an extra **MANDATORY** cycle, and you have to wait until the enemies spawn before cancelling the cycle.
- As stated before, optimally the cycles are: Fruit🍍, Not Fruit❌, Fruit🍍, Not Fruit❌, Fruit🍍. (if not going for [Cycle Skips](#cycle-skips))
- Once you get a Fruit🍍 cycle, grab a pepper and throw it into King Boo's tongue.
- After he reacts to the pepper, throw a normal fruit at King Boo.
- Repeat this 3 times.

*Important tips:*  
- Aim to throw the pepper at his tongue.  
- Each fruit has a different throw arc. Learn them.  
- You can hover into a durian if its placement is convenient for a quick fruit launch after throwing a pepper.

#### Cycle Skips
<details markdown="block">
  <summary markdown="span">
    Explanation - Click for Details
  </summary>
{: .text-gamma}
An RNG strat that loses about 2 seconds each time you go for it, but has the potential to save around 12 seconds each time you get it. Getting a cycle skip is a 1/64 chance, is pure luck, and you need to do it twice to save up to <u>a total of 20 seconds</u> (getting it twice is 1/4096 or a 0.0244% chance). This doesn't include the odds that a perfect King Boo needs a Fruit🍍 cycle first, which reduces the odds even further to **1/5851, or around 0.0171%**! Samura1Man was lucky enough to get it in an IL grind around [7th try](https://www.youtube.com/watch?v=DIcjtHJf4AI), and AverageTrey grinded for it for [18 months](https://www.youtube.com/watch?v=JFDljTWMRvE) before he got it once. 

To go for it, you simply need to run under King Boo right when he starts to spin his slots after being sprayed on a Not Fruit❌ cycle. When you run under King Boo while his slots are spinning, you will get a roll once King Boo reappears. On its own this wouldn't be useful, but whenever King Boo reappears, his slots are set to random positions **regardless of the normal cycle rules**. So if this is done while the slots are spinning, you will get a cycle based on those random positions, with some possible leftover rotation if the slots don't have time to stop before King Boo reappears.
</details>  

<details markdown="block">
  <summary markdown="span">
    How it works in the game's code - Click for Details
  </summary>
{: .text-gamma}
*( from the Super Mario Sunshine decompilation, `Enemy/bosstelesa.cpp` )*

**Cancelling a cycle is a plain distance check.** King Boo carries an invisible collision actor (`TBossTelesaKillSmallEnemy`). Every frame it checks the distance from Mario to King Boo's position **ignoring height**. If it is under **300 units**, it calls `forceHide()`. There is no RNG and no timing window on the cancel itself: being within 300 units of King Boo's XZ position is enough, so it is fully consistent.

`forceHide()` does nothing while King Boo is dying, already hiding (anim 4) or already appearing (anim 0). Otherwise it kills every spat-out item at once (`forceAllItemKill`, which also detaches anything Mario is holding), plays the escape/disappear sound, and jumps straight to his Hide state. From there he goes Hide → HideWait → Appear. HideWait only ends after **400 frames**, and only once Mario is **no longer** within 300 units, so standing under him keeps him down.

**Why cancelling early doesn't count as a cycle.** The items are only created when King Boo reaches his spit state (`generateSlotItem`). Cancel before that and nothing was ever spawned, so nothing is tracked.

**How the slot decides a normal cycle** (`TTelesaSlot::forceStopSlot`, called once at the end of the slot-start animation on the middle drum):
- With probability `mSLSlotFirstHitCollectRate` (**10%**, raised to **90%** at 1 HP) the result is rigged: Fruit🍍, or coins instead if Mario has 3 HP or less.
- Otherwise the result is whatever symbol the middle drum is already heading for, which depends on the spin speeds rolled in `rouletteStart`.
- If that result equals the **previous** cycle's result it becomes the mixed-enemies result. This is the "no back-to-back" rule, and it applies to every symbol.
- A coin result becomes the single-enemy result once the 3-coin-cycle budget is used up, or the mixed-enemies result if Mario has 6 HP or more.

The four results are: Fruit🍍, coins, a single enemy type (Strollin' Stus, or Smolderin' Stus at 2 HP or less) and a mix of enemy types.

**Why a cycle skip is 1/64.** When King Boo reappears, `randomReset()` snaps each of the three drums to one of **8 positions** (45° steps). The 8 positions hold the four results twice each, so each symbol is on 2 of the 8. The slot-started flag (`unk18C`) set when the spin began is never cleared by `forceHide()`, so the next time he is sprayed the game sees "slot started and no drum is rolling" and reads the result straight from those random positions, skipping `forceStopSlot` and its rules entirely. All three drums landing on fruit is (2/8)³ = **1/64**; all three on the same symbol of any kind is 1/16; the other 60/64 of the time the drums don't match (result −1), which spawns a **double** batch of bubbles (the only time bubbles come from the slot). Drums that still had spin speed keep turning from their random position until they stop, which is the "leftover rotation".
</details>  
