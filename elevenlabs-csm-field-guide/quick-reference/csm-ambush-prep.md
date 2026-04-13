# CSM Pre-Meeting Quick Reference
## Your Pre-Flight Card — Use It the Morning Before Every Buyer Conversation

---

> *"Every person in that buying committee gave up something
> to be there. Respect for their time is the only consensus
> that already exists before the meeting starts."*
> — Module 06: The Buying Committee Playbook

---

## 1. WHO — Know the Room Before You Enter It

### The Buying Committee

| Persona | What They Need to Leave With | What Silence Means |
|---------|-----------------------------|--------------------|
| **Business Owner** | A clear next step they own | They're worried their team can't use it |
| **Business Leader** | A number or outcome they can repeat upward | They've mentally moved to their next meeting |
| **IT Administrator** | A confirmed path to get their questions answered | They are building a case for no |
| **Legal** | Named follow-up on consent and IP questions | They have a concern they haven't voiced yet |
| **Finance** | Worst-case invoice scenario addressed | They're doing math in their head |

### The Missing Champion Check
Before walking in — confirm:

☐ Is the deal champion in the room today?
☐ Do they have the authority and context to advance the deal?

**If the champion is missing:** Adjust the meeting goal.
You are no longer advancing the deal.
You are building the case the champion will carry forward.
Know which meeting you're in before you start.

---

## 2. WHAT — Know What You're Selling Today

### Platform Quick Reference

> *"ElevenLabs is an AI tool that creates voices that sound
> like real people — and can do that in 70+ languages."*

| Capability | What It Does | Who Asks About It |
|------------|-------------|-------------------|
| **Text to Speech** | Converts text to spoken audio in 70+ languages | Business Owner, Marketing |
| **Voice Cloning — Instant** | Clone from 1–2 min of audio. Fast. Source-quality dependent. | Business Owner |
| **Voice Cloning — Professional** | High-fidelity clone from ~30 min studio audio. Brand-ready. | Business Owner, Business Leader |
| **Voice Library** | Thousands of licensed pre-built voices | Business Owner |
| **ElevenAgents** | Voice and chat agent deployment at scale | Out of scope — escalate |

### Integration Status — Is Their Stack Ready?

| Platform | Status | CSM Note |
|----------|--------|----------|
| HeyGen | ✅ Native — with conditions | Credits bill to ElevenLabs, not HeyGen. API key permissions must be correct. |
| Zapier | ⚠️ Partial | Ephemeral URL problem. Multi-step workflows need workarounds. |
| Make | ⚠️ Partial | Basic TTS native only. Advanced use needs HTTP module. |
| Adobe | 🔄 Workaround Required | Manual round-trip. Lock script before generating. |
| Descript | 🔄 Workaround Required | ElevenLabs quality OR Descript workflow. Not both. Currently. |

*Verify current status before any meeting where integration is a deciding factor.*
*Last verified: April 2026 — see Module 03 for full detail.*

### If an IT Administrator Will Be Present

☐ Trust Center URL confirmed: compliance.elevenlabs.io
☐ Top certifications and what they cover reviewed
☐ Escalation path for deep compliance questions confirmed

*See Module 08: Data Security and Compliance —
pre-meeting checklist.*

### Voice Cloning Readiness Check

If voice cloning is on the agenda:

☐ Use case identified — Instant or Professional?
☐ Source audio plan discussed?
☐ Audience familiarity with the speaker assessed?
☐ Language requirements confirmed?
☐ Demo gap conversation completed?
☐ Module 2B legal checklist reviewed before any cloning begins?

### Non-Technical Operator Check

☐ Will a non-technical user be operating the platform?
   If yes → confirm the week-one onboarding sequence
   is scheduled before they generate production content.

*See Module 04: The Fine-Tuning Learning Curve.*

---

## 3. OPPORTUNITY — Where This Conversation Could Go

### Expansion Signals to Listen For

| If the buyer says... | The opportunity is... | Module to have ready |
|---------------------|----------------------|---------------------|
| "We need this in multiple languages" | Cross-language clone → Professional Clone upsell | 02A, 07 |
| "We want to use our brand voice everywhere" | Integration reality conversation → workflow design | 03 |
| "Our team will be generating a lot of content" | Pricing and regeneration cost education → quota planning | 05 |
| "We need this to sound exactly like our spokesperson" | Professional Clone quality conversation | 02A |
| "What happens to our data?" | Trust Center and compliance conversation | 08 |
| "Can we use this for [edge case use]?" | Prohibited Use Policy awareness → escalate | 02B |
| "How does this work with our existing tools?" | Integration reality → workflow design conversation | 03 |
| "What can't it do yet?" | Honest limitations → Exit framework | 07 |

### The Upsell Path

