# Codex Micro secret game: how to unlock the hidden Snake, Asteroids and Brick Breaker on OpenAI's keyboard

**Circle the joystick about two full turns in under six seconds and the Codex
Micro opens a hidden game.** There are three of them — Snake, Asteroids and
Brick Breaker — and they are built out of your own recent chat messages. OpenAI
has never documented them.

This page is the complete reproduction guide: the exact gesture, the exact
tolerances the app measures it against, which hardware can trigger it, and how
to tell whether it is working before it fires.

- **Device:** Work Louder × OpenAI Codex Micro ($230 macropad, launched
  2026-07-15)
- **Where the games live:** the ChatGPT desktop app, not the keyboard's firmware
- **Gesture:** hold the analog stick out and circle it steadily, ~1.9 turns
  inside 6 seconds
- **Result:** one of `snake`, `asteroids` or `brick-breaker`, chosen at random
- **Officially documented?** No. It appears nowhere in
  [OpenAI's Codex Micro documentation](https://learn.chatgpt.com/docs/features/codex-micro).

---

## Quick answer: how to play the Codex Micro secret game

1. Open the **ChatGPT desktop app** with your Codex Micro connected and detected.
   The games are drawn by the app, so the app has to be running and in focus.
2. Push the **analog stick** at least **a fifth of the way out** from centre and
   keep it there. Anything shallower is ignored completely — the app does not
   count it as part of the gesture.
3. **Circle it in one direction, steadily.** Do not pause, and do not reverse.
4. Keep circling for **about two full revolutions** — the exact threshold is
   **1.9 turns** — and finish **within six seconds** of starting.
5. Watch the joystick HUD. Once you are a fraction of a turn in, it starts
   showing progress and the words **"Keep circling"** with a percentage. That is
   your confirmation the app is counting.
6. At 100% the composer opens one of the three games at random.

In **Asteroids**, **Agent key 1** is your fire button.

---

## The exact parameters the app checks

The keyboard itself is not clever here. It reports only two normalised numbers —
joystick `angle` and `distance`, each 0 to 1 — and every decision below is made
in the desktop app.

| What it measures | Value | What it means when you are holding the stick |
|---|---|---|
| Minimum displacement | `0.2` | Below a fifth of full travel the sample is discarded entirely. A gentle circle near centre registers nothing at all. |
| Activation threshold | `1.9` turns | Accumulated rotation needed to fire. Just under two full revolutions. |
| Capture threshold | `0.04` turns | The point at which the HUD starts showing you progress. |
| Maximum sample gap | `1000 ms` | Pause longer than a second and the accumulation resets to zero. |
| Total time budget | `6000 ms` | The whole gesture must complete inside six seconds. |
| Reversal tolerance | `0.02` turns | Change direction by more than a rounding error and it resets. |

Progress is simply `accumulated ÷ 1.9`, and that is the number the HUD shows.

**In plain terms:** one smooth, committed, wide circle — roughly a full turn
every three seconds or faster — with no hesitation and no wobble backwards.
Most failed attempts are either too shallow (under the `0.2` floor) or too
hesitant (a pause over one second, resetting the count).

---

## Which hardware actually works

This is the part that catches people out, and it is worth being precise about
because the two keyboards look almost identical.

The ChatGPT desktop app enumerates Work Louder devices by **USB product ID**:

| Product ID | Device type in the app | Notes |
|---|---|---|
| `33431` (`0x8297`) | `creator_micro_v2` | Creator Micro 2 |
| `33432` (`0x8298`) | `creator_micro_v2` | Creator Micro 2 |
| **`33632` (`0x8360`)** | **`project_2077`** | **The Codex Micro** |

`project_2077` is the Codex Micro's internal codename. The app's device
discovery call filters to that type alone, and a device it never discovers never
gets its joystick subscribed — so the gesture detector is never fed anything.

**A Codex Micro will trigger the games.** For the **Creator Micro 2**, the
picture is genuinely unresolved and you should not trust a confident answer
either way:

- Read straight from the shipped app code, the device-type filter admits only
  `project_2077`, which would exclude a Creator Micro 2.
- But OpenAI's own documentation states plainly that "the ChatGPT desktop app
  also supports Creator Micro 2", and at least one third-party project reports
  its Codex Micro / Creator Micro 2-compatible hardware enumerating as
  `303a:8360` — the *filtered* ID.

The likeliest explanation is that current Creator Micro 2 units ship the same
product ID, but that is an inference from one ambiguous source. **If you own a
Creator Micro 2 and try this, the result is genuinely new information.** Nobody
has published it.

---

## What the three games are made of

The interesting part is not that the games exist. It is what they are built
from: **your own recent assistant messages become the game objects** — the
asteroids you shoot, the bricks you break, and the food the snake eats. Every
session's level is different because your conversation is different.

The three titles, as named internally:

- `snake`
- `asteroids`
- `brick-breaker`

You do not get to pick. One is chosen at random each time the gesture fires.

---

## Is it firmware or software?

**Software.** All of it is in the ChatGPT desktop app's webview, in a mini-games
module. The keyboard only ever sends `{angle, distance}`. Nothing is stored on
the device, no firmware modification is involved, and flashing custom firmware
onto a clone board will not give you the games — the games come from the app,
and the app decides whether to listen to your board at all.

Two consequences worth knowing:

- **An app update can remove it silently.** It is undocumented, so nothing
  obliges OpenAI to keep it.
- **It is not new.** The same detector, with the same constants, is present in
  Codex Micro-era desktop builds going back months. It simply had not been found.

---

## Troubleshooting: the secret game is not triggering

| Symptom | Most likely cause |
|---|---|
| Nothing happens, no HUD at all | You are circling too close to centre. Push past a fifth of full travel and hold it there. |
| HUD appears then vanishes | You paused for more than a second, or wobbled backwards past the reversal tolerance. Keep it continuous. |
| HUD climbs but never completes | Too slow. You need ~1.9 turns inside six seconds — about one turn every three seconds, minimum. |
| Works nowhere at all | Check the app has actually detected the Micro. If the device settings panel is not available, the app has not discovered your board. |
| Creator Micro 2 does nothing | See the hardware section above — this is the unresolved case. |
| Long-pressing the dial opens settings instead | That is the documented dial behaviour, and unrelated. The games are on the **analog stick**, not the dial. |

---

## Frequently asked questions

### What is the Codex Micro secret game?

Three hidden retro games — Snake, Asteroids and Brick Breaker — built into the
ChatGPT desktop app and unlocked by circling the Codex Micro's analog stick. The
in-app string for the gesture is literally "Secret game".

### How do you unlock the hidden games on the Codex Micro?

Hold the analog stick at least a fifth of the way out and circle it in one
direction for about 1.9 full turns within six seconds, without pausing longer
than a second or reversing.

### Is this the same as the OpenAI Codex easter egg from the Super Bowl ad?

**No, and they are constantly confused.** OpenAI's Super Bowl "You can just
build things" ad contained a separate promotional easter egg — a clue leading to
1,000 Codex merch kits. That was a marketing campaign. This is an undocumented
feature inside the desktop app, discovered by reverse engineering, with no prize
attached.

### Does the joystick do anything else?

Yes, and it is documented. OpenAI's own guide describes the analog stick as four
directional actions — pushed far enough from centre it resolves to up, right,
down or left, defaulting to Plan mode, forward, sidebar and back. The circling
gesture is a separate, undocumented behaviour layered on the same input.

### Will this work on a Codex Micro clone?

Almost certainly not, unless the clone presents USB product ID `0x8360`. Several
open-source projects now emulate the Micro's identity, so it is not impossible —
but the app's private device integration is reserved for supported Micro
devices, and clone authors have said as much themselves.
