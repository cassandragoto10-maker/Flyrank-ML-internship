# Study Notes Workflow — RUN 2 & RUN 3

**RUN 2 source:** *Unit 4 – Transfer Function Models* (PRCCHB3, Process Control 3B) — Mr. Fred Rasifudi, 29 July 2025
**RUN 3 source:** *Learning Unit 1 (Updated)* — Environmental Laws and Regulations (ENVCHB3, Environmental Engineering 3B) — Mr. L Motsoeneng, 14 July 2026

---
---

# RUN 2 — Unit 4: Transfer Function Models (PRCCHB3)

# SOURCE EXTRACTION — RUN 2

**Key concepts**
- Dynamic models can be represented as ODEs *or*, more conveniently, as **Transfer Function Models** based on Laplace Transforms.
- A transfer function characterises the dynamic relationship between one input (independent/"cause") variable and one output (dependent/"effect") variable — a **SISO (single-input, single-output)** representation.
- **Deviation (perturbation) variables** simplify Laplace-domain analysis by zeroing out initial conditions.
- Development of a transfer function from a first-principles ODE, using the stirred-tank heating process as the running example.
- **Process gain** and **time constant** as the defining parameters of a first-order transfer function.
- Properties of transfer functions: **additive property** and **multiplicative property**.
- The **Principle of Superposition** for linear dynamic systems.

**Definitions/terminology**
- **Transfer Function**: the ratio of the Laplace transform of the output to the Laplace transform of the input, with all initial conditions taken as zero. Formally, if ℓu(t) = U(s) and ℓy(t) = Y(s), the transfer function relates U(s) and Y(s) (ℓ = the Laplace operator).
- **G(s)** (SISO definition): G(s) = Y(s)/X(s), where Y(s) = L[y(t)] and X(s) = L[x(t)].
- **Input/forcing function/"cause"** (x) vs **output/response/"effect"** (y).
- **Deviation variable**: the difference between the actual value of a variable and its steady-state value (e.g., T′ = T − T̄).
- **Process Gain (K)**: a proportionality constant relating steady-state change in output to steady-state change in input.
- **Time Constant (τ)**: the parameter governing the speed of the dynamic response; for the stirred-tank example, τ = ρV/w.
- **First-order transfer function**: a transfer function whose denominator is first order in the Laplace variable s (e.g., K/(τs+1)).
- **Additive property**: if two inputs independently affect one output via separate transfer functions, the combined response is the sum of each input's individual contribution.
- **Multiplicative property**: transfer functions in series (cascade) multiply together to give the overall transfer function.
- **Principle of Superposition**: valid for linear, dynamic models (transfer functions); it is why the effects of multiple simultaneous input changes are additive.

**Formulas/equations**
- General Laplace transform pairs given as motivation: ℓ[sin ωt] = ω/(s²+ω²); ℓ[e^(−at)] = 1/(s+a); s = σ + jω (complex frequency).
- Stirred-tank ODE (from Unit 1, recalled): VρC(dT/dt) = wC(Tᵢ − T) + Q — (1)
- Steady-state form: 0 = wC(T̄ᵢ − T̄) + Q̄ — (3)
- Deviation-variable ODE: VρC(dT′/dt) = wC(Tᵢ′ − T′) + Q′ — (6), where T′ = T − T̄, Tᵢ′ = Tᵢ − T̄ᵢ, Q′ = Q − Q̄ — (7)
- Laplace transform of (6): VρC[sT′(s) − T′(t=0)] = wC[Tᵢ′(s) − T′(s)] + Q′(s) — (8), and T′(t=0) = 0 because the process starts at steady state.
- Rearranged transfer function form: T′(s) = [K₁/(τs+1)]Tᵢ′(s) + [K₂/(τs+1)]Q′(s) — (10)
- Parameter definitions: Process Gain 1 = K₁ = 1; Process Gain 2 = K₂ = 1/(wC); Time Constant = τ = ρV/w.
- Transfer function between Q′ and T′ (Tᵢ held constant, so Tᵢ′(s)=0): T′(s)/Q′(s) = K/(τs+1) — (12)
- Transfer function between T′ and Tᵢ′ (Q held constant, so Q′(s)=0): T′(s)/Tᵢ′(s) = 1/(τs+1) — (13)
- SISO general definition: G(s) = Y(s)/X(s).
- Additive property: Y(s) = G₁(s)U₁(s) + G₂(s)U₂(s), given Y(s)/U₁(s) = G₁(s) and Y(s)/U₂(s) = G₂(s).
- Multiplicative property: Y(s)/U₃(s) = G₂(s)G₃(s), given Y(s)/U₂(s) = G₂(s) and U₂(s)/U₃(s) = G₃(s).

**Processes (derivation steps)**
1. Start with the dynamic ODE model (constant holdup/flow assumed).
2. Write the steady-state version of the same ODE (derivatives = 0).
3. Subtract the steady-state equation from the dynamic equation.
4. Recognise dT/dt = d(T−T̄)/dt since T̄ is constant, and substitute in deviation variables.
5. Take the Laplace transform of the deviation-variable ODE.
6. Evaluate the initial condition term T′(t=0); it is zero because the process starts at steady state.
7. Rearrange algebraically to isolate T′(s) as a function of the input deviation variables — this gives the transfer function form.
8. To isolate an individual transfer function (e.g., T′/Q′), hold the other input constant at its steady-state value (so its deviation variable transforms to zero) and simplify.

