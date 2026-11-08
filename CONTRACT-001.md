# Construction Contract 001 — "The Broken Bridge"

**Status:** DRAFT for council review · not yet FIAT approved
**Drafted by:** Vero, record keeper · 2026-11-07
**Covers:** the first playable build of the O'Clan game (Proposal 001)
**Approval needed:** Mago and Teso review → Captain's 4 decision cards → Captain's construction FIAT

> **In one sentence:** in 8 weeks (about 96 hours), build one small turn-based game where Captain and three AI teammates must share secrets to fix a broken bridge, with every move checked by Momo and every dollar capped.

---

## 1. What we are building

| | |
|---|---|
| **Deliverable** | One playable session of "The Broken Bridge" that Captain can finish in about 15–20 minutes |
| **Pass mark** | Captain plays it and finds it fun to play with the O'Clan |
| **Runs on** | Captain's own computer. $0 hosting |
| **Time box** | 8 weeks at about 12 hours a week (~96 hours). Review at week 8; the council may vote HOLD if no fun session exists |

### In scope (first build only)

- A 10×10 village grid, turn-based, 7 in-world days, 3 actions per character per day
- 4 characters: Captain (human), Mago, Vero, Teso (AI)
- 6 actions: move, look, gather, give, build, say
- Momo Core: a plain-code referee that checks every action
- Save, recover and replay
- A simple map picture redrawn after each turn
- The budget controller (section 6)

### Out of scope (needs a new FIAT to add)

Shaman dolls and villager growth · other NPCs · combat · economy and trading · more clans or villages · live animated graphics · voice · online multiplayer · public hosting.

**Change rule:** anything not on the in-scope list needs a decision card and Captain's FIAT before anyone builds it.

---

## 2. The scenario (draft rules, tuned in Gate 0)

A storm broke the river bridge. The village's food is running out, and the fields are on the far bank. Fix the bridge before the food runs out.

| Rule | Draft value |
|---|---|
| Map | 10×10. A river runs north to south; the only crossing is the broken bridge |
| Start | Everyone starts in the village square |
| Move | Up to 5 squares per action |
| Look | See everything within 2 squares |
| Gather | +2 wood per action, standing on a forest square |
| Carry | Each character carries at most 4 wood |
| Give | Hand wood to a character on the same square |
| Build | Put your wood into the bridge, standing at the correct bridge site |
| Say | Send one message to the team (costs an action; see Card D) |
| Win | 12 wood built into the correct bridge site before the food runs out |
| Lose | Food runs out first (a hidden day, 4 to 6) |

**The secrets (what makes teamwork matter).** Each AI character knows one thing the others don't. They change every game.

| Secret | Why it matters |
|---|---|
| Where the forest is | Others must search or be told |
| Which of 3 riverbank spots is the real bridge site | Building at a wrong spot wastes the action |
| How many days of food are left | Tells the team how fast to go |

Captain knows nothing special at the start, like a captain arriving at a new village.

**Rough feasibility check (done 2026-11-07).** A quick test of these draft numbers, not the real game engine:

| Team behavior | Bridge finished |
|---|---|
| Everyone already knows the secrets | Day 2 |
| Everyone spends day 1 sharing secrets | Day 3 |

So the game looks winnable with room for mistakes. Gate 0 must prove it again with the real rules, and tune the numbers so it is neither too easy nor impossible.

---

## 3. How a day works

1. **Morning:** each AI character gets a short report of what it can see and remember, and returns its plan for the day (see Card A).
2. **Day:** everyone's actions run in a fixed order. Momo checks each one. Rejected actions still use up the action, with a clear reason.
3. **Evening council:** Captain may ask the team a question and issue FIAT on the next day's goal. FIAT sets goals; it never lets anyone break a rule.
4. **Save:** the day is saved. The map picture redraws.

---

## 4. Truth and memory (from Proposal 001, all accepted)

| Layer | Owner | Can it be wrong? |
|---|---|---|
| World state | Game engine | No |
| Event log (every accepted action, numbered) | Game engine | No |
| Each character's memory | That character | Yes |
| Anything a character says | Nobody | Yes, it's just talk |

Talk never changes the world. Only actions that Momo accepts do.

---

## 5. Gates (build order)

Each gate must pass before the next starts. Hours are rough estimates out of 96.

