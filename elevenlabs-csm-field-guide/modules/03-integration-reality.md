# Module 3: Third-Party Integration Reality
## What Connects, What Doesn't, and What to Say About It

---

### The Ambush Risk

The pitch is "use ElevenLabs voices everywhere."
The reality is "use ElevenLabs voices everywhere ElevenLabs
has a native integration — and build your own connector
everywhere it doesn't."

Most enterprise buyers arrive with an existing creative
and production stack. They assume a new platform will
slot into that stack. The CSM who lets that assumption
stand until the buyer tries to connect their tools
is the CSM managing a 90-day check-in complaint
instead of an expansion conversation.

Name the integration reality before the contract is signed.
That's not a limitation conversation — it's a trust-building one.

---

### Integration Status at a Glance

| Platform | Status | What That Means | Last Verified |
|----------|--------|-----------------|---------------|
| HeyGen | Native — with conditions | Full voice type support; credits, API permissions, and model selection have gotchas | April 2026 |
| Zapier | Partial | Native action exists; advanced use requires workarounds | April 2026 |
| Make | Partial | Basic TTS only native; advanced use requires HTTP module | April 2026 |
| Adobe (Premiere / Audition) | Workaround Required | No native integration; full manual round-trip | April 2026 |
| Descript | Workaround Required | No pipeline; ElevenLabs quality OR Descript workflow — not both | April 2026 |

*Last Verified dates reflect posse verification. Update each row
when integration status is confirmed changed. Do not let dates
run more than 90 days without a verification pass.*

---

### HeyGen

**What the buyer expects:** Use their cloned ElevenLabs brand voice
inside HeyGen avatar videos without manual file transfers.

**What's now possible:** Direct account connection via API key.
Once connected, ElevenLabs voices appear in HeyGen's voice
selector and can be assigned to any avatar slot or script track.

**Supported voice types:**
- Professional Voice Clones (PVC) ✓
- Instant Voice Clones (IVC) ✓
- Generated and Designed Voices ✓
- Voice Library voices added to "My Voices" collection ✓

This is a meaningful capability unlock — and it has
four conditions the CSM must know before the conversation.

---

**Condition 1: Credits Run on ElevenLabs, Not HeyGen**

**[Business Owner] [Finance]**

HeyGen does not use its own credits for ElevenLabs audio generation.
Every word generated inside HeyGen using a connected ElevenLabs voice
draws from the ElevenLabs character quota.

A buyer who doesn't know this will burn ElevenLabs quota
inside HeyGen and discover it on their next invoice —
not in their HeyGen dashboard.

**CSM talking point:**
> "When you use your ElevenLabs voice inside HeyGen,
> the characters are billed to your ElevenLabs account,
> not your HeyGen account. Your team needs to know that
> before they start generating at volume — otherwise
> the first sign something is off will be a quota
> alert they weren't expecting."

---

**Condition 2: API Key Permissions Must Be Correct**

**[IT Administrator]**

When creating the ElevenLabs API key for HeyGen integration,
Text-to-Speech access must be enabled. If "Restrict Key"
is turned on without all necessary permissions granted,
HeyGen returns an "Invalid API key" error — with no
explanation of why the key is invalid.

A non-technical operator handed this error has no clear
path to resolution without IT support.

**CSM action:** During integration setup, walk the IT
Administrator or technical lead through API key generation
with the correct permissions. Do not hand this step
to a non-technical operator without a documented checklist.

**Setup sequence:**
1. ElevenLabs profile settings → API Keys → generate key
2. Ensure Text-to-Speech access is enabled
3. If using "Restrict Key" — confirm all necessary permissions granted
4. HeyGen → Voices → + New Voice → Integrate 3rd Party Voice → ElevenLabs
5. Paste key → Confirm
6. Select which specific voices to import into HeyGen library

---

**Condition 3: Model Selection Affects Lip-Sync Quality**

**[Business Owner]**