**Examples**
- **Stirred-tank heating system** (Fig. 2.3): a heater tank with inlet flow/temperature (wᵢ, Tᵢ), constant holdup volume V, heater duty Q, and outlet stream (T, w) — the running worked example for the whole chapter.
- **Class Exercise (worked, slide 18–20)**: stirred-tank heating process, constant volume.
  - Given: T̄ᵢ = 70°F, Q̄ = 1920 Btu/min, w = 220 lb/min, ρ = 62.4 lb/ft³, C = 0.32 Btu/(lb·°F), V = 1.6 ft³.
  - Steady-state result: T̄ = 100°F.
  - Disturbances at t = 0: Tᵢ changes from 70 to 90°F; Q changes from 1920 to 1600 Btu/min.
  - Solution: T′(s) = K₁/(τs+1)·Q′(s) + K₂/(τs+1)·Tᵢ′(s), with τ = ρV/w, K₁ = 1, K₂ = 1/(wC).
  - After substitution and simplification: T′(s) = −5/[s(0.5s+1)] + 20/[s(0.5s+1)] = 15/[s(0.5s+1)].
  - Inverse Laplace result: **T(t) = 100 + 15(1 − e^(−2t))**.
- **Class Exercise 1 (unworked, slide 21)**: single tank with cross-sectional area A, inflow qᵢ, outflow q, level h; resistance to flow given by h = qRᵥ. Task: derive the transfer function model, write expressions for process gain and time constant, given inflow ≠ outflow.
- **Class Exercise 2 (unworked, slides 22–23)**: two surge tanks in series (top tank inflow q₁, area A₁, resistance R₁, level h₁; lower tank area A₂, resistance R₂, level h₂, outflow q₂). Task: derive Q₂′(s)/Q₁′(s) and relate it to the individual TFs H₁′(s)/Qᵢ′(s), Q₁′(s)/H₁′(s), H₂′(s)/Q₁′(s), Q₂′(s)/H₂′(s).

**Important relationships/numbers**
- The heater example's numerical constants: τ = ρV/w = (62.4 × 1.6)/220 ≈ 0.454 (rounds to the 0.5 used in the exercise); K₂ = 1/(wC) = 1/(220×0.32) ≈ 0.0142.
- Steady-state exit temperature T̄ = 100°F given the stated nominal steady-state inputs.
- Final dynamic response settles to a new steady state of T = 115°F as t→∞ (100 + 15), approached exponentially with time constant 0.5 min.

**Likely assessment points**
- Derive a transfer function from a first-principles ODE using deviation variables (as in the worked class exercise) — this is explicitly flagged as a "Class Exercise" type of question, i.e., a strong candidate for a test/exam question.
- State the definition of a transfer function (ratio of Laplace-transformed output to input, zero initial conditions).
- Explain why deviation variables are used (they zero the initial-condition term, simplifying analysis).
- Identify process gain and time constant from a given transfer function or derive them symbolically.
- Apply the additive and multiplicative properties of transfer functions, including drawing the corresponding block diagram.
- Explain the Principle of Superposition and its link to linearity.
- Complete Class Exercises 1 and 2 (unworked in the slides) — likely to appear as tutorial/test questions given the "See whiteboard for detailed solution" framing of the worked example.

---
---

# DRAFT STUDY NOTES — RUN 2

Transfer function models are an alternative, Laplace-domain representation of the same dynamic behaviour normally captured by ordinary differential equations. Where an ODE describes a process in the time domain, a transfer function G(s) = Y(s)/X(s) captures the same input–output relationship as an algebraic ratio in the complex-frequency domain, under the convention that all initial conditions are zero. This is possible because Laplace transforms convert common time functions (like sin ωt or e^(−at)) into algebraic functions of the complex variable s = σ + jω, making differential equations easier to manipulate.

A transfer function is inherently a **SISO** (single-input, single-output) construct: it relates one "cause" (input/forcing function, x) to one "effect" (output/response, y). To derive one from a physical ODE, the chapter works through the stirred-tank heating process. Starting from the governing energy balance ODE, the process's steady-state form is subtracted from the full dynamic equation, yielding an equation in terms of **deviation variables** — the actual value of a variable minus its steady-state value (T′ = T − T̄, etc.). This is a key simplification, because it makes the initial condition term vanish when the Laplace transform is taken (since the process starts at steady state, T′(0) = 0), which considerably simplifies subsequent algebra.

Rearranging the Laplace-transformed deviation-variable equation isolates the output T′(s) as a function of the input deviation variables, weighted by **process gains** (K₁, K₂) and a shared **time constant** (τ = ρV/w for this system). Holding one input constant at a time (so its deviation variable becomes zero in Laplace space) isolates the individual transfer function relating that one input to the output — giving, for the tank example, T′(s)/Q′(s) = K/(τs+1) and T′(s)/Tᵢ′(s) = 1/(τs+1). Both are **first-order transfer functions**, so named because their denominators are first order in s.

The worked class exercise applies this directly with numerical values, deriving τ, K₁, and K₂ from given physical parameters, substituting given step disturbances in both Tᵢ and Q, and inverse-Laplace-transforming the result to obtain the explicit time-domain response T(t) = 100 + 15(1 − e^(−2t)).

Two general properties of transfer functions are introduced: the **additive property** (when an output is affected by two inputs via separate transfer functions, the combined response is the algebraic sum of each individual contribution — represented graphically by a summing junction in a block diagram) and the **multiplicative property** (when transfer functions are connected in series/cascade, the overall transfer function is the product of the individual ones). Both properties hold because linear, dynamic transfer-function models obey the **Principle of Superposition** — this is also why the individual effects of Q and Tᵢ on T combine additively in the tank example.

The chapter closes with two unworked class exercises applying the same derivation method to single-tank and two-tank-in-series liquid level systems, using the flow-resistance relationship h = qRᵥ, reinforcing the general derivation procedure (ODE → steady-state subtraction → deviation variables → Laplace transform → rearrange → isolate individual TFs).

---
---

# SOURCE CHECK — RUN 2

**1. Missing concepts**
- The draft summary does not explicitly restate the outcomes list from slide 3 (block flow diagrams, deviation variables, ODEs in deviation-variable form, Laplace/inverse Laplace to solve a TF model) as a discrete item. *Correction*: added as a standalone "Learning outcomes" bullet in Final Notes.
- The draft does not explicitly mention that block flow diagrams are one of the stated learning outcomes but are only illustrated implicitly (the u(t)→Plant→y(t) and x(t)/X(s)→system→y(t)/Y(s) diagrams on slides 5–6, and the summing-junction diagram on slide 16). *Correction*: flagged explicitly in Final Notes under Processes/Examples.

