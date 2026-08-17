# ⚖️ Statute — a UK law learning game

**Read the facts. Pick the provision that applies. Three lives.**

A single-file browser game that drills the skill law exams and practice both actually test: not *what does this Act say*, but *which provision governs these facts*. 21 everyday scenarios across five areas of UK law, each resolved by a real statutory provision, each linked to the text on legislation.gov.uk.

**Live:** _add your Vercel URL here_

---

## Why this exists

Most legal quiz apps test definitions — "what is consideration?" — which is the part students already revise well. The part that's harder, and the part an exam or a client actually presents, is the other direction: here is a messy set of facts, which section applies?

So every question in Statute starts with a situation, not a term:

> *A gym has you sign a waiver disclaiming all liability for injury, then a faulty machine injures you.*

Four options, one right answer, and when you answer you get the reasoning plus a link straight to the provision — [UCTA 1977 s.2](https://www.legislation.gov.uk/ukpga/1977/50/section/2), in that case, because liability for personal injury caused by negligence cannot be excluded no matter what was signed.

Three lives. Lose them and you reach the **Verdict**.

## Who it's for

Primarily **UK law students** in their first or second year, and anyone on a conversion course, who wants recall practice on the provisions that come up most.

Secondarily **non-lawyers** who want to know where they actually stand — the consumer, tenancy and road traffic questions are all situations people meet in real life.

It is **not** a revision substitute for reading the statute, and it is **not** legal advice. See *Limitations*.

## What it covers

21 provisions across five categories. Every one is real, current at the time of writing, and linked to the official text.

**Contract basics**

| Provision | The point it tests |
|---|---|
| [Misrepresentation Act 1967, s.2(1)](https://www.legislation.gov.uk/ukpga/1967/7/section/2) | Burden is on the maker of the statement to prove reasonable belief |
| [Unfair Contract Terms Act 1977, s.2](https://www.legislation.gov.uk/ukpga/1977/50/section/2) | Liability for personal injury from negligence cannot be excluded |
| [Consumer Rights Act 2015, s.62](https://www.legislation.gov.uk/ukpga/2015/15/section/62) | Unfair terms are not binding on the consumer |
| [Law of Property (Miscellaneous Provisions) Act 1989, s.2](https://www.legislation.gov.uk/ukpga/1989/34/section/2) | Land contracts must be in signed writing — a handshake is not enough |

**Consumer rights**

| Provision | The point it tests |
|---|---|
| [Consumer Rights Act 2015, s.9](https://www.legislation.gov.uk/ukpga/2015/15/section/9) | Goods must be of satisfactory quality |
| [Consumer Rights Act 2015, s.22](https://www.legislation.gov.uk/ukpga/2015/15/section/22) | Short-term right to reject, generally within 30 days |
| [Consumer Rights Act 2015, s.49](https://www.legislation.gov.uk/ukpga/2015/15/section/49) | Services must be performed with reasonable care and skill |
| [Consumer Contracts Regulations 2013, regs 29–30](https://www.legislation.gov.uk/uksi/2013/3134/regulation/29) | Cancellation rights on distance contracts |
| [Consumer Credit Act 1974, s.75](https://www.legislation.gov.uk/ukpga/1974/39/section/75) | Card issuer is jointly liable on qualifying purchases |

**Tenancy & property**

| Provision | The point it tests |
|---|---|
| [Housing Act 2004, s.213](https://www.legislation.gov.uk/ukpga/2004/34/section/213) | Deposits must go into an authorised scheme within 30 days |
| [Landlord and Tenant Act 1985, s.11](https://www.legislation.gov.uk/ukpga/1985/70/section/11) | Landlord's repairing obligations |
| [Protection from Eviction Act 1977, s.1](https://www.legislation.gov.uk/ukpga/1977/43/section/1) | Unlawful eviction and harassment — arrears are no defence |
| [Party Wall etc. Act 1996, s.1](https://www.legislation.gov.uk/ukpga/1996/40/section/1) | Notice before building on the line of junction |

**Road traffic**

| Provision | The point it tests |
|---|---|
| [Road Traffic Act 1988, s.5](https://www.legislation.gov.uk/ukpga/1988/52/section/5) | Over the prescribed limit — no accident required |
| [Road Traffic Act 1988, s.170](https://www.legislation.gov.uk/ukpga/1988/52/section/170) | Duty to stop, give details, and report |
| [Road Traffic Act 1988, s.143](https://www.legislation.gov.uk/ukpga/1988/52/section/143) | Using a vehicle without insurance |
| [Road Vehicles (Construction and Use) Regulations 1986, reg 110](https://www.legislation.gov.uk/uksi/1986/1078/regulation/110) | Hand-held mobile phones, and the narrow exceptions |

**Data protection**

| Provision | The point it tests |
|---|---|
| [Data Protection Act 2018, s.170](https://www.legislation.gov.uk/ukpga/2018/12/section/170) | Unlawfully obtaining personal data — a nosy look can suffice |
| [Data Protection Act 2018, s.173](https://www.legislation.gov.uk/ukpga/2018/12/section/173) | Altering data to prevent disclosure after a subject access request |
| [UK GDPR, Article 15](https://www.legislation.gov.uk/eur/2016/679/article/15) | Right of access |
| [UK GDPR, Article 17](https://www.legislation.gov.uk/eur/2016/679/article/17) | Right to erasure, and its exceptions |

## How it's built

One file. `statute.html`, about 1,000 lines, containing the markup, styles, question bank and game logic.

- **No framework** — no React, no build step, no bundler, no `npm install`
- **No backend** and no API calls
- **No dependencies** except Google Fonts
- **No storage at all** — game state is in memory only, deliberately (see below)

To run it, open `statute.html` in a browser. That is the whole setup.

The design goal was that the file should still work, unchanged, in ten years. Anything that needed installing, building, or hosting would have failed that test.

## Limitations

- **This is not legal advice.** Every answer is a compressed summary of a provision written to be *learnable*, not to be relied on. The links go to the actual text for a reason.
- **The law moves.** Provisions are summarised as at the time of writing. Anything here could be amended, repealed or reinterpreted; check legislation.gov.uk, which is linked on every question.
- **Jurisdiction is mixed.** Consumer and data protection provisions are broadly UK-wide; the road traffic provisions are Great Britain; Protection from Eviction, the Housing Act deposit rules and the Party Wall Act are England and Wales. The game does not currently flag which is which.
- **21 questions is a small bank.** You will start seeing repeats quickly.
- **Nothing is saved.** Close the tab and your progress is gone — a deliberate choice to keep the file dependency-free, but it does rule out any real revision schedule.
- **No explanation of the wrong answers.** You learn why the right option is right, but not why the other three are wrong, which is often where the useful distinction sits.

## What I'd improve next

In the order I would actually do them:

1. **Say when the law was checked.** A dated "provisions accurate as at …" line. For legal content that is the single most important missing piece — a summary with no date is a summary you cannot trust.
2. **Label the jurisdiction on each question.** Cheap to add, and it stops the game quietly teaching that a Great Britain road traffic offence and an England-and-Wales housing rule are the same kind of thing.
3. **Explain the distractors.** One line per wrong option on why it doesn't apply. This is where most of the learning actually is.
4. **Grow the bank and track weak categories,** so a session can focus on the areas you keep getting wrong.
5. **Save progress and add spaced repetition.** This means accepting `localStorage`, which is a real trade against the no-dependencies goal — worth it, but worth being deliberate about.
6. **Add a meta description and social preview tags.** There are none, so the link currently shares as a bare URL.

## How this was built, honestly

I'm a second-year International Law student without a computer science background, and this was built with heavy AI assistance — the code was largely AI-written from my specifications.

What is mine is the legal content and the framing: choosing provisions that come up in real situations rather than the ones that are easiest to quiz, writing each scenario so the facts genuinely point to one section, and getting every citation right and linked to the primary source. If you want to check whether I understand this material, read the question bank and the *Limitations* section above rather than the JavaScript.

## Licence

MIT.
