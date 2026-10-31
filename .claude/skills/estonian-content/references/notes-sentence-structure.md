# How Estonian food-media sentences are actually built

Measured, not guessed. Owner asked for this on 2026-07-29 after flagging
"Ja lõpuks see, et…" as something Estonians do not say.

**Corpus**: the 16 owner-supplied PDFs in this folder (Oma Maitse food
features and recipes, plus three Ärileht news pieces), 13,774 words,
940 editorial sentences after stripping portal chrome.
**Compared against**: my own four ET articles, 264 sentences.

Reproduce with `pdftotext -layout`, join wrapped lines into paragraphs,
strip the "Kuula artiklit / FOTO / SOOVITAME / SISUTURUNDUS" furniture,
then split on sentence-final punctuation.

## The measured profile

| | Native corpus | My ET articles |
|---|---|---|
| Median words per sentence | **10** | 13.5 |
| Sentences of 8 words or fewer | **39%** | 20% |
| Sentences of 16 to 25 words | **15%** | 29% |
| Sentences with **no comma at all** | **49%** | 21% |
| Sentences opening with a conjunction | **3%** | 12% |
| `see` per 1000 words | **4.0** | 16.9 |
| `mis` (relative pronoun) per 1000 words | **6.8** | 13.2 |
| impersonal `-takse` per 1000 words | **3.7** | 2.1 |
| `ning` per 1000 words | **5.7** | 3.4 |

Read those four bold-vs-mine rows together and the diagnosis is one
thing: **I write English syntax with Estonian words.** Long sentences,
held together by relative pronouns and demonstratives, where Estonian
uses two short independent ones.

## The five specific habits to break

### 1. Half of all sentences carry no comma

Nearly half the native corpus is a single clause with a full stop.
"Želee sobib nii saiale määrimiseks, tordi vahele, punaveinikastmesse
kui ka lihamarinaadi." is a list, not a subordinate structure. "Nii saad
valmis koogi paberi abil vormist välja tõsta." is the whole thought.

Mine, by contrast, run 20+ words with two or three subordinate clauses.
Fix: when a draft sentence passes ~15 words, look for the comma and put
a full stop there instead.

### 2. `see` is 4x overused

English requires a dummy subject ("it is", "this means", "that is why").
Estonian frequently drops it or repeats the noun. My prose is full of
"See on…", "See ei ole…", "see ongi…", "arvab maha selle, mis…".

- Weak: *See on ainus mõistlik valik olukorras, kus…*
- Better: *Ainus mõistlik valik olukorras, kus…* or name the thing.
- Weak: *arvab maha selle, mis sul sahvris juba olemas on*
- Better: *arvab maha kodus olemasoleva* (nominalise, drop the clause)

### 3. `mis` relative clauses are 2x overused

This is the heaviest single tic. Real example from my draft, 29 words:

> AI, mis genereerib nädala retsepte teadmata, mis sul juba kapis on,
> saadab sind ostma asju, mis sul olemas on, ja ei märka poolikut
> kapsapead…

Three `mis` clauses in one sentence. Estonian has better tools:

- **Participle instead of a relative clause**: *riknemise äärel olev
  jogurt* rather than *jogurt, mis on riknemise äärel*. The corpus is
  full of these (`-tud` 169 hits, `-nud` 113, `-des` 76).
- **Compound noun** instead of a defining clause: *kokkamisõhtu*,
  *sügavkülmapank*, *ostunimekiri*. Estonian compounds where English
  needs "a night when you cook".
- **A second sentence.** Cheapest and usually best.

### 4. Only 3% of sentences open with a conjunction

I do it 12% of the time, because English prose uses "And…" / "But…" for
rhythm. In Estonian it reads as a fragment. Note also **`aga` (31) beats
`kuid` (14)** in this corpus: the food-media register prefers the spoken
contrastive. `ning` is common (64 hits) purely to avoid repeating `ja`
inside a list.

### 5. Explicit logical connectors are rare

Counts across 13,774 words: `seega` 3, `seetõttu` 2, `nii et` 0,
`sellepärast` 1, `esiteks/teiseks/kolmandaks` 1 each. English expository
prose signposts constantly ("therefore", "which means that", "and
finally"). Estonian juxtaposes and lets the reader connect.

**`ja lõpuks` occurs zero times in the corpus.** The owner's instinct was
right and the corpus confirms it. Same for enumerating a list in prose
with "and finally the fact that…": if the items are a list, make them a
list, and keep every item the same grammatical shape (all noun phrases:
*Kogused.* / *Ostunimekirja koostamine.* / *Plaani meelespidamine.*).

## What the corpus does that I should do more

- **Impersonal voice for general truths**: *Suvel grillitakse palju*,
  *Kimchit valmistatakse ka redisest*, *Poes pakutakse…*. Underused by
  me at 2.1 vs 3.7 per 1000. It is the natural way to state what people
  generally do, and it avoids inventing a subject.
- **Colon to introduce, then a bare list.** 10% of native sentences use
  a colon. It replaces a subordinate clause entirely.
- **Concrete nouns as sentence subjects**, not abstractions. *Hooaeg teeb
  ülejäänu.* *Mälu ostab asju.* Short, active, physical.
- **Dashes for glossary-style definitions**: *Gochugaru – kuivatatud
  Korea tšillist valmistatud helbed või pulber.* (An en dash in that
  position is native convention; the banned character is the em dash.)

## Working targets for an ET article

Aim to land inside the native band, not merely closer to it:

- [ ] Median sentence length **10 to 12 words**
- [ ] At least **35%** of sentences with no comma
- [ ] At most **4%** opening with a conjunction
- [ ] No sentence with more than **one** `mis` clause
- [ ] `see` used only where it carries real reference, never as a dummy subject
- [ ] Zero instances of `ja lõpuks`, `nii et` as a discourse marker, or prose enumeration that a list would do better
