# Design Notes

> Status: exploratory. These are the design variants considered for the
> prototype — not a settled spec.

## Concept

A turn-based post-apocalyptic strategy-RPG. The protagonist does not save the
wasteland himself — he makes the wasteland able to save itself. He scavenges,
clears, protects and rebuilds; settlements supply him in return. Without
settlements he is not weak, he is **alone**, and that is the difference the
whole game is built on.

## The fork that decides everything

Ask: **what does the player see in the last 20 minutes?**

- **Variant A — RPG with a wasteland.** Last minutes: one man walking to where
  it all started. The network is background, the protagonist is foreground.
- **Variant B — Strategy with a hero.** Last minutes: a map, icons, panels,
  decisions, the hero reduced to a figure with bonuses.

Both are viable, they are **different games**, and the first line of any real
spec must pick one.

**Preferred:** A, with the settlement network as the strategic layer in between.

## Genre

Turn-based strategy-RPG — closer to Heroes of Might & Magic than to an RPG with
strategy bolted on. References worth studying for dependency mechanics:
State of Decay, Kenshi, Battle Brothers, This War of Mine, Frostpunk.

## Core principle

A dependency is only good if it **generates decisions instead of waiting**.
Being forced to choose what to lose is a game; being forced to idle is not.

So the hero is never made weak. He is made **one**. He is a force multiplier,
not a force.

## The late-game problem

*"He can't sit at a desk and become a bureaucrat."* Correct — so the endgame
must offer something other than a desk. Three models:

1. **Exception handler** (preferred). The system handles the routine: production,
   patrols, administration. The hero handles only what one person can do —
   reach places a squad cannot, talk to those who speak only to him, make a call
   that costs lives. Late game is not more actions, it is fewer and heavier ones.
2. **The hero becomes the state** (genre shift). Mount & Blade / Bannerlord:
   the hero turns into a ruler and the RPG layer ends. Honest, but you lose the
   attachment the character was carrying.
3. **Legacy.** The win condition is not his power but the wasteland surviving
   without him. The finale is succession, not ruling.

**Preferred:** 1, resolved as 3. He never sits down — the game ends before he
could. "The desk" belongs in the epilogue, where he is no longer needed, and
that is the victory.

## Dependency mechanisms

- **Logistics** — ammo, food, meds, fuel come from settlements; the backpack is
  small. He doesn't fail, he runs out.
- **Attention** — he is physically in one place; three threats mean two grow.
- **Holding** — he can destroy a raider camp alone, but not hold the place. That
  takes settlers, who take resources, who take territory.
- **Expertise** — engineer, medic, scout. He cannot be all of them.
- **Legitimacy** — uniting the wasteland is trust, not conquest. A second
  resource beside combat power.

## Key asymmetry

The dependency is mutual, or the game reads as charity: settlements cannot act
without someone who walks, risks and decides; the hero produces nothing without
settlements. He is neither nanny nor god — he is the intermediary.

## Three acts

1. **Survival** — alone, wasteland, raiders. (Already the current prototype.)
2. **Network** — settlements grow, delegation appears, threats grow faster.
   He is pulled in every direction. The most interesting part.
3. **Scale** — the enemy is no longer a raider band but something a lone man
   cannot fight. The network wins it, but he holds the key: one last trip,
   alone, where it all began.

## Loop

Scout → clear → **hold** → supplied → harder region. The game lives between
*clear* and *hold*.

## What not to do

- Don't build "our Fallout". Setting is secondary; mechanics are the point.
- Don't make settlement building a mini-game detached from the map (Fallout 4's
  mistake). Settlements must change what is possible on the map, and vice versa.
- Don't allow a solo regional victory "by skill". One camp, yes. One region, no.
- Don't build both layers at once — operational and tactical combat together is
  too much to learn at the same time.

## Roadmap

MVP is steps 1–5. Each step answers one question.

1. **Hero and day** — one controllable unit, turn = day, fog of war, movement.
   No combat. *Is exploring interesting?*
2. **Threat and time** — one raider camp that grows if ignored; only the hero
   can clear it. *Is triage interesting?*
3. **Settlement and scarcity** — one settlement, resource tick, needs.
   *Is losing interesting?*
4. **Close the loop** — the hero eats from the settlement; the settlement loses
   people without the hero. *Is the cycle playable?*
5. **Two threats at once** — the thesis test. *Does the player feel they must
   sacrifice something?*
6. **Recruitment** — squads and specialists from settlements. *Is the hero still
   needed as a leader?*
7. **Tactical combat** — after auto-resolve, never before.
8. **Unification** — trust, routes, mutual defence, endgame.

## Success test

One question for any playtest: **did the player ever have to choose what to
sacrifice?** If not, the dependencies are still decorative.
