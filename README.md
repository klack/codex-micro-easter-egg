# Codex Micro secret game: how to unlock the hidden Snake, Asteroids and Brick Breaker on OpenAI's keyboard

**Circle the joystick about two full turns in under six seconds and the Codex
Micro opens a hidden game.** There are three of them — Snake, Asteroids and
Brick Breaker — and they are built out of your own recent chat messages. OpenAI
has never documented them.

This page is a hands-on guide for people who own the hardware: how to perform
the gesture, how to tell it is working before it fires, and why it sometimes
does not.

- **Device:** [Work Louder × OpenAI Codex Micro](https://openai.com/supply/co-lab/work-louder/)
  ($230 macropad, launched 2026-07-15 — [product page](https://worklouder.cc/codex-micro))
- **Where to do it:** in a conversation, with the message box on screen
- **Gesture:** hold the analog stick out and circle it steadily, about two turns
  inside six seconds
- **Result:** Snake, Asteroids or Brick Breaker, chosen at random
- **Officially documented?** No. It appears nowhere in
  [OpenAI's Codex Micro documentation](https://learn.chatgpt.com/docs/features/codex-micro).

> **They told us in the [launch video](https://www.youtube.com/watch?v=m8uUUUsMD3Y).**
> The analog stick, they said, is "a great fidget toy while you're waiting for
> Codex to complete a task". That was the hint.

---

## Quick answer: how to play the Codex Micro secret game

1. Open the **ChatGPT desktop app** with your Codex Micro connected and
   detected, and go to a **conversation** — anywhere the message box you
   normally type into is on screen.
2. Push the **analog stick** at least **a fifth of the way out** from centre and
   keep it there. A shallow circle near centre does not count at all.
3. **Circle it in one direction, steadily.** Do not pause, and do not reverse.
4. Keep circling for **about two full revolutions**, and finish **within six
   seconds** of starting.
5. Watch the joystick HUD. Once you are a fraction of a turn in, it starts
   showing progress and the words **"Keep circling"** with a percentage. That is
   your confirmation the app is counting.
6. At 100% the message box is replaced by one of the three games, chosen at
   random.

**In plain terms:** one smooth, committed, wide circle — roughly a full turn
every three seconds or faster — with no hesitation and no wobble backwards. Most
failed attempts are either too shallow or too hesitant.

The Micro also has to be **actively connected**, not merely paired. If the app
is not currently talking to the keyboard, the gesture goes nowhere.

It is undocumented, so nothing obliges OpenAI to keep it. An app update could
remove it without a word.

---

## What the keys do while a game is running

This is the part nobody tells you, and it is the difference between playing the
game and being stuck in it.

**Agent key 1 is the only key any of the three games listens to** — and it does
two completely different jobs depending on which game you got:

| Game | Agent key 1 |
|---|---|
| **Asteroids** | **Fire.** |
| **Snake** | **Quits the game.** |
| **Brick Breaker** | **Quits the game.** |

You steer with the **analog stick** — the same stick you just circled.

Two details worth knowing before you start:

- **Asteroids tells you which key fires.** When it opens, the app lights Agent
  key 1 in the same blue it uses for a thinking task. That light is not a
  session status; it is the game advertising your trigger.
- **Agent keys 2 to 6 do nothing at all** while a game is up. They are not
  bound to anything, and pressing them will not get you out.

**The dial and the command keys are not taken over.** They keep doing their
normal app work for the whole time a game is running, so a stray press of
Approve or Send still does what it always does. Treat the keyboard as live.

And note the asymmetry: because Agent key 1 fires in Asteroids rather than
quitting, **Asteroids has no exit key on the Micro.** Snake and Brick Breaker you
can back out of from the keyboard; Asteroids you cannot.

**If you are stuck in any of them, press `Escape` on your actual keyboard.**
That is what the quit key is doing underneath, and it works in all three.

---

## Which hardware actually works

**The Codex Micro. The Creator Micro 2 may also be supported.**

The Creator Micro 2 is the board the Codex Micro was built on, and the ChatGPT
desktop app supports it too, so it may well open the games as well.

---

## What the three games are made of

The interesting part is not that the games exist. It is what they are built
from: **your own recent assistant messages become the game objects** — the
asteroids you shoot, the bricks you break, and the food the snake eats. Every
session's level is different because your conversation is different.

You do not get to pick which one you get. It is chosen at random each time the
gesture fires.

---

## Troubleshooting: the secret game is not triggering

| Symptom | Most likely cause |
|---|---|
| Nothing happens, no HUD at all | You are circling too close to centre. Push past a fifth of full travel and hold it there. |
| HUD appears then vanishes | You paused for roughly a second or more, or wobbled backwards. Keep it continuous and one-directional. |
| HUD climbs but never completes | Too slow. You need about two turns inside six seconds — roughly one turn every three seconds, minimum. |
| Nothing happens on the settings screen | Expected. Go to a conversation, where the message box is on screen. |
| Works nowhere at all | Check the app has actually detected the Micro. Paired is not the same as connected — if the device settings panel is not available, the app is not currently talking to your board. |
| A game opened and now I cannot get out | Press `Escape` on your keyboard. From the Micro, Agent key 1 quits Snake and Brick Breaker — but not Asteroids, where it fires instead. |
| Agent keys 2–6 do nothing during a game | Correct, and expected. Only Agent key 1 is bound while a game is up. |
| Creator Micro 2 does nothing | See the hardware section above — it may be supported, but the Codex Micro is the known case. |
| Long-pressing the dial opens settings instead | That is the documented dial behaviour, and unrelated. The games are on the **analog stick**, not the dial. |

---

## Frequently asked questions

### What is the Codex Micro secret game?

Three hidden retro games — Snake, Asteroids and Brick Breaker — built into the
ChatGPT desktop app and unlocked by circling the Codex Micro's analog stick.

### How do you unlock the hidden games on the Codex Micro?

Hold the analog stick at least a fifth of the way out and circle it in one
direction for about two full turns within six seconds, without pausing or
reversing, while you are in a conversation.

### Do I need to be on the Codex Micro settings page?

No — and it will not work there. You need to be somewhere the message box is on
screen, because that is what the game replaces.

### Is this the same as the OpenAI Codex easter egg from the Super Bowl ad?

**No, and they are constantly confused.** OpenAI's Super Bowl "You can just
build things" ad contained a separate promotional easter egg — a clue leading to
1,000 Codex merch kits. That was a marketing campaign. This is an undocumented
feature inside the desktop app, with no prize attached.

### Does the joystick do anything else?

Yes, and it is documented. OpenAI's own guide describes the analog stick as four
directional actions — pushed far enough from centre it resolves to up, right,
down or left, defaulting to Plan mode, forward, sidebar and back. The circling
gesture is a separate, undocumented behaviour layered on the same input.

---

## Timeline

| Date (UTC) | Commit | What happened |
|---|---|---|
| **2026-07-15** | — | The Codex Micro goes on sale. |
| **2026-07-17** | *(private working repo)* | Hit by accident. Something kept taking over the display while I was updating a [Space Invaders port for Starbound](https://steamcommunity.com/sharedfiles/filedetails/?id=3728262023), so I pinned down what set it off — the rotation building up, the "Keep circling" HUD — and the games were observed. |
| **2026-07-26 09:47** | [`039e11e`](https://github.com/klack/codex-micro-easter-egg/commit/039e11e1f6) → [`fd6ec20`](https://github.com/klack/codex-micro-easter-egg/commit/fd6ec2039d) | The instructions go up here, in public. |
| **2026-07-28 10:06** | — | [Tibor Blaho posts his Codex Micro first impressions](https://www.linkedin.com/posts/tiborblaho_it-took-a-while-but-my-codex-micro-silent-activity-7487810678922264576-AMWW) and ends with: *"Fun fact - if you keep circling the analog stick, it starts one of the built-in minigames in the ChatGPT desktop app."* Found independently. |
| **2026-07-29 17:00** | [`241b2a5`](https://github.com/klack/codex-micro-easter-egg/commit/241b2a53c3) | Taken back down — "Archive Codex Micro Easter Egg instructions". |
| **2026-08-27 06:16** | — | [RuntimeWire publishes](https://runtimewire.com/article/openai-hid-asteroids-snake-and-brick-breaker-inside-the-codex-micro), independently, and lands on the same distinctive figure. |
| **2026-08-27 19:13** | [`e5ed97c`](https://github.com/klack/codex-micro-easter-egg/commit/e5ed97cd2b) | Restored — "as this easter egg has now been found by the public". |

Plenty of people own this keyboard. Somebody may well have been idly
circling that stick since launch and never mentioned it to anyone. The table is
only what happens to be written down.

**Corrections are welcome, and credited.**
