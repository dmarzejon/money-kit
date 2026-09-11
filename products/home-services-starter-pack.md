# AI Automation Starter Pack for Home Service Businesses

**Subtitle:** Checklists, scripts, and wiring diagrams to stop losing after-hours jobs — without hiring a nighttime CSR.

**Edition:** 1.0 · September 2026  
**For:** Owners and office managers in HVAC, plumbing, electrical, roofing, and cleaning (roughly 2–25 trucks).  
**Not for:** Enterprise franchises with full call centers, or shops getting fewer than ~5 inbound leads per month.

---

## How to use this pack

Block **half a day**. Work the sections in order:

1. Diagnose your leak (Scorecard)  
2. Write your rules (Qualification sheet)  
3. Install the minimum stack (48-hour wiring checklist)  
4. Paste the scripts (Voice / SMS / Form)  
5. Test with the 10-call gauntlet  
6. Track results for 14 days (KPI sheet)

If you want this installed for you as a done-with-you / done-for-you system, that’s our productized service: **After-Hours Lead Desk** (setup + monthly retainer).

---

## 1. After-Hours Revenue Leak Scorecard

Score each item **0** (no) · **1** (sometimes) · **2** (yes, reliable).

| # | Question | Score |
|---|----------|-------|
| 1 | Every missed call after 5pm gets a callback the **same evening** | |
| 2 | Web form leads get a human or automated reply in **under 5 minutes**, nights included | |
| 3 | Someone can **book a calendar slot** without waiting for the owner to wake up | |
| 4 | Out-of-area and tire-kicker leads are filtered before they hit your phone | |
| 5 | You know last month’s count: inbound leads · missed · booked · no-shows | |
| 6 | Angi/Yelp/Facebook leads enter the **same** follow-up path as website leads | |
| 7 | Customers get SMS confirmation with time window + prep instructions | |
| 8 | Angry or complex calls have a clear escalate-to-owner path | |
| 9 | Reviews are requested automatically after completed jobs | |
| 10 | You could explain your after-hours process to a new hire in under 10 minutes | |
| | **TOTAL / 20** | |

**Read the score**
- **0–8:** You’re donating jobs to whoever texts back first. Start at Section 2 this week.  
- **9–14:** Partial system — fix booking + speed (Sections 3–4).  
- **15–20:** Optimize seasonality and multi-channel (Section 6 stretch goals).

**Rough dollar lens:**  
`(Missed after-hours leads per month) × (Close rate if you’d responded) × (Average ticket) = Monthly leak.`  
Example: 10 × 0.4 × $650 ≈ **$2,600/mo**.

---

## 2. Qualification & Disqualify Sheet (fill once)

### Service identity
- Trade(s): ________________________________  
- Primary city / ZIPs served: ________________________________  
- Hard no ZIPs / cities: ________________________________  
- Residential only? Y/N · Light commercial? Y/N  

### Hours & coverage
- Business hours: ________________________________  
- After-hours policy: (a) book next open slot (b) emergency dispatch fee $_____ (c) on-call tech  

### Job types
| Book now | Book with deposit / fee disclosure | Never book — escalate or reject |
|----------|-------------------------------------|----------------------------------|
| e.g. no-heat, clogged main, sparking outlet | e.g. full system replace estimate | e.g. commercial chiller, outside radius |

### Money talk (what AI / receptionist may say)
- Diagnostic / trip fee: $_____  
- Emergency after-hours fee: $_____  
- “We don’t quote complex jobs over the phone — we book an on-site.”

### Escalate to owner immediately if
- Customer is angry / threatening  
- Active water / gas / electrical hazard with panic in voice  
- Media / lawyer / insurance adjuster  
- VIP / commercial account on list: ________________

Tape this sheet next to whoever handles the phone — or paste into your AI receptionist prompt.

---

## 3. 48-Hour Minimum Wiring Checklist

