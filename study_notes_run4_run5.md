# Study Notes Workflow — RUN 4 & RUN 5 (Integrated, All 3 Courses)

**Sources combined in both runs:**
1. *Entrepreneurship: Theory, Process, Practice* (Frederick & Kuratko) — Chapters 1–5
2. *Unit 4: Transfer Function Models* (PRCCHB3, Process Control 3B)
3. *Learning Unit 1: Environmental Laws and Regulations* (ENVCHB3, Environmental Engineering 3B)

**Note on integration:** Transfer Function Models is a self-contained mathematical/technical topic with no substantive conceptual overlap with the other two courses, so it is carried through each step as its own track. Entrepreneurship (especially Ch.3–4: environmental economics, ecopreneurship, ethics) and Environmental Law (Triple A framework, SA regulatory hierarchy, environmental ethics/compliance) *do* share real thematic ground — both deal with environmental regulation, sustainability trade-offs, ethical/legal decision-making, and risk — so those two are cross-referenced explicitly where genuinely connected, not just placed side by side.

RUN 4 and RUN 5 are two independent full passes through the same four steps, applied to the same combined material — RUN 5 is not a copy of RUN 4; it re-derives the synthesis and source-check independently as a consistency/variance check, per your instruction to repeat the process.

---
---
---

# RUN 4

# SOURCE EXTRACTION — RUN 4

## Track A: Entrepreneurship (Chapters 1–5) — condensed