**2. Missing definitions**
- None of substance — all key terms (transfer function, deviation variable, process gain, time constant, additive/multiplicative property, superposition) are defined in both the extraction and draft.

**3. Missing formulas**
- The draft's numeric substitution for τ and K₂ ("τ ≈ 0.454...K₂ ≈ 0.0142") in the Source Extraction step are Claude's own arithmetic check, not stated explicitly in the source slides — the source slide only shows the final simplified transfer function T′(s) = 15/[s(0.5s+1)] without showing the intermediate numeric substitution step for τ and K₂. *Correction*: Final Notes labels these intermediate numbers as "derivable from the given data" rather than presenting them as directly quoted from the slide, to avoid implying the source shows this arithmetic explicitly.

**4. Unsupported claims**
- None identified in the draft that aren't traceable to the extracted slide content.

**5. Incorrect interpretations**
- None found — the derivation sequence, formulas, and worked example numbers all match the source slides exactly (equations 1–13, and the final answer T(t) = 100 + 15(1−e^(−2t))).

**6. Oversimplifications**
- The draft states the "final dynamic response settles to a new steady state of T = 115°F" — this is a valid mathematical inference from T(t) = 100 + 15(1−e^(−2t)) as t→∞, but the source slides themselves stop at presenting T(t) and do not explicitly state the new steady-state value or the settling behaviour. *Correction*: Final Notes marks this explicitly as an inference from the given result, not a directly stated source fact.

**7. Changes in terminology that could alter meaning**
- None identified — "process gain," "time constant," "deviation variable," and "transfer function" are used consistently with the source's own terminology throughout.

---
---

# FINAL STUDY NOTES — RUN 2

**1. Topic:** Deriving and using transfer function (Laplace-domain) models of dynamic processes, using deviation variables, illustrated with a stirred-tank heating system.

**2. Key definitions**
- **Transfer function**: the ratio of the Laplace transform of the output to the Laplace transform of the input, with all initial conditions set to zero.
- **G(s) = Y(s)/X(s)**, where Y(s) = L[y(t)], X(s) = L[x(t)] — the general SISO transfer-function definition.
- **Input/"cause"** (x) and **output/"effect"** (y) — the forcing function and the response.
- **Deviation (perturbation) variable**: the difference between a variable's actual value and its steady-state value, e.g. T′ = T − T̄, Tᵢ′ = Tᵢ − T̄ᵢ, Q′ = Q − Q̄.
- **Process Gain (K)**: proportionality constant relating a steady-state output change to a steady-state input change.
- **Time Constant (τ)**: parameter governing the speed of the dynamic response (τ = ρV/w for the stirred-tank example).
- **First-order transfer function**: one whose denominator is first order in the Laplace variable s.
- **Additive property**: response to multiple inputs = sum of the individual responses (Y(s) = G₁(s)U₁(s) + G₂(s)U₂(s)).
- **Multiplicative property**: transfer functions in series multiply (Y(s)/U₃(s) = G₂(s)G₃(s)).
- **Principle of Superposition**: valid for linear dynamic models; underlies both properties above.

**3. Main concepts**
- Two equivalent ways to represent a dynamic model: (a) an ODE in the time domain, (b) a transfer function in the Laplace (s) domain — both describe the same dynamic behaviour.
- A transfer function is a SISO relationship (one input, one output).
- Using deviation variables makes the Laplace-transformed initial-condition term zero (since the process starts at steady state), simplifying algebra significantly.
- Individual transfer functions between one output and each of several inputs can be found by holding all other inputs constant at their steady-state values.
- The Laplace transform converts common time functions into algebraic functions of s (e.g., ℓ[sin ωt] = ω/(s²+ω²); ℓ[e^(−at)] = 1/(s+a)), with s = σ + jω being a complex variable ("complex frequency").

**4. Important formulas**
- Stirred-tank dynamic ODE: VρC(dT/dt) = wC(Tᵢ − T) + Q
- Deviation-variable ODE: VρC(dT′/dt) = wC(Tᵢ′ − T′) + Q′
- Laplace-transformed and rearranged: T′(s) = [K₁/(τs+1)]Tᵢ′(s) + [K₂/(τs+1)]Q′(s), with K₁ = 1, K₂ = 1/(wC), τ = ρV/w
- Transfer function (Tᵢ constant): T′(s)/Q′(s) = K/(τs+1)
- Transfer function (Q constant): T′(s)/Tᵢ′(s) = 1/(τs+1)
- Additive property: Y(s) = G₁(s)U₁(s) + G₂(s)U₂(s)
- Multiplicative property: Y(s)/U₃(s) = G₂(s)G₃(s)

**5. Processes/steps** (general recipe for deriving a transfer function from an ODE)
1. Write the dynamic ODE model.
2. Write its steady-state form (set derivatives to zero).
3. Subtract the steady-state equation from the dynamic equation.
4. Substitute in deviation variables (using dT/dt = d(T−T̄)/dt since T̄ is constant).
5. Take the Laplace transform; the initial-condition term is zero if the process starts at steady state.
6. Algebraically rearrange to isolate the output deviation variable as a function of the input deviation variable(s), reading off K (gain) and τ (time constant).
7. To isolate a single-input transfer function, hold other inputs constant at steady state (their deviation variables become zero in Laplace space) and simplify.
- The learning outcomes for this unit (as stated) are to: draw block flow diagrams representing transfer functions; define and apply deviation variables; write ODEs in terms of deviation variables; and use Laplace/inverse Laplace transforms to solve a transfer function model.