### Hour 0–2 — Map
- [ ] List every lead source (Google Business calls, website form, Angi, Yelp, Facebook, referrals)  
- [ ] Note who answers each during business hours vs after hours today  
- [ ] Pick **one** booking destination to start: Google Calendar **or** Jobber **or** Housecall Pro **or** ServiceTitan  
- [ ] Write emergency fee + service area in one sentence

### Hour 2–8 — Capture
- [ ] Enable missed-call text-back (carrier feature or VoIP) **or** overflow to AI/voice agent  
- [ ] Website form → webhook / Zapier / Make → SMS to lead within 60 seconds  
- [ ] Same path for at least one marketplace lead email (Angi/Yelp forward)  
- [ ] Shared inbox or CRM stage: `New → Qualified → Booked → Done`

### Hour 8–16 — Book
- [ ] Publish 2–3 bookable windows per day for the next 7 days  
- [ ] Confirmation SMS template live (Section 4)  
- [ ] Owner SMS alert on `Booked` and on `Escalate`  
- [ ] Calendar title format: `{Trade} | {Name} | {ZIP} | {Phone}`

### Hour 16–48 — Prove
- [ ] Run the 10-call gauntlet (Section 5)  
- [ ] Fix two tone issues max — don’t rewrite forever  
- [ ] Go live on **nights/weekends only** first if you’re nervous  
- [ ] Start the 14-day KPI log (Section 6)

**Tools note:** Start dumb. Google Voice/VoIP + form + Calendar + SMS beats a six-week software evaluation.

---

## 4. Scripts you can paste

### 4.1 Missed-call / after-hours SMS (first touch)
```
Hi {{first_name}}, it’s {{company}} — sorry we missed you.
Are you dealing with (1) an emergency needing today/tonight, or (2) scheduling a visit this week?
Reply 1 or 2 and your address/ZIP so we can check service area.
```

### 4.2 Qualification follow-up
```
Got it — we serve {{service_area}}.
For {{job_type}}, I can book:
A) {{slot_1}}
B) {{slot_2}}
Reply A or B. Diagnostic/trip fee is ${{fee}}; I’ll text confirmation + what to have ready.
```

### 4.3 Out-of-area rejection (polite)
```
Thanks for reaching out — you’re a bit outside our service area ({{service_area}}), so I don’t want to book you and then cancel.
If you have a neighbor ZIP we cover, send it; otherwise here’s a trusted referral if we have one: {{referral_or_omit}}.
```

### 4.4 Voice / AI receptionist — core prompt skeleton
```
You are the after-hours receptionist for {{company}}, a {{trade}} company serving {{service_area}}.
Goals: (1) determine emergency vs schedulable, (2) confirm ZIP in area, (3) book an approved calendar slot OR take a callback request, (4) disclose trip/emergency fees when asked or before booking emergency.
Never invent prices for full replacements. Never argue. If caller is angry, or describes active uncontrolled hazard with panic, say you’ll have the owner call back within {{escalate_minutes}} minutes and end booking flow.
Speak in short sentences. Confirm phone number. Repeat the appointment time once.
```

### 4.5 Web form auto-reply (email or SMS)
```
Subject: We got your request — {{company}}

Thanks {{first_name}} — we received your {{job_type}} request for {{ZIP}}.
We’ll confirm a window shortly. If this is an emergency (no heat/AC in extreme weather, active leak, sparking), reply EMERGENCY and a phone number we can reach now.
```

### 4.6 Appointment confirmation
```
You’re booked with {{company}} on {{date}} {{window}}.
Address: {{address}}
Phone on file: {{phone}}
Please ensure access to {{equipment_or_panel}}. Reply C to confirm or R to reschedule.
```

### 4.7 Post-job review ask (send next day)
```
Hi {{first_name}} — {{tech_name}} marked your job complete. If we earned it, would you leave a quick Google review? {{review_link}}
Thank you for trusting {{company}}.
```

---

## 5. Ten-Call Gauntlet (test before you trust it)

Run these as real tests (friend’s phone or staff). Check pass/fail.

