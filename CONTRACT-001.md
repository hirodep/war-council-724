# Construction Contract 001 — "The Broken Bridge"

**Status:** REVISION 2 · **FIAT APPROVED 2026-11-07** · construction authorized; Gate 0 in progress
**Drafted by:** Vero, record keeper · Rev 1 and Rev 2: 2026-11-07
**Covers:** the first playable build of the O'Clan game (Proposal 001)
**Captain's decisions (2026-11-07):** Card A1 · Card B0 · Card C1 · Card D1 · construction FIAT issued

> **In one sentence:** in 8 weeks (about 96 hours), build one small turn-based game where Captain and three AI teammates must share secrets to fix a broken bridge, with every move checked by Momo and every dollar capped.

### What changed in Revision 2

| Finding (from Mago's review) | Fixed in |
|---|---|
| M1: the food secret may not matter | Section 2 (tighter food deadline) and section 5 (Gate 0 must prove each secret matters) |
| M2: how the daily AI plan works | Section 3 (new "daily plan rules") |
| M3: caps must be checked before spending, not after | Section 6 (reserve before every call) |
| M4: Gate 0 needs executable proof | Section 5 (Gate 0 checklist) |
| C1: rejected actions in the log | Section 4 |
| C2: the map picture is mandatory | Sections 1 and 5 |
| C3: Vero can't verify her own work | Section 7 (independent checks) |

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
- **A simple map picture redrawn after each turn (mandatory by FIAT)**
- The budget controller (section 6)

### Out of scope (needs a new FIAT to add)

Shaman dolls and villager growth · other NPCs · combat · economy and trading · more clans or villages · live animated graphics · voice · online multiplayer · public hosting.

**Change rule:** anything not on the in-scope list needs a decision card and Captain's FIAT before anyone builds it.

---

## 2. The scenario (draft rules, tuned in Gate 0)

A storm broke the river bridge. The village's food is running out, and the fields are on the far bank. Fix the bridge before the food runs out.

| Rule | Value (tuned in Gate 0) |
|---|---|
| Map | 10×10. A river runs north to south; the only crossing is the broken bridge |
| Start | Everyone starts in the village square |
| Move | Up to 5 squares per action (Captain rejected the Gate 0 tuning to 6, 2026-11-09) |
| Look | See everything within **1** square (**Captain's FIAT B1**, 2026-11-09; was 2) |
| Gather | +2 wood per action, standing on a forest square |
| Carry | Each character carries at most 4 wood |
| Give | Hand wood to a character on the same square |
| Build | Put your wood into the bridge, standing at the correct bridge site |
| Say | Send one message to the team (costs an action; see Card D) |
| Win | 12 wood built into the correct bridge site before the food runs out. **Finishing during the food day itself counts** (Mago G0-N1): the food check happens only at the end of that day, after every action |
| Lose | Food runs out first: a hidden day from **4 to 6** (**Captain's FIAT B1**, 2026-11-09; Rev 2 had 3 to 5) |

**The secrets.** Each AI character knows one thing the others don't. They change every game.

| Secret | Why it matters |
|---|---|
| Where the forest is (one of 3 possible spots: (0,0), (0,9) or (3,2)) | Others must search or be told |
| Which of 3 riverbank spots is the real bridge site | Building at a wrong spot wastes the action |
| On which day the food runs out (4, 5 or 6) | Decides whether the team can afford to explore or must rush |

**Captain's FIAT B1 (2026-11-09): food day 4–6 and look radius 1.** With food on day 3, 24 of 162 games could not be won even with perfect sharing, because messages arrive the next morning. Day 3 existed only to make the food secret matter, and FIAT F3 had already made it story only. A shorter look keeps sharing important. Gate 0 result with these rules: sharing team 162/162, silent team 52%. Captain rejected the alternative tuning (move range 6, forest spots moved).

**Captain's FIAT F3 (2026-11-07): the food secret is story only.** Gate 0 proved that in a pure race, knowing the deadline never changes the team's plan. Captain chose to keep it as story and tension rather than add a rule. Gate 0 check 9 applies to the forest and bridge-site secrets only.

**Why the food deadline changed (Mago's M1).** In Rev 1 the earliest deadline was day 4, but a good team finishes on day 2 or 3, so the food secret never mattered. With deadlines from day 3, a team that wastes day 1 can lose, so knowing the deadline changes what the team should do. Gate 0 will check this with real runs and adjust the numbers.

**Rough feasibility check (done 2026-11-07).** A quick test of the draft numbers, not the real game engine:

| Team behavior | Bridge finished |
|---|---|
| Everyone already knows the secrets | Day 2 |
| Everyone spends day 1 sharing secrets | Day 3 |

This is only a starting point. Gate 0 provides the real, executable proof.

---

## 3. How a day works

1. **Morning report:** every character, including Captain, gets a short report: what it can see, its memory, and any messages delivered overnight.
2. **Morning plans:** each AI character returns its plan for the day: 3 actions, in one decision. Captain also chooses 3 actions.
3. **Day:** actions run in a fixed order. Momo checks each one.
4. **Evening:** results, messages and the map picture are shown. Captain may hold a council and issue FIAT on the next day's goal. FIAT sets goals; it never lets anyone break a rule.
5. **Save.**

### Daily plan rules (Rev 2, answers Mago's M2)

| Question | Rule |
|---|---|
| Do AI characters plan at the same time or one after another? | **At the same time**, from the same morning report. Nobody sees another's plan in advance. This keeps each character's thinking independent |
| When does new information arrive? | Things a character sees with "look" are added to **its own** memory right away, but plans don't change mid-day. Messages from "say" are delivered to everyone at the **next morning report** |
| What if one action fails? | Momo rejects that action, and it still uses up its slot. **The rest of the plan continues**, with each action checked separately |
| What uses the spare decisions? | The budget is 30 per session: **21** for morning plans (3 characters × 7 days), up to **6** for council answers (each answer from one member = 1 decision), and **3** reserved for retries |
| What happens at 30 decisions? | The AI teammates stop. Each one "rests" (does nothing) for the rest of the game. The game saves. Captain may keep playing alone or end the session. Going past 30 needs its own FIAT |

Every action is still checked individually by Momo, whoever planned it.

---

## 4. Truth and memory

| Layer | Owner | Can it be wrong? |
|---|---|---|
| World state | Game engine | No |
| Event log (every accepted action, numbered) | Game engine | No |
| Rejected attempts (Rev 2) | Game engine | No. Kept in the log with their reason, but clearly marked as "rejected," separate from accepted events |
| Each character's memory | That character | Yes |
| Anything a character says | Nobody | Yes, it's just talk |

Talk never changes the world. Only actions that Momo accepts do.

---

## 5. Gates (build order)

Each gate must pass before the next starts. Hours are rough estimates out of 96.

| Gate | Goal | Done when | Est. hours |
|---|---|---|---|
| 0 | Winnable, fair rules | The Gate 0 checklist below passes | 12 |
| 1 | World engine | The full rule set runs, with Momo checking every action | 15 |
| 2 | Save and replay | Stopping mid-game and restarting loses nothing; replays match exactly | 10 |
| 3 | AI teammates | The three AI characters play through the action menu only, within the budget | 20 |
| 4 | Real cooperation | Passes the 5 cooperation tests (below) | 14 |
| 5 | Captain plays | Captain plays full sessions and judges whether it's fun | 10 |
| 6 | Map picture polish | The basic map picture is built earlier and is mandatory. Gate 6 is only optional polish, if time remains | 5 |
| | Buffer | Fixes and surprises | 10 |

### Gate 0 checklist (Rev 2, answers Mago's M1 and M4)

Gate 0 is a working program, not math on paper. It plays the game with scripted teams (no AI, no cost) and must show:

1. At least one legal winning sequence of actions
2. The win happens **before that game's actual food deadline** (day 3, 4 or 5), not just within 7 days (Mago's note N1)
3. No character ever takes more than 3 actions in a day
4. Wood is counted correctly, and the 4-wood carry limit is enforced
5. Building at a wrong bridge site is rejected
6. The food deadline ends the game on the right day
7. The same recorded actions always give the same result
8. **Many starting conditions** (different forest spots, bridge sites, food days and secret holders) are all winnable by a team that shares information
9. **Each secret matters:** for each secret, there are starting conditions where knowing it changes the team's best plan
10. **Communication matters:** scripted teams that never share win clearly less often than teams that do

If 9 or 10 fail, the numbers (map, deadlines, distances) are adjusted until they pass. Proposed starting target: sharing teams win 100% of test starts; silent teams win under 60%. These targets are proposals and can be tuned.

### Cooperation tests (Gate 4, with real AI)

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

### How spending is guarded (Rev 2, answers Mago's M3)

ELI5: before buying anything, the game checks the wallet for the highest possible price, not the expected one.

1. **Check first.** Before every paid AI call, the controller checks the remaining session and monthly budgets.
2. **Reserve the worst case.** Every call has a fixed maximum length, so its highest possible cost is known in advance. The controller sets aside that maximum.
3. **Refuse if it doesn't fit.** If the worst case doesn't fit in what's left, the call is not made.
4. **Settle after.** When the call finishes, the actual cost replaces the reservation.
5. **Assume the worst when unsure.** If a call times out or its cost is unknown, the full reserved amount counts as spent.
6. **Resume never raises a cap.** Captain can resume a paused session only while it fits under every cap. Raising any cap needs its own FIAT.

**Required budget tests (Mago's note N2):** before Gate 3, Teso verifies the chosen provider's real prices and how it charges. The cap tests must include duplicate requests, two spending attempts at the same moment, timeouts, and calls whose cost is unknown. The approved caps stay unchanged.

When a hard stop is reached, AI calls stop and the game saves. Captain can still look at the map, the log and the council notes at no cost.

The real price per call is not known yet. Teso checks current prices before Gate 3. The controller and the prepaid balance (Card B) protect us either way.

---

## 7. Who does what

| Member | Role in construction |
|---|---|
| **Captain Hiro** | Decides by FIAT, runs the game on his computer, plays and judges fun. Does not need to read code |
| **Vero** | Writes the code with Captain in session, keeps the board, explains every decision in plain words |
| **Mago** | Architect: reviews the design and each gate's evidence |
| **Teso** | Treasury: checks prices and independently examines the budget controller |
| **Momo** | Not a member: the referee code inside the game |

### Independent checks (Rev 2, answers Mago's C3)

Vero builds the game, so Vero's own tests do not count as independent proof. A gate is marked **IMPLEMENTED / VERIFIED** only when:

1. **Captain runs the tests on his own computer** and sees them pass (Vero walks him through it);
2. **Mago reviews the gate evidence:** the test report, the replay check results and the event log sample; and
3. for the budget controller, **Teso reviews the spending log and the cap tests.**

Mago and Teso work in other AI services and can't run the code themselves, so Vero produces a plain evidence report for each gate that Captain can pass to them.

**Plain-language rule:** anything that reaches Captain comes as a decision card: the choice, the options, the risk of each, and a recommendation.

---

## 8. Decision cards for Captain (needed before construction FIAT)

| Card | Question | Mago | Teso | Vero |
|---|---|---|---|---|
| A | How AI teammates use their 30 decisions | A1, with the rules in section 3 | A1 | **A1, with the section 3 rules** |
| B | Which AI service runs the in-game characters | Defer until Teso checks prices | Teso compares prices | **Defer: Teso compares; decide before Gate 3** |
| C | Where the code lives | C1, private repo "oclan-game", separate from SoyEssere | C1 | **C1** |
| D | Does "say" cost an action? | D1, review it in real play | D1 | **D1, reviewed after Gate 5** |

### Card A — How the AI teammates use their 30 decisions

| Option | How it works | Risk |
|---|---|---|
| **A1. One plan per day, with the section 3 rules (all three recommend)** | Each morning, each AI picks its 3 actions in one go: 21 decisions, plus 6 for council answers and 3 for retries | Plans can go stale mid-day |
| A2. One decision per action | The AI rethinks before every move | Needs up to 63 decisions; breaks the 30 cap by about day 3 |

### Card B — Which AI service powers the in-game characters

| Option | Notes |
|---|---|
| **B0. Decide later (all three recommend)** | Teso compares current prices, speed and character consistency for a small model from each service; Captain picks before Gate 3. Nothing before Gate 3 needs an AI service |
| Claude (Anthropic) | Same family as Vero |
| ChatGPT (OpenAI) | Same family as Mago |
| Gemini (Google) | Same family as Teso |

Whichever we pick needs an account with a small prepaid balance. Prepaid credit is a second safety net: it can't overspend.

### Card C — Where the code lives

| Option | Notes |
|---|---|
| **C1. A new private GitHub repository, "oclan-game" (all three recommend)** | Every change is saved and can be undone; kept separate from SoyEssere |
| C2. A folder on Captain's computer only | Simpler, but no history, and harder to recover if something breaks |

### Card D — Does "say" cost an action?

| Option | Effect |
|---|---|
| **D1. Yes, it costs 1 of the 3 daily actions (all three recommend)** | Sharing a secret is a real choice, which is the heart of the game. Reviewed after Captain's play sessions (Gate 5): if it makes characters too quiet to be fun, the council proposes a change |
| D2. No, talking is free | Easier, but the team can share everything at no cost, so secrets matter less |

---

## 9. What Captain needs ready

| When | What |
|---|---|
| Before Gate 0 | Python installed on Captain's computer (Vero guides it step by step); the "oclan-game" repository created (Card C) |
| Before Gate 3 | Card B decided; an AI account with a small prepaid balance |
| Throughout | About 12 hours a week, as committed |

---

## 10. Sign-off

| Who | Rev 1 | Rev 2 |
|---|---|---|
| Mago (architect) | Pass with conditions; construction hold (findings M1–M4, C1–C3) | **Pass with notes.** All 7 findings resolved; hold withdrawn. Notes N1–N2 added as verification requirements |
| Teso (treasury) | Support | **Support.** Section 6 cleared |
| Vero (examiner, drafter) | Drafted | Drafted |
| **Captain Hiro** | | **FIAT issued 2026-11-07:** Cards A1, B0, C1, D1 approved; construction authorized |

Council approval covers the construction **design** only. It is not proof that any software works; that comes gate by gate (section 7).

*One Game. One World. One O'Clan.*