**6. Examples**
- **Stirred-tank heating system** (running example): inlet stream (Tᵢ, wᵢ), constant holdup V, heater input Q, outlet stream (T, w).
- **Worked class exercise**: T̄ᵢ = 70°F, Q̄ = 1920 Btu/min, w = 220 lb/min, ρ = 62.4 lb/ft³, C = 0.32 Btu/(lb·°F), V = 1.6 ft³ → steady state T̄ = 100°F. Step disturbances at t=0 (Tᵢ: 70→90°F; Q: 1920→1600 Btu/min) give, after deriving τ and K₂ from the given data, T′(s) = 15/[s(0.5s+1)], and by inverse Laplace transform: **T(t) = 100 + 15(1 − e^(−2t))**. (The new steady state as t→∞, T=115°F, is a direct mathematical consequence of this result, though not stated explicitly on the slide.)
- **Class Exercise 1 (unworked)**: single tank, cross-sectional area A, inflow qᵢ ≠ outflow q, level h, flow resistance h = qRᵥ — derive the TF model and expressions for process gain/time constant.
- **Class Exercise 2 (unworked)**: two surge tanks in series (areas A₁, A₂; resistances R₁, R₂) — derive Q₂′(s)/Q₁′(s) and relate it to the four individual tank transfer functions via the multiplicative property.

**7. Important points to remember**
- Deviation variables are the key trick that makes Laplace analysis of process models tractable — they eliminate the need to carry initial-condition terms through the algebra.
- A transfer function's denominator order tells you its "order" (first-order here, because τs+1 is linear in s).
- The additive and multiplicative properties are two distinct ways transfer functions combine — additive for parallel/simultaneous inputs to one output, multiplicative for TFs in series/cascade.
- Superposition (validity of the additive property) only holds because these are *linear* dynamic models — this is explicitly flagged as always true for transfer functions but not necessarily for nonlinear ODE models in general.

**8. Potential test questions**
- Starting from a given nonlinear or linear ODE process model, derive the transfer function(s) relating each input to the output (this exact type of question is explicitly worked in class and flagged for practice via Class Exercises 1 and 2).
- Define a transfer function and explain the role of the zero-initial-condition assumption.
- Explain why deviation variables are used and derive T′(t=0) = 0 from first principles.
- Given a first-order transfer function, identify the process gain and time constant, and compute the step response (numerically and via inverse Laplace transform).
- State and apply the additive and multiplicative properties of transfer functions, including drawing the corresponding block diagram.
- Complete Class Exercise 1 (single tank) and Class Exercise 2 (two tanks in series) in full.

---
---
---

# RUN 3 — Learning Unit 1: Environmental Laws and Regulations (ENVCHB3)

# SOURCE EXTRACTION — RUN 3

**Key concepts**
- The role and purpose of engineering in society: intersecting public wellbeing, industry, and the natural environment; engaging with health/safety/environmental issues; applying risk assessment; evaluating economic, social, cultural, and environmental impacts of engineering decisions.
- Learning outcomes for LU1/LU2: understand engineering decision-making; apply environmental laws and regulations; define principles of sustainable development; perform calculations for safe products and compliance with codes/standards.
- The **"Triple A" criteria** ("Integrated systems approach") for engineering decision-making: **Appropriate, Applicable, Affordable**.
- The concept of a **"systems approach"**: evaluating a technology/project as embedded within multiple interacting systems (technical, environmental, institutional, legal, financial) that must all be satisfied simultaneously.
- Categories of **identified risk**: Technical, Institutional, Environmental & Legal, Financial.
- South Africa's layered **regulatory framework**: the Constitution → national Acts → Specific Environmental Management Acts (SEMAs) → Regulations within Acts → professional/regulatory-body codes → municipal by-laws → technical standards (SANS/ISO) and common law.
- The **"polluter pays"** principle as the key enforcement logic of NEMA's environmental regulations.
- Case law: **Pienaar v Engineering Council of South Africa** — whether a registered engineer can evade disciplinary accountability by cancelling ECSA registration.
- Case study analysis method: applying the Triple A framework retrospectively to real projects (**Medupi/Kusile power stations — Case A**; **Shell — Case B**) to score, weight, and evaluate project decisions against real-world outcomes.

**Definitions/terminology**
- **"Systems approach"**: not evaluating a technology/project in isolation along a single dimension, but recognising it as embedded within multiple interacting systems (technical/engineering performance; natural environment/ecological; institutions/governance; legal/regulatory "rules of the game"; financial/economic) that must all be satisfied simultaneously for the project to succeed.
- **Triple A criteria weighting**: Appropriate = 25% of total (Technical 50% + Environmental 50% of that 25%); Applicable = 25% of total (Institutional 50% + Legal 50% of that 25%); Affordable = 50% of total (Financial 100% of that 50%). Project only "qualifies" (i.e., is judged to pass) when total weighting reaches 100%.
- **Appropriateness** — Technical (is the technology sound, reliable, scaled correctly, is there a skilled local workforce, is the site suitable?); Environmental (is the technology suited to the physical/ecological context — climate, resources, impact, end-of-life plan?).
- **Applicability** — Institutional (can local institutions/organisations/communities operate, maintain, and govern the technology; is there capacity, ownership, and recognition from higher bodies?); Legal (does it comply with relevant legislation, regulations, permits, standards?).
- **Affordability** — Financial (can the technology be funded for capital and ongoing O&M costs within the constraints of users/utility/funder; does it make economic sense?).
- **NEMA "polluter pays" principle**: if a site causes environmental damage (e.g. an oil leak), the responsible business/entity must clean it up — analogised in the slides to "if you spill milk, you must wipe it up."
- **SEMAs (Specific Environmental Management Acts)**: the individual environmental Acts operating under/alongside NEMA (Air Quality Act, Waste Act, Protected Areas Act, Biodiversity Act, etc.).
- **Regulations** (as distinct from Acts): "standard-issue rules within the Acts" — the operational rules that implement an Act's provisions (e.g., NEMA's Environmental Regulations).
- **Codes**: standards issued by professional/industry bodies (ECSA, SAICE, etc.), voluntary or contractually binding; courts can still enforce common-law liability for negligence even where a code was followed.
- **By-laws**: mostly district/municipal-specific rules developed under the authority of an overarching national Act (e.g., City of Johannesburg Municipal Planning By-law).

**Formulas/frameworks**
- Triple A weighting table:

| Triple 'A' Criteria | Technical | Environmental | Institutional | Legal | Financial | Total weighting |
|---|---|---|---|---|---|---|
| Appropriate | 50% | 50% | – | – | – | 25% |
| Applicable | – | – | 50% | 50% | – | 25% |
| Affordable | – | – | – | – | 100% | 50% |

- Case-study evaluation method (applied to Medupi/Kusile and Shell): (1) score each sub-criterion using evidence, not assumption; (2) apply the 25/25/50 weighting to reach a composite Triple A score; (3) decide pass ("proceed as implemented") or fail ("require redesign/abandonment"); (4) compare the score against the real-world outcome and explain any mismatch.

**Processes/steps**
- South African regulatory hierarchy (as laid out across slides 20, 25–30): Constitution of the RSA (1996), Sections 22, 23 & 24 (supreme law) → national Acts (Professional Regulation/Procurement; Environmental & Resource; Health & Safety; Standards; IP/Commercial) → Specific Environmental Management Acts (SEMAs) under NEMA → Regulations within Acts (e.g., NEMA Environmental Regulations, "polluter pays") → profession-specific regulatory bodies (ECSA and built-environment counterparts) → municipal by-laws → technical standards (SANS/ISO) and codes/common law.
- Pienaar v ECSA case progression: complaint lodged (Sept 2021) → ECSA investigator appointed under s.28 of the Engineering Profession Act 46 of 2000 → investigator's report (Aug 2022) found prima facie improper conduct, recommended disciplinary proceedings → Pienaar emigrated to Ireland (Oct 2022) → Pienaar requested cancellation of registration (18 May 2024) → ECSA processed cancellation (20 May 2024) → ECSA notified him of a disciplinary inquiry (31 May 2024, ~10 days later) → Pienaar applied to review/interdict the disciplinary proceedings; ECSA counter-applied to set aside its own cancellation decision → court (Windell J) accepted ECSA's broad reading of "investigation" in s.20(3), held the cancellation unlawful, and rejected Pienaar's argument that ECSA's mandate doesn't extend abroad.
- Medupi/Kusile timeline (Case A): 2007 national electricity crisis/rolling blackouts → Eskom board approves Medupi (April 2007, R69.1bn initial CTC) and Kusile (2008) → boiler contract awarded to Hitachi Power Africa (Chancellor House held 25% stake in Hitachi's SA venture) → World Bank approves US$3.75bn loan (April 2010) with FGD condition attached → extensive delays (labour disputes, welding defects, coal-handling redesign, 2019 flooding) → CTC rises repeatedly (R69.1bn → R135–160bn by 2016 → >R300bn combined by 2019; independent "true cost" estimate ~R234bn Medupi / R226–239bn Kusile) → units commissioned mid-2010s onward with reliability problems (~40% reliability, 87 trips in one year) → Unit 4 hydrogen explosion (9 Aug 2021) → Kusile flue-gas stack structural failure (Oct 2022), temporary regulatory postponement to bypass FGD → ongoing Minimum Emission Standards postponement applications, contested by civil society (Centre for Environmental Rights, groundWork, Earthlife Africa) → SIU investigation into ~R4bn disputed contractor overpayments; Hitachi's 2015 US SEC settlement over Chancellor House bribery.

**Examples**
- **Slide 2 timeline**: illustrative career path of an engineer (intern/graduate → junior engineer → Pr. Eng Tech) and the industries employing chemical/process engineers: oil & gas/energy, chemicals manufacturing, fertiliser/agrochemicals, mineral processing, consumer/life sciences (pharma, biotech, food & beverage, cosmetics, pulp & paper), water/wastewater treatment, construction/EPC, academia/R&D.
- **Pienaar v ECSA**: worked case-law example of engineering professional accountability and the limits of evading regulatory jurisdiction via deregistration.
- **Medupi/Kusile power stations ("Case A")**: extended real-world case (slides 31–42) for applying the Triple A scoring framework; designed as a graded exercise (Task A: extract ≥10 facts/issues and classify by criterion; Task B: score and weight each sub-criterion to reach a composite decision; Task C: reflective questions comparing the scored outcome to the real outcome).
- **Shell ("Case B")**: parallel case-study exercise (slide 43) using the WWF "Risky Business" report as source material, applying the same Triple A scoring method.
- Regulatory examples cited: City of Johannesburg Municipal Planning By-law; SANS (>7,400 standards) and ISO (>25,000 standards) as the applicable technical standards bodies.

**Important relationships/numbers**
- Triple A weighting: Appropriate 25%, Applicable 25%, Affordable 50% of the total decision score; sub-criteria within each split 50/50 (Affordable is 100% Financial).
- Medupi: ~4,764 MW design capacity, 6 units, dry-cooled; Kusile: ~4,800 MW, 6 units — respectively the world's 3rd- and 4th-largest coal-fired power stations.
- Medupi initial approved cost R69.1 billion (2007) vs. independently estimated "true" all-in cost ~R234 billion — roughly 3× the original order-of-magnitude budget.
- Medupi/Kusile units reportedly achieving only ~40% reliability and 87 trips in one reported year (2019 presentation to Parliament).
- >7,400 SANS standards and >25,000 ISO standards referenced as the scale of the applicable technical-standards landscape.

**Likely assessment points**
- Explain the "systems approach" and why a project must satisfy all five systems (technical, environmental, institutional, legal, financial) simultaneously.
- Reproduce and apply the Triple A weighting table (25/25/50, with 50/50 sub-splits) to score a real or hypothetical project.
- Explain the South African environmental/engineering regulatory hierarchy from the Constitution down to municipal by-laws and technical standards.
- Explain the "polluter pays" principle and give an example of how NEMA enforces it.
- Summarise the facts, legal question, and holding of Pienaar v ECSA (can deregistration defeat ECSA's disciplinary jurisdiction?).
- Apply the Triple A scoring method to the Medupi/Kusile case study (this is explicitly structured as a graded, multi-part class task — Task A/B/C — so it is a very likely assessment/tutorial item) and/or the Shell case study.
- List the major categories of South African legislation relevant to engineering practice (Professional Regulation & Procurement; Environmental & Resource; Health & Safety; Standards; IP & Commercial) with at least one Act named in each category.

---
---

# DRAFT STUDY NOTES — RUN 3

This unit frames engineering decision-making as inherently multidimensional: engineers must weigh public wellbeing, industry needs, and environmental impact together, applying risk-assessment principles and evaluating the broader economic, social, cultural, and environmental consequences of their technical choices — not just narrow technical performance. The stated learning outcomes are to understand engineering decision-making, apply environmental laws and regulations, define principles of sustainable development, and perform compliance-related calculations.

The core decision framework introduced is the **"Triple A" criteria** — **Appropriate, Applicable, Affordable** — described as an "integrated systems approach." The underlying idea is that a technology or project cannot be judged along a single dimension; it is embedded simultaneously within a technical system (engineering performance), a natural-environment system (ecological context), an institutional system (governance and human capacity), a legal system (the regulatory "rules of the game"), and a financial system (funding and affordability), and must satisfy all of them together to succeed. This is formalised into a weighting scheme: Appropriate and Applicable each contribute 25% of the total decision score (split 50/50 between their two sub-criteria — Technical/Environmental for Appropriate, Institutional/Legal for Applicable), while Affordable contributes the remaining 50%, entirely via the Financial sub-criterion. A project is only considered fully "qualified" once the total weighting reaches 100%.

Each Triple A sub-criterion is elaborated with concrete questions engineers should ask: technically, is the technology sound, reliably scaled, and locally supportable by a skilled workforce and suitable site? Environmentally, is it suited to the local climate/resources, and is there an end-of-life/decommissioning plan? Institutionally, can local organisations actually operate and govern it, with genuine capacity and recognition from higher authorities? Legally, does it comply with relevant legislation and permits? Financially, can it be funded — both up front and on an ongoing basis — and does it make economic sense? A parallel discussion of project risk breaks these into technical, institutional, environmental & legal, and financial risk categories, each illustrated with brief real-world-style examples (e.g., foreign/non-compatible technology, lack of qualified professionals, operating without permits, adverse FOREX movements).

The unit then surveys South Africa's layered regulatory framework, starting from the Constitution (1996) — specifically Sections 22, 23, and 24 — as the supreme law, down through a wide range of national Acts organised into four groups: Professional Regulation and Procurement (Council for the Built Environment Act, Engineering Profession Act); Environmental & Resource Acts (NEMA and its associated "Specific Environmental Management Acts" or SEMAs — Air Quality, Waste, Protected Areas, Biodiversity — plus the National Water Act, Climate Change Act, MPRDA, CARA, National Forests Act); Health and Safety Acts (OHSA, Mine Health and Safety Act, Standards Act); and Intellectual Property & Commercial Acts (Patents Act, Copyright Act). Below the level of Acts sit Regulations (which operationalise Acts — e.g., NEMA's Environmental Regulations enforce the "polluter pays" principle), profession-specific regulatory-body codes (ECSA and its counterparts across the built environment — SACAP, SACPCMP, SACQSP, SACPVP, SACLAP), municipal by-laws (e.g., City of Johannesburg's Municipal Planning By-law), and finally technical standards (SANS, ISO) and common law, where courts retain the power to find negligence liability even where formal codes were followed.

A worked case study, **Pienaar v Engineering Council of South Africa**, illustrates the practical force of this regulatory structure: it examines whether a registered engineer can escape ECSA disciplinary jurisdiction simply by cancelling his registration once a disciplinary investigation is underway. The High Court held that the "investigation" referred to in section 20(3) of the Engineering Profession Act encompasses the entire disciplinary process (not merely the initial fact-finding stage), so cancellation is unlawful while that broader process remains incomplete — and that ECSA's protective mandate extends regardless of where the practitioner currently resides or practices.

The unit closes with two extended real-world case studies — **Medupi/Kusile power stations (Case A)** and **Shell (Case B)** — structured as graded exercises in applying the Triple A framework retrospectively: students must extract at least ten distinct facts from detailed background material, classify each by Triple A criterion, score and weight each sub-criterion to reach a composite decision (proceed / proceed with conditions / reject), and then compare that scored verdict against what actually happened, reflecting on where the framework succeeded or failed to predict the real-world outcome. The Medupi/Kusile background material is extensive, documenting the project's 2007 approval amid a national electricity crisis, its politically contentious contracting process, years of cost overruns and construction delays, chronic post-commissioning reliability problems, a major safety incident (a 2021 hydrogen explosion), ongoing environmental-compliance disputes, and corruption findings — providing rich material for scoring each of the five Triple A sub-criteria against real evidence.

---
---

# SOURCE CHECK — RUN 3

**1. Missing concepts**
- The draft summary compresses the "identified risks and mitigations" slide (18) into a passing mention within the Appropriateness paragraph, but the source treats it as its own distinct slide/topic with four named risk categories (Technical, Institutional, Environmental & Legal [listed twice with different examples], Financial). *Correction*: Final Notes lists all four risk categories explicitly and separately, matching the source's own structure (noting the source itself repeats the "Environmental & Legal" label for two different examples, which appears to be a slide labelling inconsistency in the original material, not an extraction error).
- The draft does not mention the list of built-environment regulatory-body counterparts to ECSA (SACAP, SACPCMP, SACQSP, SACPVP, SACLAP) individually — it references them only as "its counterparts." *Correction*: Final Notes lists each body and its profession explicitly, since this is a plausible list-recall assessment point.

**2. Missing definitions**
- None of substance — Triple A, systems approach, polluter pays, SEMA, Regulations, Codes, and By-laws are all defined in both extraction and draft.

**3. Missing formulas**
- None — the Triple A weighting table (25/25/50, with 50/50 sub-splits) is fully captured in both steps.

**4. Unsupported claims**
- None identified; all figures (Medupi/Kusile capacities, cost figures, reliability percentages, standards counts) trace directly to the slide content.

**5. Incorrect interpretations**
- None found. The Pienaar case summary (facts, legal question under s.20(3), and the court's holding) matches the source's three-slide account (22–24) accurately.

**6. Oversimplifications**
- The draft's treatment of the Medupi/Kusile case compresses roughly 3,000+ words of detailed background (slides 31–38) into one paragraph. This is appropriate for "draft notes" but risks under-preparing a student for the case-study exercise itself, which explicitly requires extracting "at least 10 distinct facts or issues." *Correction*: Final Notes adds a supplementary bullet list of ~10+ distinct, citable facts from the Medupi/Kusile background, organised by likely Triple A category, directly supporting the assessment task described in the source.
- The draft does not distinguish that the Case A exercise has three distinct graded tasks (Task A: fact extraction/classification table; Task B: scoring/weighting table; Task C: reflection questions) — it only mentions "extract...classify...score...compare" as one continuous process. *Correction*: Final Notes separates Task A, B, and C explicitly, matching the source's own slide structure (slides 40, 41, 42).

**7. Changes in terminology that could alter meaning**
- The draft uses "High Court" for the Pienaar case; the source slides do not explicitly name the court level, only naming the presiding judge ("Windell J"). *Correction*: Final Notes removes the unsupported "High Court" label and refers only to "the court," consistent with what the source actually states.

---
---

# FINAL STUDY NOTES — RUN 3

**1. Topic:** Engineering decision-making frameworks (the "Triple A" / integrated systems approach), South Africa's environmental and engineering regulatory framework, and their application to real-world case studies (professional discipline case law; Medupi/Kusile and Shell project case studies).

**2. Key definitions**
- **Systems approach**: evaluating a technology/project as embedded within multiple interacting systems (technical, environmental, institutional, legal, financial) that must all be satisfied simultaneously, rather than judging it along one dimension alone.
- **Triple A criteria**: **Appropriate** (Technical + Environmental, 25% of total), **Applicable** (Institutional + Legal, 25% of total), **Affordable** (Financial, 50% of total). A project only "qualifies" once total weighting reaches 100%.
- **Polluter pays principle**: the entity that causes environmental harm (e.g., a chemical/oil leak) must remediate it — the core enforcement logic of NEMA's Environmental Regulations.
- **SEMA (Specific Environmental Management Act)**: an individual environmental Act operating under NEMA's umbrella (e.g., Air Quality Act, Waste Act, Protected Areas Act, Biodiversity Act).
- **Regulations**: the operational rules implementing an Act's provisions.
- **Codes**: standards issued by professional/industry bodies (ECSA, SAICE, etc.); may be voluntary or contractually binding, but do not remove common-law negligence liability.
- **By-laws**: district/municipal-specific rules made under the authority of a national Act (e.g., City of Johannesburg's Municipal Planning By-law).

**3. Main concepts**
- Triple A weighting table:

| Triple 'A' Criteria | Technical | Environmental | Institutional | Legal | Financial | Total weighting |
|---|---|---|---|---|---|---|
| Appropriate | 50% | 50% | – | – | – | 25% |
| Applicable | – | – | 50% | 50% | – | 25% |
| Affordable | – | – | – | – | 100% | 50% |

- Four categories of identified project risk: **Technical** (e.g., incompatible technology, insufficient/inconsistent feedstock, lack of qualified professionals); **Institutional** (e.g., lack of capacity, political instability); **Environmental & Legal** (e.g., operating without required regulatory permits); and a second, financially-focused set of examples also labelled "Environmental & Legal" in the source (e.g., liquidity issues, construction delays, overstated sales assumptions, adverse FOREX movements, interest rate risk) — students should note this labelling overlap/inconsistency in the source material itself.
- South African regulatory hierarchy (top to bottom): Constitution of the RSA, 1996 (Sections 22, 23, 24 — supreme law) → national Acts (four groups, see below) → Regulations within Acts (e.g., NEMA's "polluter pays" Environmental Regulations) → professional regulatory-body codes → municipal by-laws → technical standards (SANS/ISO) and common law.
- Four groups of national Acts:
  - *Professional Regulation and Procurement*: Council for the Built Environment Act 43 of 2000; Engineering Profession Act 46 of 2000.
  - *Environmental & Resource Acts*: NEMA 107 of 1998 (guides EIAs); National Water Act 36 of 1998; Carbon Tax Act 15 of 2019; Climate Change Act 22 of 2024; NEMAQA 39 of 2004 (Air Quality); NEMWA 59 of 2008 (Waste); NEMPAA 57 of 2003 (Protected Areas); NEMBA 10 of 2004 (Biodiversity); MPRDA (2002, subsurface mining); CARA 43 of 1983; National Forests Act 84 of 1998.
  - *Health and Safety Acts*: OHSA 85 of 1993; Mine Health and Safety Act 29 of 1996; Standards Act 8 of 2008 (gives SABS legal authority to set SANS design codes).
  - *Intellectual Property & Commercial*: Patents Act 57 of 1978; Copyright Act 98 of 1978.
- Built-environment regulatory bodies alongside ECSA: **SACAP** (Architecture), **SACPCMP** (Construction Management), **SACQSP** (Quantity Surveying), **SACPVP** (Property Valuers), **SACLAP** (Landscape Architecture).

**4. Important formulas**
- No numerical formula; the Triple A weighting table (25%/25%/50%, with 50/50 internal splits) is the core scoring "formula" used throughout.
- Case-study scoring method: (1) score each sub-criterion from real evidence; (2) apply 25/25/50 weighting for a composite score; (3) decide pass/fail (proceed / proceed with conditions / reject); (4) compare against the real-world outcome and explain any mismatch.

**5. Processes/steps**
- **Pienaar v ECSA case progression**: complaint lodged (Sept 2021) → ECSA investigator appointed under s.28 → investigator's report (Aug 2022) recommends disciplinary proceedings → Pienaar emigrates to Ireland (Oct 2022) → Pienaar requests cancellation of registration (18 May 2024) → ECSA processes cancellation (20 May 2024) → ECSA notifies him of a disciplinary inquiry ~10 days later (31 May 2024) → Pienaar applies to review/interdict the proceedings; ECSA counter-applies to set aside its own cancellation → court accepts ECSA's broad reading of "investigation" under s.20(3), finds the cancellation unlawful, and rejects the argument that ECSA's mandate stops at South Africa's borders.
- **Case Study Task structure (Medupi/Kusile "Case A" and Shell "Case B")**:
  - *Task A*: list ≥10 distinct facts/issues from the background material; for each, identify the relevant Triple A criterion/criteria and whether it represents something present/working or missing/failed, noting points of reasonable disagreement.
  - *Task B*: score each sub-criterion with evidence-based justification, apply the 25/25/50 weighting, and reach a total weighted score with a decision recommendation (Proceed / Proceed with conditions / Reject).
  - *Task C*: reflective questions — which single criterion scored lowest, and does it alone justify "Reject"? Identify one fact belonging to two criteria at once. Identify one genuinely ambiguous fact. Would you have approved the project in 2007 with only period-appropriate knowledge? Compare your Medupi/Kusile score to your Shell (or REIPPPP/Jasper Solar) score.

**6. Examples**
- **Engineering career/industry examples** (slide 2): intern/graduate engineer → junior engineer → professionally registered engineer (Pr. Eng Tech); employing sectors include oil & gas/energy, chemicals manufacturing, fertiliser/agrochemicals, mineral processing, consumer & life sciences (pharma, biotech, food & beverage, cosmetics, pulp & paper), water/wastewater treatment, construction/EPC, and academia/R&D.
- **Pienaar v ECSA**: engineer tried to cancel ECSA registration mid-investigation to escape disciplinary jurisdiction; court held this unlawful and confirmed ECSA's mandate is not geographically limited.
- **Medupi/Kusile background facts usable for the Case A exercise** (illustrative, not exhaustive — students should extract ≥10 per the task instructions):
  1. *Technical*: Coal-handling design failure — conveyor system damage forced Eskom to truck coal directly from the mine, at times limiting output to ~1/3 of design capacity.
  2. *Technical*: Boiler design flaws produced high temperatures and spray-cooling failures that caused unit trips; required a MHPSA rework program across all 12 units.
  3. *Technical*: Unit 4 hydrogen explosion (9 Aug 2021) during maintenance purging, causing 700 MW capacity loss.
  4. *Environmental*: Both stations are dry-cooled, a design choice driven by limited regional water availability.
  5. *Environmental/Legal*: Repeated Minimum Emission Standards postponement applications under NEMAQA, contested by civil society groups over Highveld respiratory-health harm.
  6. *Environmental/Legal*: Kusile's 2022 flue-gas stack failure led to a temporary regulatory postponement allowing FGD bypass — pollution-abatement technology went unused for an extended period.
  7. *Institutional*: Eskom itself acknowledged it lacked sufficient engineers to execute Medupi, Kusile, its return-to-service programme, and gas projects simultaneously, yet proceeded regardless.
  8. *Institutional*: Labour disputes (2012–2015) caused a cumulative 18 months of program delay, including violent unrest in 2013 and an illegal strike in 2015.
  9. *Legal/Institutional*: Chancellor House (ANC investment arm) held a 25% stake in Hitachi's SA venture at the time Hitachi won the boiler contract; the Public Protector found improper conduct by Eskom's board chair; Hitachi later paid US$19m to settle US SEC bribery charges.
  10. *Financial*: Initial approved cost R69.1bn (2007) rose to independently estimated ~R234bn (Medupi) — roughly 3× the original order-of-magnitude budget; the African Development Bank stated the plant will not earn a financial return over its lifetime.
  11. *Financial*: Public Enterprises Minister stated (2019) South Africans were paying up to four times more for electricity than a decade earlier, attributed significantly to Medupi/Kusile cost overruns.
  12. *Institutional/Legal*: SIU investigation identified ~R4bn in disputed contractor overpayments; a former senior Kusile manager was arrested over an alleged bribe linked to a R745m contract.
- **Shell (Case B)**: parallel case-study exercise using the WWF "Risky Business" report, to be scored with the same Triple A method.

**7. Important points to remember**
- The Triple A framework is not just conceptual — it is a literal weighted-scoring tool (25/25/50) that the course expects students to apply numerically to real case studies.
- "Appropriate," "Applicable," and "Affordable" map onto specific sub-criteria pairs — mixing these up (e.g., putting Legal under Appropriate instead of Applicable) is an easy mistake to guard against.
- South Africa's regulatory structure is hierarchical: Constitution → Acts → Regulations → professional codes → by-laws → standards/common law — and compliance with a lower tier (e.g., a code) does not remove liability under a higher one (e.g., common-law negligence).
- The Pienaar case establishes that ECSA's disciplinary jurisdiction cannot be defeated by voluntary deregistration once an investigation/disciplinary process is underway, and that ECSA's protective mandate is not limited to practitioners working within South Africa.
- The Medupi/Kusile case is designed to show that a Triple A score computed with 2007-era information may not match the real-world outcome — a key point for the Task C reflection questions about hindsight versus foresight.

**8. Potential test questions**
- Explain the "systems approach" to engineering decision-making and why all five systems (technical, environmental, institutional, legal, financial) must be satisfied simultaneously.
- Reproduce the Triple A weighting table from memory and apply it to score a short case scenario.
- List the four categories of South African engineering-relevant legislation and name at least one Act in each.
- Explain the "polluter pays" principle and how NEMA's Regulations enforce it.
- Summarise the facts and legal holding of Pienaar v ECSA — specifically, what did the court decide about the scope of "investigation" under section 20(3) of the Engineering Profession Act?
- Apply the Triple A scoring method (Tasks A, B, and C) to the Medupi/Kusile case study, using specific facts from the background material as evidence.
- Compare your Triple A analysis of Medupi/Kusile against Shell (Case B) or another named project — what does the comparison suggest about the relationship between urgency and long-term project outcomes?