| # | Scenario | Expect | Pass? |
|---|----------|--------|-------|
| 1 | In-area no-heat emergency at 9:30pm | Fee disclosed, urgent slot or on-call escalate | |
| 2 | In-area maintenance, flexible | Books normal window, confirms SMS | |
| 3 | Out-of-area ZIP | Rejects politely, no booking | |
| 4 | “Just need a ballpark for full replace” | No fake quote; offers on-site estimate slot | |
| 5 | Hang up mid-qualify | System logs partial; optional SMS resume | |
| 6 | Angry about previous bill | Escalate — no debate | |
| 7 | Wrong trade (“do you do roofs?” if you’re HVAC-only) | Decline / refer | |
| 8 | Spam / robocall pattern | Short reject, no calendar spam | |
| 9 | Dual-language preference (if you offer it) | Correct language path or polite English fallback | |
| 10 | Form fill at 11pm with phone + ZIP | SMS &lt;60s, booking path offered | |

**Ship rule:** 9/10 pass → go live nights. Fix failures; don’t add features.

---

## 6. 14-Day KPI Log

| Date | Source | Inbound | First response &lt;5m? | Qualified | Booked | Emergency fee said? | Notes |
|------|--------|---------|----------------------|-----------|--------|---------------------|-------|
| | | | | | | | |
| | | | | | | | |
| | | | | | | | |

**Weekly review questions**
1. Where did we still miss?  
2. Which script got confusion?  
3. What’s the recovered-job estimate this week?  
4. One change for next week only.

---

## 7. Stretch upgrades (after 14 days)

- [ ] Merge Angi/Yelp into the same SMS desk  
- [ ] CRM sync (Jobber/HCP/ServiceTitan) instead of Calendar-only  
- [ ] Review ask automation  
- [ ] Seasonal prompt pack (AC rush / freeze / storm roofing)  
- [ ] Spanish script variant if your market needs it  
- [ ] Missed-call → voicemail transcription → SMS  

---

## 8. Buyer’s guide: DIY vs hire it out

| | DIY with this pack | After-Hours Lead Desk (our service) |
|--|--------------------|-------------------------------------|
| Cost | Your time + existing tools | Setup $1,997–$5,997 + retainer |
| Speed | 48 hours if focused | ~10–14 days installed + tuned |
| Best when | &lt;15 leads/week, technical owner | Consistent lead flow, want monitoring |
| Risk | You maintain scripts | We monitor + seasonal updates |

---

## 9. One-page owner playbook (print this)

**When the desk texts you “ESCALATE”** → call within 15 minutes.  
**When it books** → don’t reshuffle without texting the customer.  
**When a lead complains about AI** → “Thanks — I’ll take it from here,” then note the transcript for a script fix.  
**Never** turn the desk off on the first weird call — fix the rule.  
**Every Monday** → 15-minute KPI glance.

---

## Bonus: Season trigger cheat sheet

| Trigger | Script tweak |
|---------|--------------|
| Heat wave / AC rush | Prioritize no-cool; publish more same-day windows |
| Deep freeze | Prioritize no-heat; disclose delays honestly |
| Hail / wind | Roofing: photo request via SMS before booking |
| Holidays | Publish reduced windows early; state holiday fee if any |

---

## You’re done when…

- [ ] Scorecard completed  
- [ ] Qualification sheet filled  
- [ ] Wiring checklist checked  
- [ ] Gauntlet ≥9/10  
- [ ] KPI log started  

That’s a real after-hours system — not a chatbot toy.

---

## Want it installed for you?

**After-Hours Lead Desk** — productized AI receptionist + speed-to-lead for home service companies.

- Starter · Growth · Fleet packages  
- Sub-60s response paths · calendar booking · owner alerts  
- Lab demos labeled as demos until live client results exist  

→ Book a 20-minute demo: `{{landing_url}}`  
→ Or reply to the email this pack came from with your trade + city + approx leads/week.

---

*© 2026 · AI Automation Starter Pack for Home Service Businesses · Edition 1.0*  
*Personal use license for your business. Do not resell the pack verbatim.*
