# Module 5: Pricing Gotchas
## What Your Customer Will Discover — Before You Do

---

### The Ambush Risk

Surprise invoices are the fastest path to churn. A customer who feels 
blindsided by a bill is not asking "what went wrong with our usage?" — 
they are asking "do I trust this vendor?" 

The CSM who walks a new customer through the usage dashboard before 
the first invoice arrives is doing retention work on day one. 
The CSM who doesn't will be managing an angry phone call on day 31.

---

### What You're Actually Selling at Scale vs. Business

**Scale ($330/mo)**
- [verify current character allotment — elevenlabs.io/pricing]
- Commercial license for generated audio
- Access to Voice Library
- Instant Voice Cloning
- API access

**Business ($1,100/mo)**
- [verify current character allotment — elevenlabs.io/pricing]
- Everything in Scale, plus:
- Professional Voice Cloning
- Higher concurrency limits
- Priority support
- Usage analytics

**The conversation that matters:** Help the buyer estimate their actual 
monthly character consumption *before* they sign — not after their first 
overage charge. Use the estimation worksheet in the CSM Ambush Prep card.

---

### What a "Character" Actually Costs You

ElevenLabs bills by character count. Here is what counts:

- Every letter counts ✓
- Every space counts ✓  
- Every punctuation mark counts ✓
- Numbers expand to words before counting — "2026" costs significantly 
  more than 4 characters; exact expansion varies by model ✓

**What surprises buyers:**

SSML tags are handled inconsistently. Some tags consume characters. 
Some don't. The behavior is not consistently documented and varies 
by model. A script heavy with `<break>`, `<emphasis>`, and `<phoneme>` 
tags may cost more than the raw word count suggests.

**The practical rule:** Tell buyers to estimate character consumption 
from word count using this rough conversion:

> Average English word ≈ 5 characters + 1 space = ~6 characters per word  
> 1,000-word script ≈ 6,000 characters  
> Divide your plan's allotment by 6 to estimate maximum finished words per month

That number sounds large until you factor in iteration.

---

### The Regeneration Cost — The One Nobody Warns You About

**This is the most common source of unexpected overage charges.**

Every generation attempt consumes characters from the plan quota — 
including attempts the user rejects, discards, or regenerates because 
the output wasn't quite right.

**The math nobody shows the buyer:**

A user fine-tuning a 3,000-character narration script:
- 15 regeneration attempts to dial in the voice settings
- 15 × 3,000 = **45,000 characters consumed in one afternoon**
- Against a monthly allotment, that is a significant fraction of the budget — 
  spent before a single approved file is produced

Non-technical users doing iterative fine-tuning don't understand 
they're paying per attempt. They discover it on the invoice.

**CSM talking point:**
> "Every generation attempt draws from your character quota — including 
> the ones you don't keep. Before your team starts tuning, finalize and 
> approve the script. Generate to publish, not to explore."  


**Recommended practice:** Voice tuning and slider exploration should 
happen on a 3–4 sentence test script, not on production content. 
Find the voice settings that work, document them, then apply them 
to the full script. Exploring with a 3,000-character narration 
burns quota. Exploring with 200 characters costs almost nothing.

**Recommended onboarding action:** In the first week, sit with the 
customer's primary operator and walk through one generation session. 
Show them the quota meter moving in real time. That five-minute demo 
prevents a support escalation.

---

### The Two Usage Numbers Problem

Teams using both ElevenLabs Studio (the browser interface) and the 
API see two separate character counts in their dashboard. These are 
tracked independently.

**What happens:**
- Studio usage appears in one location
- API usage appears in another
- Combined consumption is not surfaced as a single number by default
- First invoice arrives and the total is higher than either number alone

**The result:** The customer contacts support believing there is a 
billing error. There isn't — but the dashboard UX doesn't make this 
obvious.

**CSM action:** During onboarding, show every customer with API access 
where both usage meters live and how to read total consumption. 
Do this before they generate a single character in production.

---

### Overage Pricing — The Number That Changes the Conversation

When a customer exceeds their monthly character allotment, 
overage charges apply per 1,000 characters. The rate varies by tier.

**What matters for the CSM:**

Overage is consumption-based. A team that underestimates their 
monthly volume — or doesn't account for regeneration costs — 
can exceed their allotment significantly before the billing 
cycle closes.

**For finance teams forecasting costs:** Help them build a 
consumption model before signing. Variables to include:
- Average script length (in characters)
- Estimated number of scripts per month
- Average regeneration attempts per script (honest estimate: 5–10 
  for non-technical users in their first month)
- Studio vs. API split (tracked separately)

A finance team that builds the forecast owns the number. 
A finance team handed a surprise overage charge owns the vendor relationship problem.

*See also Module 3 (HeyGen, Condition 1) — audio generated inside
HeyGen AI Studio using a connected ElevenLabs voice draws from the
ElevenLabs character quota, not HeyGen credits. HeyGen does not
surface this consumption in its own dashboard.*

---

### Commercial License — What Each Tier Actually Covers

**[Business Owner] [Business Leader]**

Both Scale and Business tiers include a commercial license for 
generated audio. But "commercial license" has limits that matter 
for enterprise buyers.

**What is covered:**
- Using generated audio in commercial products, videos, and campaigns
- Distributing generated audio to end customers
- Monetizing content that includes ElevenLabs-generated audio

**What requires additional conversation:**
- Broadcast use (TV, radio, streaming at scale)
- Use cases involving sensitive contexts (legal proceedings, medical 
  contexts, news content)
- White-labeling ElevenLabs voice capability inside a product 
  you sell to others

**CSM rule:** If the buyer's use case involves embedding ElevenLabs 
voices inside a product they sell, or broadcasting at scale, 
get that conversation to ElevenLabs' commercial team before 
the contract is signed. Do not assume Scale or Business tier 
covers every commercial use case.

---

### The Voice Library License — A Different Agreement

**[Business Owner] [Legal]**

Voices in the ElevenLabs Voice Library are governed by individual 
voice talent agreements — not the standard ElevenLabs platform license. 
Each voice has its own usage terms.

**What this means in practice:**
- Some Library voices are licensed for personal use only
- Some are licensed for commercial use at additional cost
- Some have restrictions on use case (no political content, no adult content)
- The license terms are per-voice and must be reviewed individually

**The risk:** A team that builds a production workflow around a 
Library voice, then discovers mid-campaign that the license 
doesn't cover their use case, has a content problem and a 
legal problem simultaneously.

**CSM action:** For any Business tier buyer planning to use Voice 
Library voices in commercial production, confirm the specific 
voice license before workflow design begins. The only fully 
controlled voice asset is a cloned voice the customer owns.

---

### The One Thing to Do Before the First Invoice

Walk the customer's primary operator through the usage dashboard 
in week one. Show them:
1. Where Studio usage appears
2. Where API usage appears  
3. How the quota meter moves in real time during generation
4. Where overage alerts can be configured

That is 20 minutes of onboarding that prevents a churn conversation.

---

*ElevenLabs CSM Field Guide | Module 5: Pricing Gotchas*  
*ArchieCur + Sonnet 4.6 + Claude Code*
*Built April 2026 |  Portfolio demonstration — ElevenLabs GTM Enablement*
*Verify time-sensitive content before every buyer conversation*
*See csm-ambush-prep.md for estimation worksheet and persona quick reference*  
