# Apnea Comp — User Manual

**AIDA Competition Management System**

This manual covers running an apnea competition with Apnea Comp from setup to results. The in-app Help (More → Help) is a quick reference; this document goes deeper, with operational scenarios and troubleshooting.

If you only have five minutes, read **Quick Start** below and the FAQ at the bottom.

---

## Contents

1. [Before you start](#before-you-start)
2. [Quick Start](#quick-start)
3. [Roles and what each can do](#roles-and-what-each-can-do)
4. [Creating an event (Organizer)](#creating-an-event-organizer)
5. [Joining an event (Staff)](#joining-an-event-staff)
6. [Setup: athletes, lines, and OTs](#setup-athletes-lines-and-ots)
7. [Check-in](#check-in)
8. [Judging results](#judging-results)
9. [Penalties (Rulebook 17.7)](#penalties-rulebook-177)
10. [Schedule adjustments (OT Delay)](#schedule-adjustments-ot-delay)
11. [Offline operation](#offline-operation)
12. [AIDA integration](#aida-integration)
13. [Multi-day events](#multi-day-events)
14. [Results and export](#results-and-export)
15. [FAQ](#faq)
16. [Troubleshooting](#troubleshooting)
17. [Contact](#contact)

---

## Before you start

You will need:

- An iPhone or Android device with the Apnea Comp app installed.
- A reliable internet connection (optional during the day — see [Offline operation](#offline-operation)).
- An account on AIDA International if the event will be officially scored (Organizer only).
- For Organizers: the AIDA Token and Event ID for the competition. Without these the app runs in 🧪 Mock mode (sample data, no AIDA sync).

We recommend each judge / staff member uses their own device. The app supports several people working on the same event simultaneously — results sync between devices in real time.

---

## Quick Start

### For the Organizer (event creator)

1. Open the app, tap **+** on the Events screen.
2. Enter event name, type (Pool / Depth / Team), dates, and tap Create.
3. Open the event → **Edit Event** → paste **AIDA Token** and **AIDA Event ID** → tap **Test Connection** → Save.
4. Setup tab → **Load Athletes** to pull the start list from AIDA.
5. Setup tab → set **Lines** (number of lanes), **First OT**, and **Interval** between athletes.
6. Share the event **invite code** (visible in Edit Event) with your staff.
7. Approve staff in **Users** tab as they join (they appear as Pending).

### For Staff (judges, check-in officials, …)

1. Open the app, sign in.
2. Events screen → tap **Join with code** → paste the invite code.
3. You appear as Pending until the Organizer approves you and assigns a role (Judge, Main Judge, Staff, …).

You are now ready to run the day.

---

## Roles and what each can do

| Role | Setup | Judge | Check-in | Users | Log | OT Delay |
|------|-------|-------|----------|-------|-----|----------|
| 👑 Organizer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ⚖️ Main Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ✏️ Judge | — | ✅ | ✅ | — | — | — |
| 👀 Staff | — | view | ✅ | — | — | — |
| ⏳ Pending | — | — | — | — | — | — |

- **Organizer** is the default role for whoever creates the event.
- **Main Judge** has the same permissions as Organizer; assign in Users.
- **Pending** members wait until an Organizer or Main Judge approves them in Users and assigns a real role.

---

## Creating an event (Organizer)

### Basic info

- **Name** — visible to your staff.
- **Type** — 🏊 Pool, 🌊 Depth, or 👥 Team.
- **Dates** — for multi-day events, choose start and end dates.

### AIDA Integration (recommended)

Open the event → **Edit Event** → fill:

- **AIDA Token** — from your AIDA admin panel.
- **AIDA Event ID** — numeric ID of the AIDA competition.

Tap **Test Connection**. A green checkmark means the credentials are valid and the app can read the start list. Save.

> ![Edit Event screen with AIDA fields](images/edit-event-aida.png)

If you leave these blank or set the token to `test`, the app runs in 🧪 **Mock mode** — it generates sample athletes for practice. Mock mode does not send anything to AIDA.

### Inviting your staff

The invite code is shown in **Edit Event**. Share it via your usual channel (chat, email, paper). Staff use **Join with code** on the Events screen to enter the code.

> Tip: rotating the invite code is not yet supported. Treat it like a password and only share with people who should be on the team.

---

## Joining an event (Staff)

1. Sign in to the app.
2. On the Events screen, tap **Join with code**.
3. Paste the code. The event appears in your list with status **Pending**.
4. Wait for the Organizer to approve you and assign a role. You will see the event become tappable once approved.

If you accidentally use the wrong code, ask the Organizer to remove you from Users so you can try again.

---

## Setup: athletes, lines, and OTs

> ![Setup screen layout](images/setup-screen.png)

### Loading athletes

- **Load Athletes** — pulls the registered start list from AIDA. Idempotent: existing judgments are preserved on reload.
- **Mock mode** — generates a sample start list for practice.

### Configuring lines and OTs

- **Lines** — number of lanes (Pool) or platform lines (Depth).
- **First OT** — the time when the first athlete starts (e.g. `09:00`).
- **Interval** — gap between consecutive athletes on the same line.
- **Depth Line Interval** (Depth only) — minimum gap between two athletes on different lines. Must satisfy `(lines − 1) × line_interval < athlete_interval`, otherwise the schedule cannot be generated.

### Line assignment

After loading athletes, open **Line Assignment** to drag them between lines and reorder. OTs are recalculated automatically:

- Pool: round-robin assignment, OT depends on position within the line.
- Depth: full sequence with line cycling, accounting for the depth line interval rule.

Save when done — start times are now finalised for the day.

---

## Check-in

Athletes sign in before warm-up. Open the **Check-in** tab.

- Tap an athlete card with a pending status to open the signature sheet.
- Athlete signs on screen, tap **Save** → the athlete is marked as Checked In and the signature is stored.
- For no-shows: tap the athlete → confirm **DNS** (Did Not Show).
- For late arrivals beyond the cutoff: tap → **Late Check-in**. They get a Red card with "Late Check-in" remark automatically.

> Check-in requires internet. If you are offline, the signature step will fail with a red SnackBar — try again once reconnected. (Result-saving in Judge does work offline; check-in does not, yet.)

---

## Judging results

> ![Judge tab with athlete cards](images/judge-tab.png)

The Judge tab shows all athletes for the current day. Tap a card to enter the result.

### Entering a result

1. **RP** — realised performance (time for static, distance for dynamic, depth for depth).
2. **Card** — White (clean), Yellow (penalty), or Red (DQ).
3. **Penalty reasons** — required when a card other than White is selected. See [Penalties](#penalties-rulebook-177).
4. **Start offset** — seconds early (negative) or late (positive). Used for the start-window penalty calculation.
5. **REMARKS** — required for certain reasons (BO, Other Penalty, DQ Other, etc.). The app pre-fills a template; complete the missing detail.
6. Tap **Save Result**.

### Card badges

After saving you will see a small badge on the athlete card:

- **✅ AIDA** — synced to AIDA International.
- **🔁 Retry** — sync to AIDA failed; tap to see the reason and retry.
- **⛔ Offline** — saved locally on this device; will sync automatically once you are back online. See [Offline operation](#offline-operation).

If no badge is shown, AIDA integration is not configured (no startId for that athlete) — that is normal in Mock mode.

---

## Penalties (Rulebook 17.7)

The app follows AIDA Rulebook section 17.7. Reasons are grouped by card colour.

### 🟨 Yellow card reasons

- **Start** — incorrect start technique (Pool DYN: failed wall start, etc.).
- **Early Start** — left before the OT. 1 point per 5 seconds early, within the start window.
- **Late Start** — left after the OT. 1 point per 5 seconds late, within the start window.
- **Grab** — pulled on the line, wall, or platform during the performance.
- **Other Penalty** — anything else not covered. **REMARKS required**.

### 🟥 Red card reasons

- **Surface Protocol** — incorrect surface protocol within 15 seconds of surfacing.
- **Blackout Surface** — loss of motor control or consciousness at the surface. **REMARKS required** (recovery time, etc.).
- **Blackout UW** — blackout underwater. **REMARKS required**.
- **DQ Late Start** — Late Start exceeded the start window (Pool +10s, Depth +30s).
- **Jump Start** *(Pool DYN only)* — left the wall before OT.
- **DQ Other** — disqualification for any other reason. **REMARKS required**.

### Start window

| Discipline | Window | Within window | Past window |
|------------|--------|----------------|-------------|
| Pool | ±10 s | 1 pt / 5 s (Yellow Early/Late Start) | DQ Late Start (Red) for late side; Jump Start (Red, DYN only) for early-pool wall start |
| Depth | ±30 s | 1 pt / 5 s (Yellow Early/Late Start) | DQ Late Start (Red) for late side |

### REMARKS

AIDA Rulebook 4.1.16.2 requires written reasons for every Yellow and Red. The Save button blocks the action if REMARKS is empty for a reason that requires it.

When you select a reason, the REMARKS field is pre-filled with a template (e.g. `BO Surface, recovery: ___`). Complete the missing detail before saving — this is the official record.

Multi-select is supported for Red cards (e.g. Surface Protocol + Blackout Surface). Tap each applicable reason.

---

## Schedule adjustments (OT Delay)

If the day slips — long warm-up, an incident, equipment issue — you can shift remaining OTs without rebuilding the start list.

### Where to find it

On the **Start List** or **Judge** tab, the AppBar shows a 🕒 icon just before the role badge on the right. **Visible only for Organizer and Main Judge.**

> ![OT Delay icon location](images/ot-delay-icon.png)

### How to use

1. Tap 🕒 → the **Adjust Schedule** dialog opens.
2. Pick the athlete the delay starts from (the first one whose OT shifts).
3. Enter the delay in **minutes** (whole minutes, positive only).
4. Preview shows the new times — old → new for each affected athlete.
5. Tap **Apply**.

Every OT from the chosen athlete onward shifts forward by that amount. The corresponding check-in / warm-up times shift too.

### Important

- Only positive delays are supported. Cannot shift earlier.
- Each adjustment is recorded in the Log screen.
- Undo is **not available yet** — review the preview carefully before applying.
- All staff devices update in real time.

---

## Offline operation

The app is designed to keep working when the internet drops mid-day, which is common at pool / depth venues.

### What happens when you lose connection

A red bar **"You are offline"** appears at the top. You can still:

- ✅ Save Judge results (stored locally, synced later)
- ❌ Check-in athletes (requires internet — try again after reconnect)
- ❌ Load new athlete lists from AIDA

### The Offline badge

> ![Offline badge on athlete card](images/offline-badge.png)

When you save a result while offline, the athlete card shows a small **⛔ Offline** badge instead of the AIDA sync badge. This means:

- The result is **safe** in your device's memory.
- It has **not yet** reached the server.
- The app will retry automatically every 5 seconds in the background.

When the internet returns, the badge changes to **✅ AIDA** automatically. No manual action needed.

### Manual sync

If for some reason auto-retry has not caught up, open **Results**:

> ![Results sync banner](images/results-banner.png)

If anything is pending you will see an orange banner:

- **"N offline result(s) waiting to sync"** with a **Sync now** button — tap to retry immediately.
- **"M results not synced to AIDA"** with a **Resync** button — for AIDA-side failures (token, server error, …).

### ⚠️ Important

Offline results live in your device memory until they sync. **Do not force-close the app or reboot the phone while you have offline items pending** — they would be lost. Wait for the ⛔ badges to clear, or tap Sync now before quitting.

If you are unsure, open Results and look for the orange banner. No banner = nothing pending.

---

## AIDA integration

### Getting your token

Log in to your AIDA International admin account at <https://www.aidainternational.org>. Open the competition you registered. Look for the API / Integration section to copy:

- **AIDA Token** — looks like a long string of letters and digits.
- **AIDA Event ID** — a number, usually 4–6 digits.

If you do not see these options, the AIDA admin who registered the event needs to share them, or your account permissions need updating.

### Configuring in the app

Edit Event → paste both values → Test Connection → Save. The app caches the token securely on the server (never exposed in URLs). When you update the token, the new value is used immediately for the next save (no app restart needed).

### What syncs and when

- **Read** — Setup → Load Athletes pulls the start list, including names, AP, PB, and discipline.
- **Write** — every Save in Judge sends the result (RP, card, reasons, remarks, start offset). Background, non-blocking.

### When sync fails

- **Token expired / invalid** → red SnackBar: *"AIDA token invalid — update in Edit Event"* (Organizer / Main Judge) or *"ask Organizer to update"* (others). Update the token, then Results → Resync.
- **Network error** → 🔁 Retry badge on the card. Tap it for the error message and retry, or use Results → Resync to do all at once.
- **Offline** → ⛔ Offline badge. Auto-retries when online; see [Offline operation](#offline-operation).

### Mock mode

Set the token to `test` (or leave both fields blank) to run without AIDA. The app generates sample athletes; nothing is sent. Use this for training, dry runs, or app demos.

---

## Multi-day events

For competitions spanning multiple days:

- Setup → **Total Days** → set to the number of competition days.
- Each day has its own start list, check-in, results, and OTs.
- A **Day selector** appears below the AppBar when there is more than one day. Tap to switch.
- **Rest days**: mark them in Setup; they are skipped in scheduling.

Data does **not** carry between days — moving an athlete in Day 2 does not affect Day 1. Total scores across days are computed in Results.

If your event is registered on AIDA with multiple days, Load Athletes pulls the per-day start lists automatically.

---

## Results and export

The **Results** tab shows live standings, updated as judgments come in.

- **Summary cards** at the top: total athletes, white / yellow / red, AP / PB / RP.
- **Discipline filter** to narrow by event.
- **Sync banners** (if any) at the top: Offline pending, AIDA pending, or token issues.
- **Athlete list** sorted by points, with detail on tap.
- **Export** — share a CSV / image for posting on a notice board or sending to athletes.

---

## FAQ

### A staff member's phone runs out of battery — do I lose their entries?

No. As soon as they save a result, it is stored on the server (or on their device if offline). Other devices in the same event see the result immediately. Even if their phone is permanently lost, only their unsynced offline results would be at risk — and only if they had any pending at the moment of failure.

### Two people are looking at the same athlete and saving different results

Last save wins. The app does not currently warn about concurrent edits. Coordinate verbally to avoid this — typically only one judge enters a given result.

### An athlete shows AP / PB but no startId — why?

Likely they were added in Mock mode or imported manually outside AIDA. AIDA sync requires a startId; results for those athletes will not be sent to AIDA (no badge shown). They still appear in Results.

### I changed the AIDA token and old results are still failing

Open Results → if the banner says "Update token & resync" → tap it. Pending items will be re-sent with the new token. The app caches credentials on the server and refreshes the cache when you save Edit Event, so no app restart is needed.

### Check-in failed when I had no internet — does the athlete need to sign again?

Yes. The signature was not saved (we never accept a check-in without confirming the server received it). Once back online, ask the athlete to sign again.

### Can I delete an event?

Currently events can be archived but not permanently deleted from the app. Contact us if you need a deletion (privacy, GDPR-style request).

### Do I need to keep the app open during the day?

Yes, on the device(s) used for judging or check-in. The app does not run in the background. If you switch to another app the screen state is preserved, but offline auto-retry pauses until you reopen the app.

### What devices are supported?

iPhone (iOS 15+) and Android (Android 9+). Tablet works but the layout is optimised for phone.

---

## Troubleshooting

### "Could not save" red SnackBar in Judge

This means the app could not even store the result locally — usually because the athlete was loaded but the local list got out of sync. Tap **Reload** (Setup) and try again. The error message includes the athlete ID and current count for diagnosis.

### "AIDA token invalid" keeps appearing

- Confirm in Edit Event that the token has no leading/trailing spaces.
- Tap Test Connection — does it succeed?
- If Test fails: contact your AIDA admin to issue a new token.
- If Test passes but saves still fail: open Results → Resync.

### App shows "You are offline" but I am clearly online

The connectivity check pings the server. If the server is briefly unreachable (rare) or your network blocks Supabase URLs (unusual on hotel / public wifi), the indicator may stay red. Try saving a result anyway — if it succeeds, the indicator clears within a few seconds.

### OT Delay icon is missing

Check:

- You are on the **Start List** or **Judge** tab (icon hides on other tabs).
- Your role is Organizer or Main Judge (other roles cannot see it).
- Look on the right side of the AppBar, just before the role badge.

### Schedule looks wrong after Line Assignment

The OT calculation runs on save. If you reordered athletes and saw the wrong OTs, scroll up and tap **Save** again — the times should now match the order. If not, please contact us with a screenshot.

### A team member is stuck on Pending

Open Users tab → find their name → assign a role (Judge / Staff / …). They need to be approved per event; approval does not carry between events.

### Results screen is blank but I have judged athletes

Pull down to refresh. If still blank, switch to another tab and back. If the issue persists, please screenshot and contact us — this should not happen.

---

## Privacy & Data

For full details on what data the App collects, how it is processed, and your rights, see the [Privacy Policy](https://elfreediving.github.io/aida-competition-privacy/PRIVACY_POLICY).

Quick summary:

- **What is stored** — your account email, display name, profile picture (if you upload one), and the competition data you enter (athlete results, signatures, activity logs).
- **What is not stored** — athletes' contact details, photos, dates of birth, or any personal identifiers beyond what AIDA exposes publicly.
- **Where** — Supabase (currently US region), encrypted at rest, accessed only via Row-Level Security policies that scope data per-event.
- **AIDA tokens** — encrypted, accessible only to Organizer / Main Judge roles, never exposed in URLs or client memory longer than necessary.
- **Offline buffering** — judge results saved while offline live in the App's memory only and sync within seconds of reconnecting.

---

## Contact

For bugs, questions, or feedback:

- Email: lee33179@gmail.com

When reporting a problem, please include:

- Device model and OS version
- App version (More → About — coming soon)
- A screenshot if relevant
- Approximate time the problem occurred (so we can match it with logs)

---

*This manual is part of the Apnea Comp project. Source on GitHub: <https://github.com/elfreediving/apnea-comp-manual>. Last updated: 2026-05-03.*
