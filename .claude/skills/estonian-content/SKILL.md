---
name: estonian-content
description: Write or review Estonian (ET) text for Reeturid, the Traitors-style party game (index.html UI strings, TV host screen, rules, toasts, errors). Use whenever producing or editing ANY Estonian in this repo. Encodes the owner's voice, the locked game glossary and the review workflow, adapted from the Mealhive estonian-content skill.
---

# Estonian content for Reeturid

Reeturid is an Estonian party game: guests join on their phones, get a secret role, and vote at round tables while the TV runs the show. All UI is Estonian (`<html lang="et">`). The owner is a native speaker and reviews everything. Write short, lively, spoken Estonian that a room full of guests reads in two seconds, never translationese.

## Where ET content lives

- Everything is in `index.html`: player phone screens, the host/TV screen (`?host`), the rules panel, toasts and error messages (inline strings in the script). Grep the existing strings before adding a new one, and reuse the exact wording for the same concept.

## Locked game glossary (taken from the live UI, do not improvise)

| Concept | Estonian | Notes |
|---|---|---|
| Traitor / traitors | **reetur / reeturid** | partitive *reeturit*, plural partitive *reetureid* |
| Faithful (non-traitor) | **ustav / ustavad** | "jääd ustavaks" |
| Host | **saatejuht** | |
| Round table (vote) | **ümarlaud** | "Ümarlaud: keda pagendada?" |
| Vote someone out | **pagendama** (*pagendati*) | not *välja saatma* |
| Night kill | **mõrv / mõrvama** (*mõrvati*) | |
| Recruit a faithful | **värbamine / värbama** (*värvati*) | |
| Breakfast reveal | **hommikusöök** | |
| Night task | **öine ülesanne** | |
| Final vote | **lõpuhääletus** | |
| Shield | **kilp** (*kilbiga mängijat*) | |
| Out of the game, still plays team games | **kummitus** | |
| Team games | **meeskonnamängud** | |
| Prize pot | **kullapott** | "Kullapott kasvab iga mänguga." |

## Game-specific voice

- One player = **sina** ("Sind värvati reeturiks."). The traitors as a group, or the whole room on the TV = **teie / -te** ("Keda täna öösel mõrvate?", "Vaadake oma telefoni."). Both are informal.
- Drama is welcome on the TV and in reveals: ellipses and a single emoji are part of the live style ("Kõik tulevad hommikusöögile… peale ühe?", "👻"). Error messages stay plain and say what to do next ("Sellist mängu ei leitud. Kontrolli koodi.").
- Buttons: short verb, first person for agreement (**Nõustun**), imperative for actions (**Sulge hääletus**, **Lõpeta mäng**).
- Never reveal a role in text that could show on the TV or another player's phone; role words in shared screens must stay generic.

## Before writing, read

1. **`references/`** in this skill directory. Start with `notes-sentence-structure.md` (how native Estonian sentences are actually built, measured on 13,774 words of Delfi / Oma Maitse prose), then `notes-omamaitse-2026-07.md` (that register, distilled). Both were written for Mealhive, so their food examples are examples, not topic rules. The source PDFs stay in `rolandsade-mvp/meal-planner` under `.claude/skills/estonian-content/references/` and are not copied here.
2. **The Estonian already live in this repo** (see "Where ET content lives" below). The owner has reviewed it; match its words before inventing new ones.

## Sentence construction (measured, not guessed)

Earlier drafts read wrong not because of vocabulary but because they were **English syntax in Estonian words**: long sentences held together by relative pronouns and demonstratives.

| | Native | Generated drafts |
|---|---|---|
| Median words per sentence | **10** | 13.5 |
| Sentences with no comma at all | **49%** | 21% |
| Opening with a conjunction | **3%** | 12% |
| `see` per 1000 words | **4.0** | 16.9 |
| `mis` per 1000 words | **6.8** | 13.2 |

Hard rules:

1. **Break at the comma.** Past ~15 words, replace a comma with a full stop.
2. **Drop `see` as a dummy subject.** English needs "it is / this means"; Estonian does not. Name the thing.
3. **One `mis` clause per sentence, maximum.** Prefer a participle, a compound noun, or a second sentence.
4. **Do not open with Ja / Aga / Kui** for rhythm. `aga` outranks `kuid` in everyday register.
5. **Skip the signposts** (`seega`, `nii et`, `ja lõpuks`). Juxtapose instead.
6. **Use the impersonal for general truths**: *Suvel grillitakse palju.*
7. **Keep list items grammatically parallel.**

