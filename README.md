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
6. [Joining as an athlete](#joining-as-an-athlete)
7. [Setup: athletes, lines, and OTs](#setup-athletes-lines-and-ots)
8. [Break Times](#break-times)
9. [Team competitions](#team-competitions)
10. [Check-in](#check-in)
11. [Start List & Speaker Mode](#start-list--speaker-mode)
12. [Judging results](#judging-results)
13. [Penalties (Rulebook 17.8)](#penalties-rulebook-178)
14. [Protests](#protests)
15. [Re-swim & Opener](#re-swim--opener)
16. [Schedule adjustments (OT Delay)](#schedule-adjustments-ot-delay)
17. [Push notifications](#push-notifications)
18. [Offline operation](#offline-operation)
19. [AIDA integration](#aida-integration)
20. [Multi-day events](#multi-day-events)
21. [Results and export](#results-and-export)
22. [Display & Language](#display--language)
23. [FAQ](#faq)
24. [Troubleshooting](#troubleshooting)
25. [Privacy & Data](#privacy--data)
26. [Contact](#contact)

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
   *Tip: tick **Remember email** to pre-fill your email next time. You can also tick **Remember password** — the password is then kept in your device's secure keystore (iOS Keychain / Android EncryptedSharedPreferences), never on our servers. Sign out to clear both.*
2. Events screen → tap **Join with code** → paste the invite code.
3. You appear as Pending until the Organizer approves you and assigns a role (Judge, Main Judge, Staff, …).

### For Athletes

1. Open the app, sign up with your email.
2. Choose **I am an athlete** during signup.
3. The app tries to match your name to AIDA's start lists automatically.
4. If matched, your registered events appear immediately. If your name has duplicates, ask the Organizer for a one-time invite code.

You are now ready to run the day.

---

## Roles and what each can do

| Role | Setup | Judge | Check-in | Users | Log | OT Delay | Send Push |
|------|-------|-------|----------|-------|-----|----------|-----------|
| 👑 Organizer | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ⚖️ Main Judge | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| ✏️ Judge | — | ✅ | ✅ | — | — | — | — |
| 👀 Staff | — | view | ✅ | — | — | — | — |
| 🏊 Athlete | — | — | — | — | — | — | — |
| ⏳ Pending | — | — | — | — | — | — | — |

- **Organizer** is the default role for whoever creates the event.
- **Main Judge** has the same permissions as Organizer; assign in Users.
- **Athlete** is read-only — start lists and personal results only. No access to other members' data, AIDA token, or controls.
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

If you leave these blank or set the token to `test` or `demo`, the app runs in 🧪 **Mock mode** — it generates sample athletes for practice. Mock mode does not send anything to AIDA.

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

## Joining as an athlete

If you are competing rather than running the event, sign up as an athlete to see your start list, OT, line, and personal results.

You can switch between staff and athlete views at any time: tap your avatar (top-right) → **Switch to Athlete Mode** (and back the same way).

### How it works

When you sign up, the app reads your name and tries to match it to athletes that organizers have already loaded into the app from AIDA. If exactly one match is found, your account is linked automatically. Otherwise, the organizer can issue a one-time invite code.

### Path A — Automatic matching (most cases)

1. Sign up with your email.
2. Choose **I am an athlete**.
3. Enter your **first name**, **last name**, **gender**, and **nationality**, exactly as registered with AIDA.
4. The app searches loaded events. If your name matches a single athlete and the gender/nationality agree, you are linked immediately.
5. The Events screen now shows the events you appear in. Tap one to see your start list and (later) your results.

### Path B — Invite code (when names collide)

If two athletes share the same name, automatic matching cannot decide which one is you. Ask the Organizer for an invite code:

1. The Organizer opens the event → **Athlete Invite Codes** → finds your name in the list → taps it to generate a 6-character code.
2. The Organizer sends you the code privately.
3. You open the app → Events → **Enter invite code** → paste it.
4. The app verifies the code and links your account.

### Find me on AIDA

> ![Find me on AIDA search](images/aida-find-me.png)

If automatic matching does not find you, you can link your AIDA athlete profile by hand. In **Edit Profile** or **Athlete Setup**, tap **Find me on AIDA**, type your name, and pick your profile from the results. This stores your AIDA athlete ID so your results match correctly. The 🔄 sync icon also pulls in events you are registered for. (Athletes with no competition history may not appear in search — in that case enter your name, nationality, and gender manually, exactly as registered with AIDA.)

### What you can see

Athlete Mode has four tabs: **My Info**, **Start List**, **Results**, and **Rewards** (past events show three — no Start List).

- 🏊 Athlete role: read-only access to events you appear in.
- **My Info** — your assigned OT, line, check-in status (Pending / Checked-in / DNS / Late), and your result. You can also file a protest here (see [Protests](#protests)).
- **Start List** — the day's running order, with a "Show my line only" filter.
- **Results** — published results.
- **Rewards** — points standings by discipline and gender, with your row highlighted.

You cannot see other athletes' personal information, judges' notes, or AIDA tokens.

### Push notifications

If you allow notifications, you receive:

- **Start list published** — when the Organizer publishes the day's start list.
- **Unofficial / Official results** — when results are released.
- **OT delay** — if the schedule shifts and your OT changes.
- **Check-in deadline reminders** — automatic, only if you have not checked in yet:
  - 1 hour before check-in deadline (which is OT − 1h)
  - 30 minutes before check-in deadline
- **Protest updates** — if a protest concerning you is filed on your behalf (asking for your signature) or decided by the jury.

Notification text arrives in your chosen app language. You can turn notifications off at any time in your device's system settings or in the app's About screen.

---

## Documents (Consent Forms)

Many events require athletes to submit AIDA consent forms before competing. Open **My Info → Documents**.

- **Required forms** — Competition Entry, Image Rights consent, and Liability waiver. A **Medical Statement** is optional but often requested.
- **Two ways to submit** — *Fill in app* (type the fields and sign on screen; a PDF is generated for you) or *Upload photo* of a signed paper copy.
- **Medical Statement** — valid for one year from its issue date. Save it on your profile (Edit Profile → Medical Statement) to reuse it across events. If you upload a photo, enter the issue date shown on the certificate. A pressure injury or black-out *after* the issue date makes the certificate invalid — submit a new one.
- **Deadline** — if mandatory forms are missing by the day before the event, you receive a push reminder listing what is missing.

**For staff (Organizer / Main Judge):** open **More → Documents** to review each athlete's submission status, open files, and **download everything as a ZIP** (folders by document type). When an athlete declares an injury or black-out, the medical statement is flagged for **manual verification** — confirm the certificate in person, then tap *Mark verified*. Submitted documents are kept for 15 days after the event, then deleted.

## Setup: athletes, lines, and OTs

> ![Setup screen layout](images/setup-screen.png)

Setup is where you decide the schedule for the day: which line each athlete swims on, when their OT (official time) is, and what breaks happen during the day.

**Auto-save** — every change you make in Setup is saved to the server automatically. If you leave the app and come back, your settings are restored. If a co-organizer reloads athletes from AIDA, the schedule still respects your line configuration.

### Loading athletes

- **Load Athletes** — pulls the registered start list from AIDA. Idempotent: existing judgments are preserved on reload.
- **Mock mode** — generates a sample start list for practice.

### Configuring lines and OTs (basic)

- **Lines** — number of lanes (Pool) or platform lines (Depth).
- **First OT** — the time when the first athlete starts (e.g. `09:00`).
- **Interval** — gap between consecutive athletes on the same line.
- **Depth Line Interval** (Depth / Team only) — when **ON**, the lines run sequentially: each line starts at a staggered offset (Line 1, then Line 2 a few minutes later, …), and the Start List shows a per-line countdown. The offset must satisfy `(lines − 1) × line_interval < athlete_interval`, otherwise the schedule cannot be generated. When **OFF**, all lines run **in parallel** — the athletes in the same row share the same OT, exactly like Pool mode.

### Advanced Setup (optional, collapsible)

> ![Advanced Setup collapsed](images/setup-advanced-collapsed.png)
> ![Advanced Setup expanded](images/setup-advanced-expanded.png)

Tap **Advanced Setup** to expand more options for fine-grained control:

- **Per-discipline lines** (Pool only) — assign a different number of lanes to each discipline. For example, STA uses 4 lanes but DYN/DNF use only 2 lanes. The app generates separate sub-schedules per discipline and stitches them together.
- **Cross-discipline lane carry-over** — when the previous discipline ends mid-line (e.g. STA ends on lane 3 with 4 lanes), the next discipline can either restart from lane 1 (default) or continue from lane 4. Useful when judges stay on the same lane across disciplines.

- **Custom Intervals** — beyond the base interval, give different intervals to ranges of athletes by start order. Example: #1–#10 → 10 min, #11–#20 → 8 min, #21–#30 → 7 min. Tap **Add interval**, set *From order / To order / Interval*, then **Done** — OTs recompute and save automatically. Per-day; ranges must not overlap and must stay within the athlete count; with no ranges the base interval applies to everyone. If a manual break exists for the day, the OT recompute is skipped (same as Save Configuration) to protect manually adjusted OTs.

### Line assignment

After loading athletes, open **Assign Lines** to move them between lines and reorder. OTs are recalculated automatically:

- Pool: round-robin assignment, OT depends on position within the line.
- Depth: full sequence with line cycling, accounting for the depth line interval rule.

**Direct line assignment** — for special cases (e.g. a specific line reserved for a national record attempt, or placing a re-swim — see [Re-swim & Opener](#re-swim--opener)), tap an athlete, then tap the target line and position. The schedule re-flows to honour your choice.

Save when done — start times are now finalised for the day.

---

## Break Times

Breaks pause the schedule for a fixed window. The app supports two kinds of breaks.

### Time-based break (Lunch Break, etc.)

> ![Time-based break in Setup](images/break-time-based.png)

Use this for fixed-time breaks that everyone agrees on in advance (lunch, ceremony, etc.):

1. Open Setup → **BREAK TIMES** → **Add Break Time**.
2. Choose **Time-based**.
3. Enter the start time and end time (e.g. `12:00` – `13:00`).
4. Save.

Any athletes whose OT falls inside the break window are pushed back so their OT lands after the break ends. The lane assignment is preserved.

### After Athlete break (NEW in Build 48)

> ![After Athlete break being added](images/break-after-athlete-add.png)
> ![After Athlete break listed](images/break-after-athlete-listed.png)

Use this when you need to insert a break **after a specific athlete finishes**, regardless of clock time. Typical scenario: the warm-up athletes finish, you want a 60-minute rest before the official athletes start.

1. Open Setup → **BREAK TIMES** → **Add Break Time**.
2. Choose **After Athlete**.
3. Pick the athlete who marks the end of the segment.
4. Enter the break duration (e.g. `60` minutes).
5. Save.

The selected athlete plus **every athlete after them in the start list order** is shifted by the break duration. Other disciplines (athletes earlier in the order, even at the same clock time) are not affected. Lane assignment is preserved.

To remove a break, tap the 🗑️ trash icon next to it in the BREAK TIMES list.

---

## Team competitions

Team events (event type **Team**) group athletes into teams whose combined scores decide the standings. A **Teams** section appears in **Setup** — only for Team-type events.

> ![Teams section in Setup](images/team-setup.png)

### Creating and editing teams

Tap **New Team** to open the team editor.

> ![Team editor — name, color, members](images/team-edit.png)

- **Name** — required.
- **Color** — pick a colour so the team is easy to spot in lists.
- **Members** — tick the athletes who belong to the team. The list is searchable by name or nationality. Selecting an athlete who is already on another team moves them over.

Each team card shows its name, colour, and member count. Tap a card to **edit**, or use its menu to **delete** it.

> An athlete who competes on more than one day appears once — selecting them assigns **all** of their day entries to the team, so you pick each person only once.

---

## Check-in

Athletes sign in before warm-up. Open the **Check-in** tab.

- Tap an athlete card with a pending status to open the signature sheet.
- Athlete signs on screen, tap **Save** → the athlete is marked as Checked In with the current time. The card then shows both the OT and the check-in time.
- For no-shows: tap the athlete → confirm **DNS** (Did Not Show).
- For late arrivals beyond the cutoff: tap → **Late Check-in**. They get a Red card with "Late Check-in" remark automatically.
- **Automatic late check-in** — an athlete still pending once the check-in deadline (OT − 1h) has passed is marked **Late Check-in** automatically. The pending list shows each athlete's deadline as `Check-in HH:mm`.
- **AIDA sync** — DNS and Late Check-in are submitted to AIDA automatically (as a Red card / 0 points), just like a judged result. You no longer need to enter these by hand in Judge.
- Tap a mini card at the top (In / Late / DNS / Pending) to filter the list to that group.

> The signature drawing is for visual confirmation only — it is shown to the staff member at the moment of check-in and discarded as soon as the sheet closes. We do not store the signature image anywhere (not on the server, not on the device). Only the fact that a signature was captured is recorded, along with the check-in time.

> Check-in works offline too. If the device is offline when you confirm, the check-in is held in device memory with a small ⛔ "Offline" badge on the card, and synced to the server automatically within 5 seconds of reconnecting. See [Offline operation](#offline-operation).

---

## Start List & Speaker Mode

> ![Start List screen with countdown](images/start-list-countdown.png)

The Start List tab shows the day's running order with a live countdown to the next athlete's OT. As each OT approaches, the app speaks the countdown aloud so athletes and judges hear it without watching the screen.

### Voice countdown

As each OT approaches, the app plays spoken cues so athletes and judges hear the count without watching the screen. The cues are **pre-recorded audio files**, so they sound **identical on iOS and Android** (earlier versions used each phone's built-in text-to-speech, which differed between devices).

Cues before OT:
`2:00` ("two minutes to official top"), `1:30`, `1:00`, `0:30`, `0:20`, `0:10`, then `5 — 4 — 3 — 2 — 1`, and at OT: **"official top"**.

Cues during the start window (after OT): **"plus one"** at +1 s, then the elapsed seconds are called as the window runs out — up to the discipline's limit — ending with **"start cancelled"** if the athlete has not started by the end of the window.

### Mute button

> ![Mute toggle on Start List](images/start-list-mute.png)

Tap the 🔊 / 🔇 icon in the AppBar to toggle voice announcements. Useful when:

- You are running an indoor pool with a separate PA system already announcing.
- The athletes prefer silent countdown.
- You stepped into a meeting and need to hush the device.

Mute applies only to the device you toggle it on — other devices in the same event keep speaking. The visual countdown keeps running regardless.

### Speaker Mode

> ![Speaker Mode active](images/speaker-mode.png)

Speaker Mode turns the device into a **dedicated countdown announcer** — perfect for the venue's main loudspeaker. Once enabled:

- The screen is locked into Start List view; other tabs are hidden.
- Mute is forced off (cannot be muted accidentally).
- The screen stays awake (no auto-lock).
- A PIN is required to exit Speaker Mode, so a curious bystander cannot accidentally close it.

**To enable**: open the role / profile menu → **Speaker Mode** → set a 4-digit PIN.

**To exit**: tap the Speaker Mode badge → enter the PIN → confirm.

Recommended setup: a dedicated phone or tablet plugged into the venue's audio system, in Speaker Mode for the entire competition day. Keep it on a charger — voice playback drains the battery faster than passive idle.

### Screen always on

The app keeps the screen awake on **every** screen, not only Start List, so countdowns and notifications work even if you don't touch the device. This is a global setting — it applies as soon as you open the app. Note: keep the device plugged in for full-day events; the battery will drain faster than normal.

---

## Judging results

> ![Judge tab with athlete cards](images/judge-tab.png)

The Judge tab shows all athletes for the current day. Tap a card to enter the result.

### Entering a result

1. **RP** — realised performance (time for static, distance for dynamic, depth for depth).
2. **Card** — White (clean), Yellow (penalty), or Red (DQ).
3. **Penalty reasons** — required when a card other than White is selected. See [Penalties](#penalties-rulebook-178).
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

## Penalties (Rulebook 17.8)

The app follows AIDA Rulebook section 17.8. Reasons are grouped by card colour.

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

### Multi-select and combined cards

> ![Red card multi-select sheet](images/judge-red-multi-select.png)

When you tap the Red card, the reason sheet shows **both Red and Yellow** reasons in two groups:

- **DQ Reason (Red)** — Surface Protocol, Blackout Surface, Blackout UW, Airways, DQ Late Start, Jump Start, Pull, Touch, Other Lane, Check-in DQ, DQ Other
- **Additional Penalty (Yellow)** — Under AP, No Tag, Grab, Pull, Turn, Start, Early Start, Late Start, Lanyard, Other Penalty

You can select multiple reasons across both groups in one save — for example Red **Airways** plus Yellow **Under AP**. Selected chips are colour-coded by category so you can see what is being recorded at a glance.

Yellow card on its own also supports multi-select (e.g. Early Start + Grab). Yellow cards do not show the Red group.

---

## Protests

A protest is a formal challenge to a result, filed under AIDA Rulebook 17.8. Apnea Comp tracks the whole flow — filing, the athlete's signature, the jury's decision, and any change to the result.

**Every protest ends with the athlete's signature**, even when a staff member starts it on the athlete's behalf.

### Who can file

Organizer, Main Judge, Judge, or the athlete. Fees are not tracked in the app.

### Filing as an athlete

> ![Athlete files a protest](images/protest-file.png)

1. Athlete Mode → **My Info** → tap **File Protest** next to your result.
2. Enter the reason, sign on screen, and submit.

> ![Protest signature pad](images/protest-sign.png)

The protest status becomes **Pending** — waiting for the jury.

### Filing on behalf (staff)

1. **Judge** tab → tap an athlete card → **File Protest (on behalf)**.
2. Enter the reason and submit. No signature yet.
3. The protest goes to the athlete as **Awaiting signature**. The athlete opens **My Info** on their own phone, reviews it, and signs — only then does it become **Pending**.

### Jury decision

> ![Protest list](images/protest-list.png)

Open **More → Protests** (Organizer / Main Judge / Judge). The list groups protests by status (Awaiting signature / Pending / Reviewing / Accepted / Rejected / Withdrawn). Tap one to decide.

> ![Protest decision screen](images/protest-decide.png)

- **Accept** — you can amend the result (card, RP, remarks). The athlete's record updates automatically, and the change flows to Results, Rewards, and AIDA.
- **Reject** / **Withdraw** — the result stands.

A protest cannot be decided while it is still **Awaiting signature** — the athlete must sign first.

### Deleting a protest

Organizer or Main Judge can delete any protest from its detail screen (🗑 trash icon) — use this to clear a test entry, or a legacy protest that is stuck waiting for a signature that will never come.

### Notifications

All staff and the affected athlete receive a push when a protest is **filed**, **awaiting signature**, or **decided**, in their chosen app language.

---

## Re-swim & Opener

### Re-swim

When a protest is accepted (or a judge calls for a re-performance), the athlete swims again. Because loading a day's start list from AIDA replaces that day's athletes, a re-swim is **reserved in a queue** first, then inserted when the target day's list is built — so it is never wiped out by a reload.

> ![Reserve a re-swim — choose the day](images/reswim-reserve.png)

1. **Reserve** — Judge / Main Judge / Organizer. Approve the re-swim while deciding the protest, or reserve it for a chosen day (pick the date from the day dropdown).
2. **Place** — when that day's start list is built or loaded, the app prompts: *"N re-swim(s) to place."* Choose an automatic sort (AP ascending / descending / random) or place each athlete manually with **Assign Lines** (tap the athlete, then the target line and position). If the re-swim is on the day already loaded, you can place it immediately; otherwise there is a **"Place pending re-swims"** safety button under Setup → Add Athlete.

> ![Place a re-swim into the start list](images/reswim-placement.png)

3. **Original excluded** — the original entry is marked **invalidated**: excluded from rankings (Rewards) but still shown in Results. The re-swim result feeds the day's ranking and is pushed to AIDA using the original start ID.

### Opener

An **opener** is a warm-up or demonstration entry that should not count. Organizer / Main Judge add one under **Setup → Add Athlete**: name, nationality, gender, discipline, AP, PB (STA uses a mm:ss time picker; other disciplines use a number). Openers are **excluded from rankings and never sent to AIDA**.

> ![Add Athlete dialog (opener / manual entry)](images/add-athlete.png)

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

### Side effects

- **Push notifications** — every athlete whose OT changed receives an automatic push: *"Your OT has been delayed by N minute(s)"*. They do not need to be subscribed to anything; the notification is targeted by the affected athletes only.
- **Activity log** — recorded in the Log screen.

### Important

- Only positive delays are supported. Cannot shift earlier.
- Undo is **not available yet** — review the preview carefully before applying.
- All staff devices update in real time.

---

## Push notifications

Apnea Comp uses push notifications for time-sensitive event updates. Notifications are delivered through OneSignal, which forwards them to APNs (iOS) and Firebase Cloud Messaging (FCM, Android). Each notification is sent in the recipient's chosen app language.

### What gets sent

There are two flavours: notifications you trigger manually, and ones the system sends automatically based on event state.

#### Manual (Organizer / Main Judge only)

From the More menu, **Send Push** opens a small panel with three buttons. Each sends to all athletes registered for the chosen day:

- **Publish Start List** — when the day's lanes and OTs are confirmed.
- **Unofficial Results** — release initial results for athlete review.
- **Official Results** — final results after the protest window.

Each tap shows a confirmation dialog with the recipient count before sending.

#### Automatic

These run without staff action:

| Trigger | Recipients | When |
|---------|-----------|------|
| OT Delay applied | Affected athletes only | Immediately when an Organizer / Main Judge applies a delay |
| Check-in deadline reminder (1 hour) | Athletes who have not checked in | 2 hours before OT (= 1 hour before check-in deadline) |
| Check-in deadline reminder (30 minutes) | Athletes who have not checked in | 1.5 hours before OT (= 30 minutes before check-in deadline) |
| Protest filed | All event staff + the athlete | When a protest is submitted |
| Protest awaiting signature | All event staff + the athlete | When staff file on the athlete's behalf |
| Protest decided | All event staff + the athlete | When the jury accepts / rejects / withdraws |

Once an athlete checks in (or is marked DNS / Late), the reminders stop.

### Who receives notifications

Only users with all of the following:

- A linked athlete account (Path A or Path B above)
- Notifications enabled at the OS level
- Notifications enabled in the app (default: on)
- An active push token (created when the app is launched at least once)

### Disabling notifications

- iPhone: Settings → Apnea Comp → Notifications → toggle off.
- Android: Settings → Apps → Apnea Comp → Notifications → toggle off.
- In the app: More → About → Notifications toggle.

Disabling clears your push token from the server immediately.

---

## Offline operation

The app is designed to keep working when the internet drops mid-day, which is common at pool / depth venues.

### What happens when you lose connection

A red bar **"You are offline"** appears at the top. You can still:

- ✅ Save Judge results (stored locally, synced later)
- ✅ Check-in athletes (stored locally, synced later)
- ❌ Load new athlete lists from AIDA
- ❌ Receive push notifications (delivered when reconnected, FCM holds them)

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

Set the token to `test` or `demo` (or leave both fields blank) to run without AIDA. The app generates sample athletes; nothing is sent. Use this for training, dry runs, or app demos. Mock-mode events ignore real-world dates so countdown and voice prompts work immediately for testing.

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
- **Export** — share a CSV for posting on a notice board or sending to athletes.

### Rewards & ranking

The **Rewards** tab (also a tab in Athlete Mode) ranks athletes by points, grouped by discipline and gender.

- **Day chips** — Total, Day 1, Day 2, … to scope the standings.
- **Include yellow card scores** toggle.
- **Tiebreak** (⚙ top-right) — drag to reorder the tiebreak rules. The AIDA default (Rulebook §4.2.16) is: total points → **smallest AP−RP difference** → fewer Red → fewer Yellow → more White cards. Athletes who remain exactly tied share the same place and the next place is skipped (**Olympic placing**, e.g. two 1st → next is 3rd). Depth RP is entered in whole meters (§4.1.22.1).
- Openers and invalidated (re-swum) entries are excluded from rankings; everyone still appears in Results.
- **Export CSV** — the ↓ icon shares a UTF-8 CSV (opens correctly in Excel / Numbers in every language) reflecting the current Day / Yellow / Tiebreak settings.

---

### Records (WR/CR/NR)

Mark and confirm World / Continental / National record attempts.

1. **Mark the event** — when creating or editing an event, toggle **World Record** and / or **Continental** under **Record Attempts**. A 🏅 badge then shows on the event card and the Results header.
2. **Check records** — on the **Results** tab, tap **Check WR/CR/NR**. For each white-card athlete the app queries the AIDA official records (by nationality, discipline, gender) and suggests WR / CR / NR. Needs network — entries it cannot fetch are skipped.
3. **Confirm** *(Organizer / Main Judge)* — a suggestion shows as a dashed badge (e.g. "WR?"). Tap it to confirm the level or clear it. Confirmed records show as a solid badge and are included in the CSV export.

> Only white-card (valid) performances qualify. A performance with any penalty cannot be a World or Continental Record (Rulebook §10.2). The suggestion compares the realized performance (RP) to the current record; the judge makes the final decision.


## Display & Language

Both settings live in the avatar menu (top-right), and apply instantly across the app.

### Theme

> ![Theme picker](images/theme-picker.png)

Tap your avatar → **Theme** → choose **System default**, **Light**, or **Dark**.

### Language

> ![Language picker](images/language-picker.png)

Tap your avatar → **Language** → choose **System default**, **English**, **한국어**, **日本語**, **简体中文**, or **繁體中文**. The app switches immediately and remembers your choice.

Competition-standard terms stay in English in every language — OT, AP, RP, PB, discipline codes (STA, DYN, …), WHITE / YELLOW / RED, role names, and Line — so staff from different countries read the same labels.

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

### What happens if internet drops during check-in?

The check-in is saved locally and the athlete card shows a small ⛔ "Offline" badge. As soon as the connection comes back, the check-in syncs to the server automatically (within 5 seconds). The athlete does not need to sign again. The signature drawing itself is not stored — it is only used for visual confirmation at the moment.

### An athlete is not receiving push notifications

Common causes:

- The athlete is signed up but not yet linked to an AIDA athlete record (no automatic match found, no invite code redeemed). Without the link, the system does not know which athlete is them.
- Notifications are disabled at the OS level. iPhone: Settings → Apnea Comp → Notifications. Android: Settings → Apps → Apnea Comp → Notifications.
- The app has not been launched on the new device yet — push tokens are issued at launch.
- The athlete has been marked DNS / Late / already checked in (in which case check-in reminders intentionally stop).

### Can I delete an event?

Yes. An Organizer or Main Judge can delete an event — swipe it in the event list, or use **Edit Event → Delete**. Deletion is permanent and removes all of that event's data (athletes, results, logs, check-in status, protests). Generated protest PDFs in file storage are not auto-removed on full-event deletion; contact us if you need them purged.

### A protest is stuck on "Awaiting signature" and the athlete can't sign

This happens with old protests created before the current signature flow. An Organizer or Main Judge can open **More → Protests → the protest → 🗑** and delete it. See [Protests → Deleting a protest](#protests).

### The app shows an "Update required" screen and won't let me in

Your installed version is below the minimum the organizer set for live use. Update to the latest version from the App Store / Play Store, then reopen — the app re-checks and lets you through.

### Do I need to keep the app open during the day?

Yes, on the device(s) used for judging or check-in. The app does not run in the background. If you switch to another app the screen state is preserved, but offline auto-retry pauses until you reopen the app.

**The app prevents the screen from auto-locking on every screen**, so you can leave the device on a table without it going dark. The battery drains faster than normal because of this — keep the device plugged in for full-day events.

Push notifications themselves do not require the app to be open — iOS / Android deliver them even when the app is closed, as long as you have permitted notifications.

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

### Push notifications stopped working after I switched phones

Sign in on the new phone and launch the app once. The new device's push token replaces the old one in your account. The old phone will no longer receive notifications.

---

## Privacy & Data

For full details on what data the App collects, how it is processed, and your rights, see the [Privacy Policy](https://elfreediving.github.io/aida-competition-privacy/PRIVACY_POLICY).

Quick summary:

- **What is stored** — your account email, display name, profile picture (if you upload one), AIDA athlete UUID (if you signed up as an athlete), push notification subscription ID (if notifications are enabled), and the competition data you enter (athlete results, check-in status, activity logs, and protests).
- **Protest signatures** — when a protest is filed, the athlete's (and jury's) hand-drawn signature **is** stored as part of the official protest record, and embedded in a generated PDF. This is the one exception to the rule below.
- **What is not stored** — athletes' contact details, photos, dates of birth, **check-in** signature drawings (the check-in pad is visual confirmation only), or any personal identifiers beyond what AIDA exposes publicly.
- **Where** — Supabase (currently US region), encrypted at rest, accessed only via Row-Level Security policies that scope data per-event. Push notifications transit through OneSignal, which forwards them to APNs (iOS) and FCM (Android).
- **AIDA tokens** — encrypted, accessible only to Organizer / Main Judge roles, never exposed in URLs or client memory longer than necessary.
- **Offline buffering** — judge results saved while offline live in the App's memory only and sync within seconds of reconnecting.
- **Local device storage** — **Remember email** saves your email to standard local storage (SharedPreferences / NSUserDefaults). **Remember password**, if you enable it, saves your password to the device's secure keystore (iOS Keychain / Android EncryptedSharedPreferences), never to our servers. Your theme and language choices are also stored locally. Sign out or uninstall to clear stored credentials.

---

## Contact

For bugs, questions, or feedback:

- Email: lee33179@gmail.com

When reporting a problem, please include:

- Device model and OS version
- App version (More → About)
- A screenshot if relevant
- Approximate time the problem occurred (so we can match it with logs)

---

Last updated: 2026-06-02.