| Gate | Goal | Done when | Est. hours |
|---|---|---|---|
| 0 | Winnable rules | A scripted team wins within 7 days × 3 actions; illegal actions are rejected; the same recorded actions always give the same result | 10 |
| 1 | World engine | The full rule set runs, with Momo checking every action | 16 |
| 2 | Save and replay | Stopping mid-game and restarting loses nothing; replays match exactly | 10 |
| 3 | AI teammates | The three AI characters play through the action menu only, within the budget | 20 |
| 4 | Real cooperation | Passes the 5 cooperation tests (below) | 14 |
| 5 | Captain plays | Captain plays full sessions and judges whether it's fun | 10 |
| 6 | Map picture polish | Only if time remains; a live viewer is not part of this contract | 6 |
| | Buffer | Fixes and surprises | 10 |

**Cooperation tests (Gate 4):**

| Test | Passes if |
|---|---|
| Hidden information (secrets reshuffled each game) | The team still wins most games |
| Silence (the "say" action switched off, same starting map and secrets) | Win rate drops clearly; if not, the talking was decoration |
| Fabrication (ask a character about something that never happened) | It answers "no record" |
| Crash (stop mid-game, restart) | Everyone resumes from the saved state |
| Replay (same recorded actions) | Same outcome, every time |

---

## 6. Budget controller (FIAT approved; enforced in code)

| Limit | Warning (80%) | Hard stop (100%) |
|---|---|---|
| Dollars per session | $0.20 | $0.25 |
| AI decisions per session | 24 | 30 |
| Dollars per month | $4.00 | $5.00 |

When a hard stop is reached:

1. AI calls stop. Nothing is lost; the game saves.
2. Captain can still look at the map, the log and the council notes for free.
3. Captain may resume a paused session only while under the monthly cap.
4. Raising any cap needs its own FIAT. "Resume" never raises a cap.
5. Retries count against the budget. At most 1 retry per failed decision.

The dollar cost of each call is not verified yet. Teso checks real prices before Gate 3; the code caps protect us either way.

---

## 7. Who does what

| Member | Role in construction |
|---|---|
| **Captain Hiro** | Decides by FIAT, runs the game on his computer, plays and judges fun. Does not need to read code |
| **Vero** | Writes the code with Captain in session, keeps the board, explains every decision in plain words |
| **Mago** | Reviews the design and each gate's results; architect's sign-off on gates 1–3 |
| **Teso** | Checks prices, watches the budget, signs off on the budget controller |
| **Momo** | Not a member: the referee code inside the game |

**Plain-language rule:** anything that reaches Captain comes as a decision card: the choice, the options, the risk of each, and a recommendation.

---

## 8. Decision cards for Captain (needed before construction FIAT)

### Card A — How the AI teammates use their 30 decisions

AI characters take up to 63 actions a game (3 characters × 7 days × 3), but the budget allows 30 AI decisions.

| Option | How it works | Risk |
|---|---|---|
| **A1. One plan per day (Vero's pick)** | Each morning, each AI picks its 3 actions in one go: 3 × 7 = 21 decisions, leaving 9 for council and retries | Plans can go stale mid-day; if an action fails, the rest of that day's plan is cancelled |
| A2. One decision per action | The AI rethinks before every move | Needs up to 63 decisions; breaks the 30 cap by about day 3 |

### Card B — Which AI service powers the in-game characters

Proposal 001 says one service at first, with three separate character sheets.

| Option | Notes |
|---|---|
| Claude (Anthropic) | Same family as Vero |
| ChatGPT (OpenAI) | Same family as Mago |
| Gemini (Google) | Same family as Teso |

**Vero's recommendation:** let Teso compare current prices for a small, cheap model from each, then run a quick test: can Captain tell the three characters apart? Pick the cheapest one that passes. Note: whichever we pick needs an account with prepaid credit. Prepaid credit is itself a safety net, because it can't overspend.

### Card C — Where the code lives

| Option | Notes |
|---|---|
| **C1. A new private GitHub repository, "oclan-game" (Vero's pick)** | Every change is saved and can be undone; the council board can link to progress |
| C2. A folder on Captain's computer only | Simpler, but no history, and harder to recover if something breaks |

### Card D — Does "say" cost an action?

| Option | Effect |
|---|---|
| **D1. Yes, it costs 1 of the 3 daily actions (Vero's pick)** | Sharing a secret is a real choice, which is the heart of the game; makes the silence test meaningful |
| D2. No, talking is free | Easier, but the team can share everything at no cost, so secrets matter less |

---

## 9. What Captain needs ready (before Gate 3)

1. Python installed on Captain's computer (Vero will guide this step by step).
2. An AI account with a small prepaid balance, once Card B is decided.
3. About 12 hours a week, as committed.

---

## 10. Sign-off

| Who | Status |
|---|---|
| Mago (architect) | Pending review |
| Teso (treasury) | Pending review |
| Vero (examiner, drafter) | Drafted |
| **Captain Hiro** | **Construction FIAT pending**, after Cards A–D |

*One Game. One World. One O'Clan.*