These medians describe feature prose. They are a floor to clear, not a target: a native speaker will happily write a 25-word sentence when the content needs it. Do not chop copy into telegram style either; a two-word consequence fragment reads unfinished.

## Voice and register

- **Informal "sina"** to one person, always. Never formal "Teie".
- Plural **"te / teie"** is right when addressing a group (a team, a household, all players): *Vaadake oma telefoni.* That is plural, not formal.
- Short UI strings. If an English source sentence is long, split it.
- **No em-dashes (—)** in user-facing copy. Use a comma, a period, parentheses, or "kuni" for ranges. Numeric ranges in tables and instructions may use an EN dash ("2–3 km"). The spaced Estonian mõttekriips (–) is fine where the owner approves it.
- Translate meaning, not words. If the Estonian reads like a calque, rewrite the sentence from scratch.

## General patterns the owner has corrected (from Mealhive reviews, apply everywhere)

- **Never transplant an English metaphor or phrasal verb.** "sülitab välja" (spits out) → *genereerib / koostab*; "istutada" (plant a few) → *korjata*; "elasid viies äpis" (lived in) → *olid viie rakenduse vahel laiali*; "ei rääkinud X-ga" (talked to) → *ei ühildunud*. Pick the verb an Estonian uses for the actual action.
- **No translated rhetorical framing.** "Vaata hoopis nii:", "Asi on selles:" read as translation. State the point, or use a plain label.
- **The "aus X" tic.** EN "honest comparison / honest list" → not *aus jutt, aus vaade*. Use *ausalt öeldes* at most once, or just say it.
- **A switch that is on:** use *sees / väljas* only for a literal toggle. A chosen option **on valitud**.
- **Confirm buttons:** a short first-person verb (**Kinnitan**, **Nõustun**) beats a translated imperative phrase.
- **Singular counts drop the "1"**: "Muudatus on ootel", not "1 muudatus on ootel". The numeral belongs in the plural form ("{n} muudatust", partitive singular after numbers).
- **Clipped EN contrasts** ("Plans it. Counts it roughly.") translated beat for beat stay cryptic. Say plainly what it does and what it does not.
- **"minu poolt"** (on my side / by me) is a calque; drop it.
- **"kaasas"** for "included" reads as packed in a bag; use **koos + comitative** ("koos ostunimekirjaga").
- **Vague "asi"** is filler; name the thing (*probleem, võimalus*).
- **"ka" goes before what it modifies**: "Soovid **ka** homseks lõunat?"
- **Case government**: *ära teenima* takes the total object (*koha ära teenib*); *saama* from a source takes the elative (*poest saab*); "X-i täis" with a plural sense takes partitive plural (*nuppe täis*); a point in time takes the adessive (*kolmapäeval*); time-noun compounds take the genitive (*kella viie paanika*).
- **"korralikult" is "properly"**, never an intensifier ("korralikult rohkem" → *oluliselt / tunduvalt rohkem*).
- **Drop qualifiers the sentence does not need.** Writing in Estonian for Estonians, "Eesti pood" is just *pood*.
- **Do not round off.** Generated ET reaches for a closing sentence that restates the opening. Native copy stops.
- **Two corrections in the same direction are not a rule.** Apply a correction where it was given, and ask before spreading it to cases that only look similar.
- **Numbers survive translation.** Script a check: every figure in the EN source must appear in the ET text, and the same figure must agree across every surface that repeats it.
- **Fluent slips are the last to go**: wrong verb pair (*valama* pours, *valguma* spreads by itself), wrong number agreement, a nominative written as partitive. Hunt these in the self-review.

## Workflow

1. Read the references and the live ET in this repo.
2. Write the full draft. For UI strings, keep lengths close to the EN source (layouts are shared).
3. Self-review each sentence: "would an Estonian say it this way, or is this English wearing Estonian words?" Rewrite the calques.
4. Label the output **first-pass, for owner review** unless the owner already reviewed that exact text. Never mark ET copy as final on your own authority.
5. When the owner corrects something, add it to this file (the glossary or the patterns list) in the same change, so it is never repeated. If the correction is general, also add it to the Mealhive skill, which is the master list.
