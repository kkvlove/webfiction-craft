# webfiction-craft

A production pipeline for serialized web fiction (English web novels: GoodNovel, Dreame/StaryWriting, WebNovel).

One chapter per day: **scene card → draft → 4-pass revision → 7-dimension scorecard → fact commit → publish**. Every phase leaves file evidence — no phase is "done" without its artifact on disk.

## The pipeline

```
Phase 0  Scene card        → craft/scene-card-ch{NN}.md
Phase 1  Draft (~1700w)    → book1-ch{NN}-draft.md        (anti-ai-checklist first)
Phase 2  4-pass revision   → book1-ch{NN}.md             (humanizer → dialogue → prose → consistency)
Phase 3  Scorecard gate    → craft/review-ch{NN}.md       (7 dims; prose ≥ 7 to ship, no dim < 6)
Phase 4  Fact commit       → consistency-ledger.md        (new facts / threads / body states)
         Publish           → GoodNovel + Dreame/StaryWriting
```

See [PIPELINE.md](PIPELINE.md) for the full procedure.

## Files

| File | What it is |
|---|---|
| [PIPELINE.md](PIPELINE.md) | The master procedure: contract → draft → 4 revisions → review gate → commit → submit |
| [anti-ai-checklist.md](anti-ai-checklist.md) | 26 AI-tell patterns to avoid (from q-qp-p/humanizer) |
| [chapter-review.md](chapter-review.md) | 7-dimension scorecard (novel-skills manuscript-evaluator style) |
| [scene-card-template.md](scene-card-template.md) | Blank scene card: goal / conflict / turning point / emotional turn / outcome |
| [consistency-ledger-template.md](consistency-ledger-template.md) | Blank plot bible: dossiers, world rules, thread tracker, chapter fact log |
| [voice-profile-example.md](voice-profile-example.md) | Worked example of a quantified book voice (from ns-voice-style-analyser) |
| [examples/scene-card-example.md](examples/scene-card-example.md) | Worked example: a filled scene card from a real chapter |
| [research/](research/) | Deep-dive reports on the three source projects |

## The hard rule

**No file evidence = the phase didn't happen.** A scorecard that exists only as a claim ("I scored it 8/8/8…") is watering down the process. The review file must exist on disk with all 7 dimensions scored before anything ships.

## Sources & attribution

This system synthesizes methodology from three open-source projects (see [research/](research/) for full reports):

- [lingfengQAQ/webnovel-writer](https://github.com/lingfengQAQ/webnovel-writer) (7.3k★, GPL-3.0) — contract → draft → multi-pass revision → review gate → ledger commit pipeline
- [leemain88/novel-skills](https://github.com/leemain88/novel-skills) (MIT) — 15-skill English fiction library (voice analysis, character design, manuscript evaluation)
- [q-qp-p/humanizer](https://github.com/q-qp-p/humanizer) (MIT) — 26 AI-writing-tell patterns

All prose, templates, and checklists here are original expression. Methodological inspiration is credited above; no source code was copied.

## License

MIT — see [LICENSE](LICENSE).