- **Ch.1**: Entrepreneur vs. small-business owner vs. social entrepreneur; macro/micro schools of thought; gazelles; national culture (Lee & Peterson's six dimensions); historical evolution of entrepreneurship.
- **Ch.2**: ~16 entrepreneurial characteristics; "dark side" traits; four risk types (financial, career, family/social, psychic); Entrepreneurship = f(entrepreneur); Model of Entrepreneurial Motivation (PC/PE/PG/BE); Kalish's gap-filling theory (business vs. social entrepreneurs).
- **Ch.3**: Positive/negative externalities; tragedy of the commons; cap-and-trade; peak resource theory; mitigation vs. adaptation; social discount rate; eight "entrepreneurial ecology" frameworks (natural capitalism, cradle-to-cradle, economic gardening, Natural Step, industrial metabolism, natural advantage of nations, lean/Muda, ecology of commerce); Stern Review cost figures (1% GDP action vs 5–20% GDP inaction).
- **Ch.4**: Ethics vs. morals; ethical/legal 2×2 matrix; morally questionable acts typology (non-role, role failure, role distortion, role assertion); four ecopreneur types (Innovative Opportunist, Visionary Champion, Ethical Maverick, Ad Hoc Enviropreneur); three social-enterprise models; UN Norms on TNC responsibilities; disadvantaged-entrepreneur barrier categories.
- **Ch.5**: Innovation = inventive + entrepreneurial process (Hindle); eight sources of innovative ideas; four-phase creative process; four innovation types (invention/extension/duplication/synthesis); disruptive technology (Christensen); Milker's sustainable product-design guidelines.

## Track B: Transfer Function Models — condensed

- Transfer function G(s) = Y(s)/X(s), zero initial conditions, SISO.
- Deviation variables (T′ = T − T̄, etc.) zero the initial-condition term in Laplace space.
- Derivation recipe: ODE → steady-state subtraction → deviation variables → Laplace transform → rearrange → isolate individual TFs by holding other inputs constant.
- Stirred-tank example: T′(s) = [K₁/(τs+1)]Tᵢ′(s) + [K₂/(τs+1)]Q′(s); K₁=1, K₂=1/(wC), τ=ρV/w.
- Worked answer: T(t) = 100 + 15(1 − e^(−2t)).
- Additive property (parallel inputs sum) and multiplicative property (series TFs multiply); both rest on the Principle of Superposition (linearity).

## Track C: Environmental Law — condensed

- Triple A framework: Appropriate (Technical 50% + Environmental 50% = 25% total), Applicable (Institutional 50% + Legal 50% = 25% total), Affordable (Financial 100% = 50% total).
- "Systems approach": technology must satisfy technical, environmental, institutional, legal, and financial systems simultaneously.
- SA regulatory hierarchy: Constitution (ss.22–24) → Acts (Professional Regulation/Procurement; Environmental & Resource incl. NEMA + SEMAs; Health & Safety; IP & Commercial) → Regulations (e.g., "polluter pays") → professional codes (ECSA + built-environment counterparts) → municipal by-laws → SANS/ISO standards + common law.
- Pienaar v ECSA: deregistration mid-investigation does not defeat ECSA's disciplinary jurisdiction (s.20(3) Engineering Profession Act); ECSA's mandate is not geographically limited.
- Medupi/Kusile (Case A) and Shell (Case B): retrospective Triple A scoring exercises (Task A fact extraction, Task B scoring, Task C reflection).

## Cross-course connection: Environmental economics/ethics (Entrepreneurship Ch.3–4) ↔ Environmental Law

| Concept in Entrepreneurship (Ch.3–4) | Corresponding concept in Environmental Law | Nature of the link |
|---|---|---|
| Negative externality / tragedy of the commons | "Polluter pays" principle (NEMA Regulations) | Both are mechanisms for internalising the cost of environmental harm that would otherwise be borne by third parties/society. |
| Cap-and-trade (emissions trading) | NEMAQA (Air Quality Act) / Minimum Emission Standards, Carbon Tax Act | Both are market-and-regulation-based tools for pricing/limiting emissions; Medupi/Kusile's real-world emission-standard postponement disputes are a live example of the tension between economic pressure and environmental compliance. |
| Ethical/legal 2×2 matrix (ethics ≠ legality) | Codes vs. common law (compliance with a code does not remove common-law negligence liability) | Both frameworks explicitly separate "is it legal" from "is it right/safe," and both note that satisfying one does not guarantee satisfying the other. |
| Ecopreneur typology (economic vs. sustainability orientation) | Triple A "Appropriate" criterion (Technical + Environmental) | Both frameworks force a trade-off/joint evaluation between purely economic performance and environmental fit. |
| Mitigation vs. adaptation | Environmental Impact Assessments / rehabilitation & decommissioning strategy (part of "Appropriate–Environmental") | Both distinguish proactive impact-reduction from reactive/end-of-life management of environmental consequences. |
| Eight entrepreneurial-ecology frameworks (e.g., natural capitalism, cradle-to-cradle) | "Appropriate–Environmental" sub-criterion in Triple A | Both are lenses for judging whether an economic activity is environmentally sound, just applied at different scales (firm strategy vs. project approval). |

**Likely assessment points (integrated)**
- Explain how the "polluter pays" principle in South African environmental law operationalises the economic concept of a negative externality.
- Compare the ethical/legal 2×2 matrix (Entrepreneurship Ch.4) with the codes/common-law distinction in Environmental Law — in both cases, legality and ethics/liability are shown to be separate axes.
- Use the Triple A framework to evaluate an ecopreneur venture from Ch.4 (e.g., an Ad Hoc Enviropreneur) as if it were a project proposal.
- (Transfer Functions, standalone) Derive a transfer function from a first-principles ODE using deviation variables.

---
---

# DRAFT STUDY NOTES — RUN 4

**Entrepreneurship (Ch.1–5):** Entrepreneurship is framed as a value-creating, risk-bearing process distinct from small-business ownership, driven by psychologically distinct individuals (Ch.1–2) who operate within — and are shaped by — economic and environmental constraints (Ch.3), ethical boundaries (Ch.4), and opportunities for innovation (Ch.5). A recurring thread across Chapters 3 and 4 is that markets alone do not price environmental harm correctly (externalities, tragedy of the commons), which creates both a policy problem (addressed by mechanisms like cap-and-trade) and a business opportunity (addressed by ecopreneurs and social entrepreneurs who deliberately internalise environmental or social costs that the market ignores).

**Transfer Function Models:** A parallel, unrelated technical thread: dynamic process models can be re-expressed in the Laplace domain as transfer functions, using deviation variables to eliminate initial-condition complexity. The stirred-tank heating example demonstrates the full derivation pipeline and shows how individual input-output relationships (Q→T, Tᵢ→T) can be isolated and then recombined via the additive property, reflecting the linearity (superposition) of the underlying model.

**Environmental Law:** Provides the regulatory and decision-making counterpart to Entrepreneurship's environmental-economics content: where Ch.3 explains *why* environmental externalities are a market failure, Environmental Law explains *how* South African law actually forces their internalisation in practice (NEMA and its SEMAs, the "polluter pays" Regulations, and Minimum Emission Standards). The Triple A framework offers a formal, weighted way to evaluate whether a project (like Medupi/Kusile) is simultaneously technically sound, environmentally appropriate, institutionally and legally applicable, and financially affordable — which is structurally analogous to how an ecopreneur (Ch.4) must simultaneously satisfy economic and sustainability orientations. The Pienaar case shows that legal/professional accountability structures (ECSA) are robust to attempts to evade them — a theme that resonates with Ch.4's point that legality and ethics are not the same axis, and that acting "legally" (e.g., cancelling registration) does not exempt one from a broader accountability framework.

**Integration point:** A student preparing for exams across all three courses should notice that "market failure requiring regulatory correction" is a genuinely shared idea between Entrepreneurship Ch.3 (externalities, cap-and-trade) and Environmental Law (polluter pays, NEMAQA emission standards) — the same underlying economic logic, taught from two different angles (business/economics theory vs. applied SA law). Transfer Function Models remains conceptually independent and should be studied as its own self-contained technical skill.

---
---

# SOURCE CHECK — RUN 4

**1. Missing concepts**
- The condensed Track A/B/C summaries above deliberately omit most numerical data (GEM statistics, water-footprint figures, Medupi cost figures, the exact stirred-tank exercise numbers) that were already fully captured in Runs 1–3. *Correction*: this is intentional compression to avoid pure duplication across four already-completed extraction passes; Final Notes below references back to the original Run 1/2/3 files for full numerical detail rather than re-listing everything, and flags this explicitly so it isn't mistaken for an oversight.

**2. Missing definitions**
- None beyond what's already defined in Runs 1–3; no new terms are introduced by the act of integration itself.

**3. Missing formulas**
- The Transfer Function track (Track B) omits the full derivation algebra (equations 1–13) present in Run 2's Source Extraction, since Track B is condensed here. *Correction*: Final Notes retains the two most exam-relevant formulas (the general TF form and the worked answer) and directs the reader to Run 2 for the complete derivation.

**4. Unsupported claims**
- The cross-course connection table claims a "genuine substantive link" between six pairs of concepts. On review, each pairing is defensible directly from source material already extracted (e.g., "polluter pays" ↔ negative externality is a standard, source-supported economic/legal parallel; both appear independently in Ch.3 and in the Environmental Law regulatory-framework slides). No claim in the table introduces information not present in the underlying sources.

**5. Incorrect interpretations**
- None found on review — all condensed statements in Track A/B/C remain consistent with the fuller Source Extractions already validated in Runs 1–3's own Source Check steps.

**6. Oversimplifications**
- Track C's Triple A summary omits the explicit worked example weighting numbers (25%/25%/50%, with sub-splits) shown as a table in Run 3 — stating them only in prose here risks losing the visual clarity that helps memorisation. *Correction*: Final Notes reproduces the Triple A table in full rather than only in prose.
- The integration "Likely assessment points" list undersells that Transfer Function Models genuinely has no thematic link to the other two courses — a student should not go looking for one. *Correction*: Final Notes states this explicitly as a standalone note, not just implied by track separation.

**7. Changes in terminology that could alter meaning**
- None identified — all terms (externality, polluter pays, ecopreneur, Triple A, deviation variable, transfer function) are used identically to their definitions in the original per-course extractions.

---
---

# FINAL STUDY NOTES — RUN 4

**1. Topic:** Integrated review across three courses — (A) Entrepreneurship Ch.1–5, with emphasis on environmental economics and ethics (Ch.3–4); (B) Transfer Function Models (Process Control); (C) Environmental Law and the Triple A decision framework — highlighting genuine conceptual overlap between (A) and (C), with (B) treated as an independent technical track.

**2. Key definitions**
- *Negative externality* (Entrepreneurship Ch.3): uncompensated cost imposed on a third party by economic activity.
- *Polluter pays principle* (Environmental Law): the entity causing environmental harm must remediate it — South African law's practical enforcement of the externality problem.
- *Tragedy of the commons* / *cap-and-trade* (Ch.3): shared-resource over-exploitation, and the market mechanism (tradeable emission permits) used to correct it.
- *Ethical/legal 2×2 matrix* (Ch.4) and *codes vs. common law* (Env. Law): both frameworks separate legality from ethics/liability — satisfying one does not guarantee the other.
- *Ecopreneur typology* (Ch.4) and *Triple A "Appropriate" criterion* (Env. Law): both require joint evaluation of economic/technical viability and environmental fit.
- *Transfer function*: G(s) = Y(s)/X(s), Laplace-domain ratio of output to input, zero initial conditions (standalone; see Run 2 for full definitions of deviation variable, process gain, time constant).

**3. Main concepts**
- **Shared logic across (A) and (C)**: markets do not automatically price environmental harm; correcting this requires either voluntary business action (ecopreneurship, natural capitalism, cradle-to-cradle — Ch.3–4) or regulatory force (NEMA's SEMAs, Minimum Emission Standards, the polluter-pays Regulations — Env. Law). Medupi/Kusile is a real case where this tension plays out directly: emission-standard postponement disputes are the Environmental Law course's live example of the same market-vs-regulation tension that Ch.3 explains in theory.
- **Shared logic on ethics vs. legality**: both courses independently teach that legal compliance and ethical/professional accountability are separate questions — Ch.4's 2×2 matrix and the Pienaar case (where cancelling a legal registration did not remove ethical/professional accountability) make structurally the same point from different angles.
- **Independent technical track (B)**: transfer function derivation (ODE → deviation variables → Laplace → rearrange) and TF properties (additive, multiplicative, superposition) — no conceptual bridge to (A) or (C); study as a self-contained skill.

**4. Important formulas**
- Triple A weighting table (Env. Law):

| Triple 'A' Criteria | Technical | Environmental | Institutional | Legal | Financial | Total weighting |
|---|---|---|---|---|---|---|
| Appropriate | 50% | 50% | – | – | – | 25% |
| Applicable | – | – | 50% | 50% | – | 25% |
| Affordable | – | – | – | – | 100% | 50% |

- Transfer function general form: T′(s) = [K₁/(τs+1)]Tᵢ′(s) + [K₂/(τs+1)]Q′(s); worked example result: T(t) = 100 + 15(1 − e^(−2t)). *(Full derivation: see Run 2.)*
- No formula bridges (A) and (C) directly — the link is conceptual/economic, not mathematical.

**5. Processes/steps**
- Applying Triple A to an ecopreneurial venture (integration exercise): (1) classify the venture using Ch.4's ecopreneur typology; (2) score its Technical, Environmental, Institutional, Legal, and Financial sub-criteria per the Triple A table; (3) compute a weighted decision score; (4) compare against the venture's real-world outcome, as the course does for Medupi/Kusile.
- Transfer function derivation recipe (standalone, unchanged from Run 2): ODE → steady-state subtraction → deviation variables → Laplace transform → algebraic rearrangement → isolate individual TFs.

**6. Examples**
- Medupi/Kusile's Minimum Emission Standards postponement disputes = real-world instance of the externality/cap-and-trade tension taught abstractly in Ch.3.
- Pienaar v ECSA = real-world instance of the "legal ≠ ethical/accountable" separation taught abstractly via Ch.4's 2×2 matrix.
- Stirred-tank heating system (Transfer Functions) = standalone worked technical example, no thematic counterpart in the other two courses.

**7. Important points to remember**
- Two of the three courses (Entrepreneurship Ch.3–4 and Environmental Law) genuinely reinforce each other on environmental-economics and ethics/legality themes — use one to help recall the other.
- The third course (Transfer Function Models) is a purely technical, self-contained skill with no conceptual bridge to the other two; do not force a connection when studying it.
- When an exam question mixes "is this legal" and "is this ethical/right," both courses have taught you the same underlying answer: these are different axes, and satisfying one does not satisfy the other.

**8. Potential test questions**
- Explain how the polluter-pays principle (Environmental Law) operationalises the concept of a negative externality (Entrepreneurship Ch.3).
- Using the Triple A framework, evaluate a hypothetical Ad Hoc Enviropreneur venture (Ch.4) as if it were a project proposal — score each sub-criterion and reach a weighted decision.
- Compare the ethical/legal 2×2 matrix (Ch.4) to the "codes vs. common law" distinction in Environmental Law — what do both frameworks say about the relationship between legality and accountability?
- (Standalone) Derive the transfer function for a single-input, single-output tank system using deviation variables, and state its process gain and time constant.

---
---
---

# RUN 5

*(Independent second pass — re-derived rather than copied from Run 4, per instruction to repeat the process as a consistency check.)*

# SOURCE EXTRACTION — RUN 5

## Track A: Entrepreneurship — re-derived condensation
Re-scanning the same five chapters with fresh eyes, the material organises naturally around **four recurring tensions** rather than chapter boundaries:
1. **Individual vs. system** (Ch.1–2): is entrepreneurship explained by the person (traits, motivation) or by external forces (macro schools, culture, economy)?
2. **Profit vs. mission** (Ch.1, 4): business entrepreneurs vs. social entrepreneurs vs. ecopreneurs — three variants of the same profit/mission trade-off.
3. **Market vs. regulation** (Ch.3): externalities and the tragedy of the commons show markets under-price environmental harm; cap-and-trade, natural capitalism, and similar frameworks are competing fixes (one regulatory, one voluntary/strategic).
4. **Invention vs. commercialisation** (Ch.5): most entrepreneurs are not inventors; innovation is the *combination* of invention and entrepreneurial commercialisation (Hindle's definition), a point easy to conflate on exam.

## Track B: Transfer Function Models — re-derived condensation
Re-scanning, the chapter's real "spine" is a **five-step algorithm** applied once (stirred tank) and then left for the student to repeat twice (Class Exercises 1 & 2):
ODE → subtract steady-state → substitute deviation variables → Laplace transform (initial condition vanishes) → isolate individual TF by holding other inputs constant.
Everything else (definitions of gain/time-constant, additive/multiplicative properties) exists to let you *use* the transfer function once you have it, not to derive it.

## Track C: Environmental Law — re-derived condensation
Re-scanning, the course has **two distinct halves**: (i) a *framework* half (Triple A weighting, systems approach) that is a scoring tool to be applied numerically, and (ii) a *hierarchy* half (Constitution → Acts → Regulations → codes → by-laws → standards) that is a factual structure to be recalled and correctly ordered. The case studies (Pienaar, Medupi/Kusile, Shell) are where these two halves are tested together — Pienaar tests the hierarchy/legal-interpretation side, Medupi/Kusile and Shell test the Triple A scoring side.

## Cross-course connection: re-verified independently
Re-deriving the link independently (rather than reusing Run 4's table) confirms the same core connection holds: Tension #3 in Track A ("market vs. regulation") *is* the same idea as Track C's hierarchy existing at all — a regulatory hierarchy is only necessary because, per Ch.3, markets alone under-price environmental harm. This is a genuine, source-supported connection, not a coincidence of two independently-taught topics: Ch.3's theoretical justification for regulation explains *why* Track C's entire regulatory apparatus (Constitution → NEMA → SEMAs → Regulations) exists in the first place.

A second, previously less-emphasised connection: Track A's "individual vs. system" tension (Ch.1–2) parallels Track C's "systems approach" — both frameworks argue that no single-dimension explanation (the lone entrepreneurial genius; a purely technical engineering judgement) is sufficient, and that success requires satisfying multiple interacting factors at once (schools of thought / PC-PE-PG-BE, for entrepreneurship; technical-environmental-institutional-legal-financial, for engineering decisions).

**Likely assessment points (integrated, re-derived)**
- Explain why market failure (Ch.3) provides the economic justification for South Africa's environmental regulatory hierarchy (Environmental Law).
- Compare the "systems approach" (Environmental Law) to the macro/micro schools of entrepreneurial thought (Ch.1) as two examples of multi-factor decision frameworks.
- Distinguish invention from commercialisation (Ch.5) and explain why this distinction matters for evaluating who deserves credit/reward in an entrepreneurial venture.
- (Transfer Functions, standalone) Apply the five-step derivation algorithm to a new SISO system not shown in class (e.g., Class Exercise 1 or 2).

---
---

# DRAFT STUDY NOTES — RUN 5

Approached a second time, the three courses are best understood as answering three different kinds of "why do things work this way" questions. **Entrepreneurship** asks why some individuals create new economic or social value where markets and institutions have failed to (Ch.1–2 explain the *who*; Ch.3 explains *where markets fail*, particularly environmentally; Ch.4 asks *whether the value-creation is ethical*; Ch.5 asks *how new ideas actually get generated and commercialised*). **Environmental Law** answers a narrower, applied version of the same market-failure question specifically for South African engineering practice: given that markets under-price environmental harm (the same insight as Ch.3), what legal machinery exists to force its internalisation, and what weighted framework (Triple A) should an engineer use to decide whether a project should proceed at all? **Transfer Function Models** answers a completely different kind of question — not "why," but "how do we mathematically represent and predict" a dynamic physical process — and is best kept mentally separate from the other two.

The strongest, most exam-useful integration point is this: Chapter 3's economic theory of *why* negative externalities require intervention (tragedy of the commons, cap-and-trade) is the direct conceptual ancestor of *why* Environmental Law's entire regulatory hierarchy exists — NEMA and its SEMAs, Minimum Emission Standards, and the polluter-pays Regulations are the applied, jurisdiction-specific answer to the same theoretical problem Ch.3 poses abstractly. A student who understands *why* markets fail environmentally (Ch.3) has already understood *why* South Africa needs an NEMA (Environmental Law) — the second is simply the first, operationalised into law. The Medupi/Kusile case study is the single richest artefact for testing this connection, since its emission-standard postponement disputes are literally the tragedy-of-the-commons/externality problem playing out as an active regulatory dispute.

A secondary, subtler integration point: both Entrepreneurship (Ch.1's macro/micro schools; Ch.2's PC-PE-PG-BE motivation model) and Environmental Law (the "systems approach"/Triple A) reject single-factor explanations in favour of multi-system ones. This is a shared intellectual habit across both courses — always look for the *several* interacting factors, not the one dominant cause — worth recognising as a transferable exam-answer strategy (e.g., "explain X" answers in both courses tend to reward naming multiple interacting systems/schools rather than picking just one).

Transfer Function Models remains genuinely separate: its five-step derivation algorithm and TF properties (additive, multiplicative, superposition) should be revised as a standalone applied-maths skill, not integrated with the other two courses' content.

---
---

# SOURCE CHECK — RUN 5

**1. Missing concepts**
- This run's re-derived Track A "four tensions" framing is a reorganisation, not a replacement, of the chapter-by-chapter content in Runs 1 and 4 — it deliberately omits re-listing individual definitions/statistics already fully captured there. *Correction*: Final Notes explicitly directs back to Run 1 (full Ch.1–5 detail) and Run 2 (full TF derivation) for anything not repeated here, so nothing is actually lost, only de-duplicated.

**2. Missing definitions**
- None new required — Run 5 introduces no new source-based terms, only new *organisational* framings (the "four tensions," the "two halves" of Environmental Law) that are Claude's own structuring devices, not source vocabulary. *Correction*: Final Notes labels these framings explicitly as organisational aids rather than presenting them as if the source itself used this exact structure, to avoid misattributing them as source terminology.

**3. Missing formulas**
- Same as Run 4's Source Check — the Triple A table and the core TF formula are retained in full in Final Notes rather than only summarised in prose.

**4. Unsupported claims**
- The claim that "Ch.3's theory is the direct conceptual ancestor of Environmental Law's regulatory hierarchy" is an interpretive/pedagogical claim, not a fact stated in either source document — neither course explicitly cross-references the other (they are different courses at, apparently, different institutions). *Correction*: Final Notes rephrases this as an explicitly flagged *study aid/analogy* for the student's own benefit, not as a fact asserted by either source, to avoid implying the sources themselves draw this connection.

**5. Incorrect interpretations**
- None found in the substantive content; the reframing is organisational, not factual, so there is nothing to mis-state.

**6. Oversimplifications**
- Describing Environmental Law as having "two distinct halves" (framework vs. hierarchy) is a simplification — the Pienaar case and the case studies both actually blend legal-hierarchy reasoning *and* judgement/framework application, so the "two halves" don't map perfectly onto "two separate case studies" as stated. *Correction*: Final Notes clarifies that the case studies test both halves together, not one each exclusively.

**7. Changes in terminology that could alter meaning**
- None — no source terminology is altered; only new connective/organisational language is added, and it is clearly flagged as such.

---
---

# FINAL STUDY NOTES — RUN 5

**1. Topic:** A second-pass, thematically reorganised integration of Entrepreneurship (Ch.1–5), Transfer Function Models, and Environmental Law — emphasising *why* markets fail and *why* multi-factor decision frameworks recur across two of the three courses, while confirming Transfer Function Models remains independent.

**2. Key definitions**
*(All formally defined in Runs 1, 2, and 3/4 — not redefined here to avoid duplication. Key labels used in this run's organisational framing:)*
- **"Market vs. regulation" tension** (this run's label, not source terminology): the recurring idea that unregulated markets under-price environmental harm, addressed voluntarily by ecopreneurs/entrepreneurial-ecology frameworks (Ch.3–4) or by force of law (NEMA/SEMAs/Regulations, Environmental Law).
- **"Systems approach" parallel** (this run's label): both Entrepreneurship's macro/micro schools + PC-PE-PG-BE motivation model, and Environmental Law's Triple A/systems approach, reject single-factor explanations in favour of multi-factor ones.
- *Study-aid disclaimer*: neither course explicitly cross-references the other; the connections below are Claude's pedagogical synthesis to aid recall, not facts stated by either source.

**3. Main concepts**
- Entrepreneurship's four organising tensions: individual vs. system (Ch.1–2); profit vs. mission (Ch.1, 4); market vs. regulation (Ch.3); invention vs. commercialisation (Ch.5).
- Environmental Law's two interacting halves: the Triple A *scoring framework* (numerical, weighted) and the *regulatory hierarchy* (Constitution → Acts → SEMAs → Regulations → codes → by-laws → standards) — note: the case studies (Pienaar; Medupi/Kusile; Shell) each draw on **both** halves, not one exclusively.
- Transfer Function Models' core algorithm (standalone): ODE → subtract steady-state → deviation variables → Laplace transform → isolate individual TFs by holding other inputs constant; then use additive/multiplicative properties and superposition to combine/interpret results.

**4. Important formulas**
- Triple A weighting table (repeated for completeness):

| Triple 'A' Criteria | Technical | Environmental | Institutional | Legal | Financial | Total weighting |
|---|---|---|---|---|---|---|
| Appropriate | 50% | 50% | – | – | – | 25% |
| Applicable | – | – | 50% | 50% | – | 25% |
| Affordable | – | – | – | – | 100% | 50% |

- Transfer function core result (worked example): T(t) = 100 + 15(1 − e^(−2t)); general form T′(s) = [K₁/(τs+1)]Tᵢ′(s) + [K₂/(τs+1)]Q′(s).

**5. Processes/steps**
- Exam strategy transferable across Entrepreneurship and Environmental Law: when asked to "explain" or "evaluate" a decision/venture, default to naming *multiple interacting factors/systems* (schools of thought, or Technical/Environmental/Institutional/Legal/Financial) rather than a single cause — both courses reward this multi-factor habit.
- Transfer function derivation recipe (standalone, unchanged): five-step algorithm as in Run 4/Run 2.

**6. Examples**
- Medupi/Kusile's emission-standard postponement disputes = the richest single example bridging Ch.3's externality theory and Environmental Law's applied regulatory hierarchy — genuinely worth using as an essay example in either course.
- Pienaar v ECSA = example of the regulatory-hierarchy half of Environmental Law (interpreting a specific statutory provision), distinct from — but tested alongside — the Triple A scoring half in the same course.
- Stirred-tank heating system = standalone technical example with no cross-course counterpart.

**7. Important points to remember**
- The market-failure logic in Entrepreneurship Ch.3 and the existence of Environmental Law's regulatory hierarchy are conceptually connected (same underlying economic problem, two different treatments) — but this connection is a *study aid*, not something either source text states explicitly; say so if asked to justify the link in an assignment.
- Both Entrepreneurship and Environmental Law reward "multiple interacting factors" answers over single-cause answers — a transferable exam habit.
- Transfer Function Models is unrelated to the other two courses; do not force integration when revising it.

**8. Potential test questions**
- Explain why unregulated markets tend to under-price environmental harm (Ch.3), and describe one South African legal mechanism (Environmental Law) that exists to correct this.
- Compare the "systems approach" in engineering decision-making to the macro/micro schools of entrepreneurial thought — what do both frameworks assume about single-factor explanations?
- Using the Medupi/Kusile case, identify one fact that illustrates the externality/regulation tension taught in Entrepreneurship Ch.3.
- (Standalone) Given a two-tank-in-series liquid-level system, derive the overall transfer function Q₂′(s)/Q₁′(s) using the multiplicative property.