```
Instant Clone → Professional Clone
  Signal: brand voice, audience familiarity, multilingual needs

Scale Tier → Business Tier
  Signal: Professional Clone requirement, volume, enterprise support needs

Single product → Multi-product
  Signal: content pipeline questions, automation interest, agent curiosity
```

### The Module to Pull Mid-Meeting

| Situation | Pull This |
|-----------|-----------|
| IT Administrator goes quiet | Module 08 |
| Legal team shows up | Module 02B |
| Pricing question surfaces | Module 05 |
| Integration question surfaces | Module 03 |
| Limitation surfaces | Module 07 — Exit 0 first |
| Room starts to drift | Module 06 — pivot lines |
| Non-technical operator concern | Module 04 |
| Surface Proactively | These limitations — before the buyer asks | Module 07 |

*Limitation 2 (cross-language clone degradation),
Limitation 6 (uncanny valley), and Limitation 7
(disappearing Library voice) should be surfaced
proactively when relevant to the buyer's stated use case.
A CSM who names it first converts a trust problem
into a credibility moment.*

---

## Monthly Character Budget Estimator

Use this before any conversation where quota or overage is likely to come up.
Leave a copy with every new Scale or Business customer in week one.

```
Plan allotment:              ___________ characters

Estimate per project:
  Script word count:         ___________ words
  × 6 (characters/word):     ___________ characters per script
  × avg. regenerations:      ___________ (budget 8–10 first month,
                                          3–5 after ramp)
  = characters per project:  ___________

Projects per month:          ___________

Estimated monthly use:       ___________ characters

Buffer (20% recommended):    ___________

Total budget needed:         ___________

If total > plan allotment → discuss upgrade or usage discipline
before production begins, not after first overage.
```

**Remember:** HeyGen audio generation draws from ElevenLabs
character quota, not HeyGen credits.
Studio and API usage are tracked separately in the dashboard.
Show both meters to every new customer in week one.

---

## Pricing Quick Reference — By Persona Question

| Question | Persona | What They're Really Asking |
|----------|---------|---------------------------|
| "How does character counting work?" | Business Owner | "Is my team going to blow the budget?" |
| "What's our cost if we double volume?" | Business Leader | "Is this model defensible at scale?" |
| "Why are there two usage numbers?" | IT Administrator | "Is the billing system trustworthy?" |
| "Does this cover broadcast use?" | Legal | "Are we exposed?" |
| "What happens when we go over?" | Finance | "What's the worst-case invoice?" |

*Verify current pricing at elevenlabs.io/pricing before every meeting.*
*See Module 05 for the full pricing gotchas detail.*

---

## The Escalation Paths — Know Before You Need Them

| Question Type | Escalation Path |
|---------------|-----------------|
| Complex integration architecture | ElevenLabs technical team via account contact |
| Legal questions — consent, IP, liability | Customer's legal counsel + ElevenLabs account contact |
| Compliance documentation requests | Trust Center: compliance.elevenlabs.io (some docs require access request) |
| Prohibited use case questions | ElevenLabs account contact — do not answer independently |
| Professional Clone turnaround and process | ElevenLabs account contact |
| Enterprise pricing above Business tier | ElevenLabs enterprise sales |

---

## The Three Exits — For Any Difficult Question

*(Full framework in Module 07: The Honest Limitations Card)*

**Exit 0 — The Show Me (use first)**
> *"Could you walk me through exactly how you're planning
> to use voice in your workflow? Afterwards, we can confirm
> we're solving the right problem together."*

**Exit 1 — The Workaround**
> *"Here's how teams handle that today
> while the capability catches up."*

**Exit 2 — The Roadmap Frame**
> *"AI capability in this area is improving faster
> than almost anything else right now."*

**Exit 3 — The Honest Redirect**
> *"For that specific use case, human voice talent
> is still the right answer — and I'd rather tell you
> that now than have you discover it after you've
> built a workflow around the platform."*

*Exit 3 is the hardest to say and the one most likely
to earn a long-term customer.*

---

## The Closing Move

Before leaving any buying committee meeting,
name each persona's next step in the room:

> *"Before we wrap — [Name], for your team's workflow,
> the next step is X. [Name], on the ROI question,
> I'll follow up with Y. [Name], for the technical
> questions, let's schedule Z."*

Named next steps in the room create a shared record
of commitments and signal to the Business Leader
that working with ElevenLabs looks like this.

---

*ElevenLabs CSM Field Guide | CSM Pre-Meeting Quick Reference*
*ArchieCur Posse | Deputy Code edit pass v1*
*Cross-references: All nine modules + buyer-context.md*
*Verify time-sensitive content before every buyer conversation*
*Portfolio demonstration — ElevenLabs GTM Enablement*
