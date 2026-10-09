# Chapter Production Pipeline — The Luna Who Said No

> Integrated from three GitHub sources (research in `craft/research/`):
> - **webnovel-writer** (7.3k★, GPL-3.0): 6-step pipeline, 3 hard gates, "contract → commit → check ledger" discipline
> - **novel-skills** (MIT): 4-pass revision workflow, scene_card, Wound→Lie→Want→Need, voice_profile
> - **humanizer** (MIT): 26 AI-tell patterns from Wikipedia's "Signs of AI writing"
>
> One chapter ≈ 2000 words. Every chapter runs this pipeline. No exceptions.

---

## PHASE 0 — CONTRACT (5 min, before drafting)

Fill `scene-card-template.md`:
- **Goal**: what must this chapter accomplish (plot node from outline)
- **Conflict**: the active opposition in this chapter
- **Turning Point**: the exact moment things shift
- **Emotional Value Turn**: quantified (e.g., Hopeful +2 → Devastated −3)
- **Outcome**: entry state ≠ exit state (iron rule — if nothing changed, don't write it)
- **Hard constraints**: must-cover beats, forbidden zones, timeline anchor (countdown day), chapter-end hook

Then check `consistency-ledger.md`: unresolved foreshadowing, character physical states, world rules.

## PHASE 1 — DRAFT (write forward, no self-editing)

- Load `anti-ai-checklist.md` BEFORE writing (write it right the first time)
- Follow the scene_card beats; do not freestyle outside the contract
- Enforce `voice-profile.md`: sentence-length targets, per-character language markers
- Opening: enter conflict/risk/strong emotion within 200–400 words
- One chapter = one scene = one conflict

## PHASE 2 — 4-PASS REVISION

**Pass 1 — HUMANIZER** (strip AI tells)
- Scan against the 26 patterns (strongest first: staging, closers, triads, dashes)
- Zero signature AI vocabulary
- Asymmetry injection: paragraph lengths vary drastically
- Humanity test: *"Does this sound like an actual person wrote it from lived experience?"*

**Pass 2 — DIALOGUE** (subtext)
- Exposition scrub: no "As you know, Bob"
- Subtext matrix: spoken line vs. unspoken intent
- **Blind voice test**: cover the names — can you tell who's speaking? If not, fail.
- Tags → action beats; adverb tags deleted

**Pass 3 — PROSE** (line edit)
- Filter words (saw/felt/seemed) −80%
- Emotion labels → physiology + sensory
- Sentence rhythm: 3–8 word shorts alternate with 15–25 word longs
- Weak verb + adverb → strong verb (walked slowly → trudged)

**Pass 4 — CONTINUITY** (audit)
- Per scene: who present, carrying what, body state, what time
- World-rule check (pack law, silver, mate bond, countdown)
- Injuries and physical states carry over

## PHASE 3 — REVIEW GATES

Fill the scorecard in `chapter-review.md`:
- 7 dimensions, 1–10 each
- **Ship threshold**: nothing below 6; prose (anti-AI) never below 7
- Any blocking issue → fix before publish, no exceptions

Also run the **opening/hook rotation check**: same opening type 2 chapters in a row = warning, 3 = rewrite.

## PHASE 4 — COMMIT

Update `consistency-ledger.md`:
- New facts established this chapter
- Foreshadowing planted / advanced / paid off
- Character physical states (injuries, locations, emotional state)
- Countdown day advanced

## PHASE 5 — PUBLISH

- GoodNovel: Synopsis-transit method (never the title-bar method)
- Dreame: Blurb-transit method (≤5000 chars per block)
- Both platforms get identical text
- Verify paragraphs, `---` separators, first/last paragraphs before publishing
