# By the Light of the Moon
**An Interactive Narrative built in Twine / Harlowe**

---

## 🕹️ [Play it here!](https://desinoelle.github.io/by-the-light-of-the-moon/)

---

## Overview

*By the Light of the Moon* is a 1950s werewolf thriller built in Twine (Harlowe format). Cindy Marlowe is a junior cheerleader on her first real date at the Moonlight Springs drive-in. When Danny Calloway disappears into the woods and the sounds that follow are not the sounds a person makes, she has to decide what kind of night this is going to be.

The game has **94 passages**, **two major branches**, and **five possible endings**, including a secret ending that only unlocks under specific conditions.

---

## How to Play

Open the `.html` file in a browser and click links to make choices. A few things worth knowing:

- Some passages are **timed**. If you don't choose in time, the story chooses for you.
- What you **notice in Act I** affects what options are available later. Pay attention.
- Bad endings include a "Try again" link back to the decision that led there.

---

## Structure

**Act I** plays mostly linearly. You arrive at the drive-in, choose where to sit, and have the option to explore the lot before the film's climax forces the story's major decision. Exploration is optional but meaningful, visiting the bulletin board, the nervous couple, the tree line, and the projection booth sets variables that open options later.

At the end of Act I, Danny walks into the woods:
- **Following him** -> Branch 1 (Compassion Path) - quieter, more intimate
- **Staying or fleeing** -> Branch 2 (Survival Path) - faster, more frantic, with harder timed passages and less margin for error

---

## Endings

### Good Endings
| Ending | Path | Condition |
|---|---|---|
| Sunrise Ending | Compassion Path | Stay close long enough through the night |
| Escape Ending | Both Paths | Get out alive |
| Mercy Ending | Both Paths | Requires bulletin board knowledge from Act I |

### Secret Ending
**The Curse** *(Compassion Path)*: Unlocked only if the channel fails to hold and Cindy is bitten. She realizes what happened, quietly, in the dark, just before dawn. The story ends where it began, with the roles reversed.

---

## Walkthrough

<details>
<summary>Click to reveal spoilers</summary>

### Optimal Act I (Both Paths)
1. Sit close (sets `$connectionLevel +1`)
2. Visit: the bulletin board, the nervous couple, the treeline, and the projection booth
3. At Moon Rising, ask him about it (sets `$connectionLevel +1`)
4. At the film climax, follow him for Branch 1 or stay/flee for Branch 2

### Branch 1 - Sunrise Ending
1. Choose **Hide** (lets you observe the moon's effect on him)
2. At The Decision, choose to **save him**
3. Take the Containment Arc - use the chain and/or the moon maneuver
4. Hold through the night -> **Sunrise Ending**

### Branch 1 - Secret Ending
1. Choose **Hide** (sets `$observedFighting = true`)
2. Take the Containment Arc — use the **root channel**
3. The channel fails; Cindy is bitten (sets `$bitten = true`)
4. Hold through the night → secret link appears at dawn

### Branch 2 - Projection Booth Escape
1. Must have noticed the booth in Act I (`$noticedBooth = true`)
2. Search the lot - get the chain from the fence, bat and flashlight from the cars
3. Run to the booth, brace the door with the chain, find the flare gun
4. Hold until dawn -> **Escape Ending** or **Mercy Ending**

### Branch 2 - Mercy Ending
1. Must have visited the bulletin board (`$sawMissingPersons = true`, `$callowayNameNoticed = true`)
2. Survive any route to the ending gate
3. At the ending gate, choose to go to **414 Sycamore**

</details>

---

## Design Notes

**Timed passages:** Harlowe's `(after:)` macro reveals links after a delay and auto-redirects to bad endings if no choice is made. This mechanic is concentrated in Branch 2. Act I has none - that pacing is intentional.

**Variables:** 18 boolean flags set by exploration and item pickup. They don't change the prose dramatically, but they open gate options. The goal was to make Act I feel like it mattered without feeling like a checklist.

**Prose style:** Short sentences, present tense, minimal interiority, urgent and close to the character without getting in the way.

**Theme: Metamorphosis:** The game's central theme is transformation and what it costs. Danny's curse is the literal version, but every path puts Cindy through her own change. In the secret ending, the transformation becomes literal for her too, mirroring Danny's and closing the loop. *The monster is never just the monster.*

---

## Built With

- [Twine 2](https://twinery.org) - Harlowe format
- [Harlowe 3 Manual](https://twine2.neocities.org/harlowe) - `(set:)`, `(if:)`, `(after:)`, `(go-to:)` macros
- [Twine Cookbook](https://twinery.org/cookbook) - timed passage patterns and CSS/JS implementation
- [Google Fonts](https://fonts.google.com) - Special Elite (body), Playfair Display (titles)

---

*Inspired in part by the tension between monster and person in Michael Jackson's* Thriller *(1983).*
