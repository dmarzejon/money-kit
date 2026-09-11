# Outreach email templates — After-Hours Lead Desk

**Channel:** AgentMail (cold)  
**ICP:** Owner-operated HVAC / plumbing / electrical / roofing / cleaning, ~2–25 trucks  
**Cadence:** Email 1 → wait 3 business days → Email 2 → wait 4 days → Email 3 (breakup)  
**Rules:** Plain text feel; one CTA; no attachments on first touch; personalize `{{first_name}}`, `{{company}}`, `{{city}}`, `{{trade}}`.

---

## Sequence A — Missed-call angle (default)

### A1 — Opener (Day 0)

**Subject lines (pick 1):**
- Quick question about after-hours calls at {{company}}
- {{first_name}} — who answers when your techs are on a job?
- {{city}} {{trade}} leads after 6pm

**Body:**
```
{{first_name}} — quick one.

When a {{trade}} lead calls {{company}} after hours or while your crew is on-site, do they get a person who can book… or a voicemail?

We built After-Hours Lead Desk for home service owners: AI answers the overflow, qualifies the job, and puts it on your calendar (Jobber / Housecall Pro / Google Calendar) — usually in under a minute.

If after-hours misses are costing you jobs in {{city}}, worth a 20-minute demo?

Here’s my calendar: {{calendar_link}}

— {{sender_name}}
```

### A1 follow-up note (if they reply “not interested”)
```
Appreciate it. If volume jumps this season, I’m around. I’ll send a 2-min clip of a sample {{trade}} receptionist in case it’s useful later.
```

---

### A2 — Proof / cost-of-inaction (Day 3)

**Subject:** Re: after-hours calls at {{company}}

**Body:**
```
{{first_name}} — looping back once.

Ballpark math we see a lot: miss 8–10 leads a month after hours, close even 3–4 of them, and that’s several thousand in jobs that never hit the board.

Happy to show a sample call flow for a {{trade}} shop (no obligation). 20 min:

{{calendar_link}}

If you’re covered with a live CSR nights/weekends, ignore this and I’ll stop.
```

---

### A3 — Breakup (Day 7)

**Subject:** Closing the loop — {{company}}

**Body:**
```
{{first_name}} — last note from me.

I’ll assume after-hours coverage isn’t a priority for {{company}} right now. If that changes when AC / freeze / storm season hits, you can grab time here: {{calendar_link}}

Either way, good luck with the season in {{city}}.

— {{sender_name}}
```

---

## Sequence B — Competitor speed angle

### B1 — Opener

**Subject:** Your competitors are answering in 60 seconds

**Body:**
```
{{first_name}},

Homeowners in {{city}} usually hire the first {{trade}} company that texts back with a clear next step — not the best brochure.

After-Hours Lead Desk responds to missed calls + web forms in under 60 seconds, qualifies, and books the slot on your calendar.

Want to hear a sample receptionist trained on {{trade}} jobs?

{{calendar_link}}

— {{sender_name}}
```

### B2 — Follow-up

**Subject:** Re: 60-second response

**Body:**
```
Quick bump — can show you the exact booking path (form → SMS → calendar) in 20 minutes.

If you already nail sub-5-minute response 24/7, you’re ahead of most shops and I’ll leave you alone.

{{calendar_link}}
```

### B3 — Breakup

**Subject:** Should I close your file?

**Body:**
```
{{first_name}} — I’ll close this out on my side unless you want the demo.

Calendar if useful later: {{calendar_link}}
```

---

## Sequence C — Answering-service upgrade

### C1 — Opener

**Subject:** Answering service vs booking desk

**Body:**
```
{{first_name}} — if {{company}} uses a nighttime answering service, this might be relevant.

Message-taking helps. Booking helps more.

We replace “someone will call you back” with a qualified appointment on your calendar — same night — with rules for service area, job type, and when to escalate to you.

Open to a short teardown of your current after-hours flow?

{{calendar_link}}
```

### C2 — Follow-up

**Subject:** Re: answering service vs booking desk

**Body:**
```
One more try: I can play a 90-second sample {{trade}} call and map it against what your service does today.

{{calendar_link}}

If timing’s bad, tell me when season slows and I’ll check back then.
```

### C3 — Breakup

**Subject:** Final ping

**Body:**
```
Closing the loop. If you ever want the sample call without a meeting, reply “clip” and I’ll send it.

— {{sender_name}}
```

---

## AgentMail merge fields checklist
- `{{first_name}}` `{{company}}` `{{city}}` `{{trade}}` `{{calendar_link}}` `{{sender_name}}`
- Suppress on bounce / unsubscribe
- Cap: ≤40 new cold/day until reputation proven
- Never claim fake client logos; use “lab demo” language until real case studies exist