HeyGen defaults to ElevenLabs' Multilingual v2 (or v3 where available)
for best lip-sync accuracy and voice quality. Turbo v2 is available
for faster English-only generation but may produce lower
lip-sync fidelity.

Buyers who have tuned their voice settings in ElevenLabs Studio
using a specific model should verify their preferred model
is available and selected inside HeyGen — the default
may not match their Studio production settings.

---

**Condition 4: Still-Image Avatar Lip-Sync**

**[Business Owner]**

Still-image avatar lip-sync with an ElevenLabs voice is now
supported natively within HeyGen AI Studio. No third platform required.
One caveat: editing the video in HeyGen AI Studio after AI lip-sync
or motion has been applied will cause you to lose the animation.
Treat the generated output as final — plan any script or timing
changes before generation, not after.

*Source: ArchieCur direct platform testing, April 2026.*

---

**The honest answer for HeyGen overall:**
> "HeyGen and ElevenLabs now connect directly —
> your cloned voice works inside HeyGen avatars
> without manual file transfers. There are three
> things to set up correctly before your team
> starts generating: the API key permissions,
> the model selection, and the credit tracking.
> Get those right in week one and the integration
> runs cleanly. Miss any of them and you'll get
> errors or surprise charges that look like
> platform problems but are actually setup problems."

---

### Zapier

**[Business Owner] [IT Administrator]**

**What the buyer expects:** Build an automation — generate audio
from a trigger, send it somewhere useful.

**What they discover:**

*The ephemeral URL problem:*
ElevenLabs' native Zapier action generates audio and returns
a file URL. That URL expires. Downstream Zaps that don't
immediately capture and store the file will break silently —
no error message, no failed Zap notification in some
configurations, just a broken link where audio should be.

Teams building "generate audio → post to Slack / save to Drive /
push to CMS" automations discover this only after a working
Zap starts producing dead links in production.

*The multi-step workflow gap:*
Generate → review → approve → publish is not achievable
in native Zapier without significant custom logic.
The native action is single-step: generate and deliver.
Enterprise content workflows are rarely single-step.

**The honest answer:**
> "The native Zapier integration handles straightforward
> generation well. Where it gets complicated is anything
> that requires the audio file to travel more than one hop,
> or any workflow with a review step between generation
> and delivery. Before your team builds on Zapier,
> let's map the actual workflow — the integration
> handles some of it natively and some of it needs
> a workaround."

**Workaround:** Add an immediate file-capture step after
every ElevenLabs generation action — save to Google Drive
or equivalent before the URL expires. Use the stored file
URL for all downstream steps. This adds one Zap step
and eliminates the silent failure risk.

---

### Make (formerly Integromat)

**[Business Owner] [IT Administrator]**

**What the buyer expects:** A native Make module that covers
ElevenLabs' full capability set.

**What they discover:**
- The native ElevenLabs module in Make covers basic TTS generation only
- Voice cloning, history management, fine-tuned voice selection,
  and any advanced capability requires the generic HTTP module
- HTTP module failures return raw API responses —
  error messages a developer can parse, not messages
  a non-technical content operator can act on
- Teams that hand a Make scenario to non-technical operators
  find it fragile in ways their operators can't diagnose

**The honest answer:**
> "Make works well for straightforward generation workflows.
> If your team needs anything beyond basic TTS — voice selection,
> cloning, history — they'll be working with Make's HTTP module,
> which requires more technical fluency to configure and maintain.
> Who on your team will own the Make integration long-term?
> That answer determines how far the native capability will take you."

**Workaround:** For non-technical operator teams,
keep Make scenarios to the native module only —
limit to basic TTS generation and route complex
voice work back to ElevenLabs Studio manually.
For technical teams, the HTTP module is capable;
build error handling and plain-language failure
notifications into the scenario from the start.

---

### Adobe (Premiere Pro / After Effects / Audition)

**[Business Owner]**

**What the buyer expects:** AI voice generation as part of the edit suite.
Generate narration, drop it into the timeline, iterate in place.

**What they discover:**
- Zero native integration between ElevenLabs and Adobe products
  as of early 2026
- Workflow is: generate in ElevenLabs Studio → download file →
  import to Adobe manually
- For iterative narration (generate, review, adjust script,
  regenerate), every iteration is a full round-trip
- Changes made in Adobe Audition do not sync back;
  script changes require full regeneration in ElevenLabs
- Production teams expecting "AI voice inside the edit suite"
  will find a file-transfer workflow instead

**The honest answer:**
> "Adobe and ElevenLabs don't talk to each other yet.
> The workflow is generate here, import there —
> which works fine for linear production where
> the script is locked before generation starts.
> For iterative workflows where narration and editing
> happen in parallel, the round-trip adds friction
> that's worth planning for."

**Workaround:** Lock the script before generating audio.
Any script change after generation means a new ElevenLabs session
and a new import. Teams that treat ElevenLabs as the final step —
not a parallel step — in the production process absorb
the round-trip without friction.

---

### Descript

**[Business Owner]**

**What the buyer expects:** ElevenLabs voice quality
inside Descript's AI editing workflow.

**What they discover:**
- Descript has its own AI voice cloning product (Overdub — branding may vary; the feature remains active as of early 2026)
- There is no native ElevenLabs → Descript pipeline
- Users who want ElevenLabs voice quality inside a Descript
  workflow must export audio files and import manually —
  losing Descript's AI editing features in the process
- The choice is binary: ElevenLabs voice quality,
  or Descript's workflow. Not both. Currently.

**The honest answer:**
> "Descript and ElevenLabs are solving adjacent problems
> with their own native solutions. If your team lives in Descript,
> they can use Overdub for voice work inside that environment.
> If ElevenLabs voice quality is the requirement —
> for brand voice cloning, for multilingual content,
> for expressiveness that Overdub doesn't reach —
> the workflow becomes: generate in ElevenLabs,
> bring the file into Descript. Pick the quality
> you need and build the workflow around that decision."

**Workaround:** Treat the two platforms as sequential,
not integrated. ElevenLabs generates the final audio asset.
Descript handles editing, transcription, and publishing.
The handoff is a file export. It's manual — and it's reliable.

---

### The Pattern Behind Every Integration Gap

Every integration listed above follows the same logic:

ElevenLabs generates excellent audio files.
What the buyer does with those files — in their edit suite,
their automation platform, their video tool, their CMS —
is not something ElevenLabs controls or connects to natively
beyond a small set of integrations.

This is not a failure of ElevenLabs' product.
It is the current state of a platform that does one thing
exceptionally well and is still building the connective
tissue to the rest of the creative stack.

**The CSM talking point that reframes every integration conversation:**

> "ElevenLabs is the best place to create voice assets.
> Where those assets live and how they travel through
> your production workflow is a separate design question —
> and it's one we should answer before you build,
> not after. What does your current production stack look like?"

That question turns an integration limitation conversation
into a workflow design conversation. That's the move.

---

### When to Bring in Technical Support

If a buyer's integration question involves:
- Custom API implementation connecting ElevenLabs to
  internal systems
- Enterprise SSO or data residency requirements
  affecting platform connectivity
- High-volume automation architecture
- Integration with platforms not covered in this module

That conversation has left CSM territory.
Get ElevenLabs' technical team involved before
workflow design is finalized — not after the buyer's
engineering team has already built something that doesn't work.

---

*ElevenLabs CSM Field Guide | Module 3: Third-Party Integration Reality*
*ArchieCur + Sonnet 4.6 + Claude Code*
*Built April 2026 |  Portfolio demonstration — ElevenLabs GTM Enablement*
*Verify time-sensitive content before every buyer conversation*
*HeyGen Condition 4 source: ArchieCur direct testing, April 2026*

