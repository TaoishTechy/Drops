# THE HOLLOW — France Application v1.1

## An Attribution-Structure Framework for the Senate Protest-Liability Bill

**Status:** Application of THE HOLLOW v2.0 (revised). Supersedes no prior France document. The four source-reported claims, the five axioms, and the fault tree in the input text are treated as Track A (cited journalism) and Track B (testable legal hypotheses), not as established findings.

---

## Preamble: what is different from Portugal

The Portugal application modeled an **access** hollow: a gap between what households need and what the housing stock makes reachable. The France application models an **attribution** hollow: a gap between what the state can prove about individual conduct and what the state proposes to make individuals pay for.

The structural machinery is the same — typed substrates, capacity and goal predicates, bipartite graphs, diagnostics with falsifiers. The *type* of hollow is different, and the framework's first obligation is to say so. Confusing the two is exactly the failure the audit (points 97–108) identified in the Portuguese H₀/H₁ mapping. A vacant unit is not a homology class; a bystander is not a co-conspirator.

The specific structural question this document asks:

> **Given the Senate text as reported, what is the size and shape of the set of persons who could be made liable without a proven causal connection to the damage they are asked to pay for — and what safeguards, if any, bound that set?**

That is a measurable question. The framework's job is to make it measurable, to state what would falsify the answer, and to refuse to convert the measurement into a constitutional verdict.

---

## §1 The primitive: the attribution hollow

**Definition 1.1 (attribution hollow).** An attribution hollow is a quadruple

$$A = (P, D, E, L)$$

where:
- $P$ is a finite set of **persons** — individuals present at, or accused of participating in, an event,
- $D$ is a finite set of **damages** — specific harms with a measurable cost and a specific time and location,
- $E$ is an **evidence structure** — what can be proved, by admissible means, about each person's conduct, knowledge, and connection to each damage,
- $L$ is a **liability rule** — the legal predicate that determines which persons are made to pay for which damages.

The **attribution hollow** is the pair

$$A^* = (L \setminus E, \partial)$$

where $L \setminus E$ is the set of liability attributions not supported by evidence of a causal connection, and $\partial$ is the **interface** — the subset of persons and damages on which the liability rule and the evidence structure are jointly defined.

Three types are distinguished, and the France application uses all three:

| Type | Substrate | Gap is between |
|---|---|---|
| **Causal-attribution hollow** | Person × Damage | Proven causation vs. attributed liability |
| **Knowledge-attribution hollow** | Person × Fact | Proven knowledge vs. presumed knowledge |
| **Membership-attribution hollow** | Person × Group | Proven membership vs. presumed membership |

The Senate bill, as reported, implicates all three. Axiom #1 in the input text ("shared coordinates do not prove shared intent") is the causal-attribution hollow. Axiom #3 ("a police warning is evidence, not a magical guilt ray") is the knowledge-attribution hollow. Axiom #2 ("jointly liable ≠ personally guilty") is the membership-attribution hollow. The framework treats these as distinct, because the safeguards that bound one do not automatically bound the others.

**Definition 1.2 (representation map).** An attribution hollow is *instantiated* by a data structure — an incident ledger, a set of witness statements, a set of video records, a set of police reports, a set of court filings — and a map $\rho$ that assigns each record to a component of $P$, $D$, $E$, or $L$. A hollow without a representation map is not a model; it is a legal theory.

This is the audit's Discipline 2 applied to the France case. The input text supplies the representation map informally: persons = attendees; damages = property destruction; evidence = what can be shown; liability rule = the Senate text. The framework makes this formal and requires the source of each element to be declared.

---

## §2 Claim ledger and Track discipline

Every claim in this application carries the five fields of v2.0 §2: type, track, evidence, scope, falsifier. The ledger entries below are illustrative of the discipline; a full application would list every claim.

| # | Claim | Type | Track | Evidence | Falsifier |
|---|---|---|---|---|---|
| F1 | The Senate advanced a bill on 28 Oct 2026 proposing joint liability up to €10,000 | report | A | cited (input text, with disclaimer) | A different text is passed |
| F2 | The bill makes specified benefits recoverable | report | A | cited | The enacted text omits this |
| F3 | The bill targets online content with 24-hour takedown provisions | report | A | cited | The enacted text omits this |
| F4 | "Shared location ≠ shared intent" | legal principle | A | ECHR Art. 11 jurisprudence; French constitutional review | A court holds otherwise |
| F5 | Joint liability without proof of individual causation may chill peaceful assembly | hypothesis | B | testable via attendance data | Attendance is unchanged in treated jurisdictions |
| F6 | Benefit recovery may push household members below an adequate standard of living | hypothesis | B | testable via benefit and poverty-line data | Households remain above the threshold |
| F7 | The 24-hour takedown rule may be overbroad | hypothesis | B | testable via content-classification audit | Oversight data show narrow application |
| F8 | The bill, if enacted, would likely face constitutional and ECHR challenge | hypothesis | B | comparative jurisprudence | The bill passes review without challenge |
| F9 | "Reality is the homotopy type of a hollow" | ontology | C | none | none (not falsifiable) |

F9 is included only to demonstrate the discipline: it appears in the ledger, is labeled Track C, and is not used to justify any Track A or B claim. This is the v2.0 rule.

---

## §3 Track A: the established legal and mathematical content

The following is the *complete* inventory of established content used in this application. Anything not on this list is Track B or Track C.

### §3.1 The legal framework (Track A, established)

- **French constitutional protection of assembly and expression.** The Conseil constitutionnel has repeatedly held that freedom of expression and freedom of assembly are fundamental rights; restrictions must be necessary, adapted, and proportionate to the aim pursued. This is Track A: it is established constitutional doctrine.
- **ECHR Article 11 (peaceful assembly).** Restrictions must be prescribed by law, pursue a legitimate aim, be necessary in a democratic society, and be proportionate. The European Court of Human Rights has held that the presence of a person at a demonstration does not, by itself, establish that the person is part of a violent group.
- **ECHR Article 10 (expression).** Restrictions must satisfy the same four-part test. The Court has distinguished incitement from documentation, satire, and political rhetoric.
- **French civil liability (Code civil, art. 1240 et seq.).** Liability in French civil law requires proof of fault, damage, and causal link. A rule that establishes liability without proof of causation is a departure from the ordinary regime and requires a specific legal basis.
- **The principle of individual responsibility in criminal and civil law.** A person is liable for their own acts and, in limited cases, for acts they directed or authorized. Liability for the acts of others requires a specific legal foundation (e.g., parental liability, employer liability), each with its own conditions.
- **The principle of proportionality in benefit recovery.** Social benefits are protected by the French Constitution and by the ECHR's property guarantee (Protocol 1, Art. 1); recovery must be proportionate and must not deprive a person of the minimum necessary for an adequate standard of living.

None of these is a finding that the bill is unlawful. They are the standards against which the bill would be reviewed. The framework's Track A is the *standard*; the bill is the *object* of review.

### §3.2 The mathematical content (Track A, established)

The following are the only mathematical results used in this application, with hypotheses stated:

- **Bipartite graphs and Hall's marriage theorem.** A bipartite graph $G = (P, D, E)$ has a matching saturating $P$ iff for every subset $S \subseteq P$, $|N(S)| \geq |S|$. Used to model which persons can be assigned to which damages without conflict.
- **Connected components.** The number of connected components of a graph is the number of distinct "incident groups" — persons linked to each other through shared damages. This is the graph-theoretic analog of "membership in a group."
- **Persistent homology of graph filtrations.** As the evidence threshold (e.g., the required strength of proof) is varied, the connected-component count changes. The persistence of a component measures how robust the "group" is to changes in the evidence standard. This is a Track A computation on a Track B model.
- **Torsion in the integral homology of a graph.** For any graph, $\beta_1$ is torsion-free, so the $\mathbb{Q}$-rank equals the $\mathbb{F}_2$-rank. A torsion diagnostic on a graph is identically zero. This is a **negative result**: it tells the framework that topological torsion cannot be used to model group-membership ambiguity in this case. A non-zero torsion diagnostic would be a schema error, not a discovery.

There are **no** established mathematical results that connect homotopy invariants to legal or ethical facts. That connection is Track C.

### §3.3 What is not on the Track A list

- The claim that "jointly liable" is a homological operation.
- The claim that "police warnings" are a covering-space projection.
- The claim that "the crowd" is a $\pi_1$ object.
- The claim that the bill's constitutionality can be determined by topology.

These are not demoted; they are removed from the framework's load-bearing content. They may appear as Track C text, in italics, with the caveat that they are illustrative only.

---

## §4 Track C: the ontology, quarantined

The Hollow ontology (v1.0, revised) is a Track C layer. It is retained because it gives a language for describing the shape of the attribution hollow — the gaps, the interfaces, the persistence of structures as evidence standards change. It is not retained as a source of legal conclusions.

**The Track C hypothesis, stated precisely:**

> There exists a family of interpretations in which systems of interest (physical, legal, social) are usefully modeled as structured absences — as the data $A = (P, D, E, L)$ of Definition 1.1 — and in which the structural invariants of $A$ (its connected components, its persistence under evidence-threshold variation, its matching deficiency) are correlated with observable properties of the legal system (its chilling effect, its error rate, its distributional impact).

This is a hypothesis. It is locally testable — the France v0.1 model below states the tests — and it is usually false as a general claim. The framework proceeds as if the general hypothesis were false and the local hypotheses were the only ones that matter.

**Illustrative Track C correspondences** (italicized, not load-bearing):

- *The attribution hollow is the complement of a matching: damages that cannot be matched to a proven cause.*
- *The persistence of a connected component as the evidence threshold varies is the "robustness" of the group-membership claim.*
- *The interface $\partial$ — the set of persons and damages on which liability and evidence are jointly defined — is where the safeguards operate.*

These are useful as exposition. They do not establish any legal conclusion.

---

## §5 Track B: the attribution model

This is the working surface. Everything here must have a representation map, a schema, a falsifier, and a baseline.

### §5.1 Canonical schema

**Nodes:**
- **Person**: `id`, **status** (attendee / identified-participant / identified-violent-participant / accused / charged / convicted), **presence_evidence** (photo / video / witness / police report / self-report), **knowledge_evidence** (what can be shown about what they knew), **voluntary_choice_evidence** (what can be shown about their ability to leave), **benefit_status** (which benefits are recoverable), provenance, uncertainty
- **Damage**: `id`, **type** (property / injury / other), **cost**, **location**, **time**, **causal_evidence** (what can be shown about who caused it), provenance, uncertainty
- **Evidence**: `id`, **type** (video / witness / police report / forensic / digital), **admissibility** (admissible / contested / excluded), **reliability** (high / medium / low), provenance
- **Warning**: `id`, **type** (police dispersal / loudspeaker / written), **audibility_evidence**, **clarity_evidence**, **time**, **location**, **legal_basis**, provenance, uncertainty

**Edges:**
- **(person, damage) causal**: exists iff there is admissible evidence that the person caused the damage
- **(person, damage) liability**: exists iff the legal rule makes the person liable for the damage
- **(person, warning) present**: exists iff there is evidence the person was present and able to hear/see the warning
- **(person, person) group**: exists iff there is evidence the persons acted as a coordinated group (not merely co-present)

Every edge carries provenance and uncertainty. This implements the audit's Discipline 3 (data model).

### §5.2 The three predicates

The bill's liability rule is modeled as a conjunction of three predicates, each of which can be independently tested:

**Predicate 1 (knowledge).** $\kappa(p, d)$: the person knew that violence, theft, or damage was occurring in the vicinity of the damage. The framework requires evidence of $\kappa$; it does not presume $\kappa$ from presence.

**Predicate 2 (voluntary participation).** $\nu(p, d)$: the person voluntarily remained in the gathering after the legally specified warnings, and had a meaningful opportunity to leave. The framework requires evidence of $\nu$; it does not presume $\nu$ from presence, and it explicitly includes the exclusions the bill itself specifies (legitimate reason to remain, disability, journalistic duty, blocked exits).

**Predicate 3 (specified circumstances).** $\sigma(p, d)$: the damage occurred within the circumstances the bill specifies (location, time window, group definition). The framework requires that the circumstances be declared and that the person's connection to them be evidenced.

The bill's liability rule is then:

$$L(p, d) \iff \kappa(p, d) \land \nu(p, d) \land \sigma(p, d)$$

**The critical structural fact** is that this rule, as reported, does *not* require causal attribution. A person can satisfy $\kappa$, $\nu$, and $\sigma$ without having caused $d$. The attribution hollow is exactly the set of $(p, d)$ pairs where $L(p, d)$ holds but no causal edge exists. The size of this set is the measure of the bill's breadth.

### §5.3 Diagnostics

For an incident ledger instantiated under §5.1:

- **S1 (causal-support rate).** The fraction of liability attributions that have a causal edge. A rate of 1.0 means no hollow; a rate of 0.0 means every attribution is without proven causation.
- **S2 (knowledge-evidence rate).** The fraction of liability attributions for which $\kappa$ is supported by admissible evidence, rather than presumed.
- **S3 (voluntary-choice-evidence rate).** The fraction of liability attributions for which $\nu$ is supported by evidence of a meaningful opportunity to leave.
- **S4 (group-identification rate).** The fraction of liability attributions for which the "group" is identified by more than co-presence.
- **S5 (benefit-impact distribution).** The distribution of benefit recovery amounts across affected households, compared to the poverty line and the adequate-standard-of-living threshold.
- **S6 (chilling effect).** The change in lawful-demonstration attendance in jurisdictions where the bill applies, relative to a matched comparison, controlling for the demonstration's subject and size.
- **S7 (content-classification error).** For the 24-hour takedown provision, the fraction of takedown requests that, on independent review, targeted protected expression rather than unlawful incitement.

Each diagnostic is paired with a predeclared falsifier:

| Diagnostic | Falsifier |
|---|---|
| S1 | If S1 ≥ 0.9 in practice, the attribution hollow is small and the "punishment by association" concern is overstated for that dataset |
| S2 | If S2 ≥ 0.9, knowledge is generally proved, not presumed |
| S3 | If S3 ≥ 0.9, voluntary-choice evidence is generally available |
| S4 | If S4 ≥ 0.9, the "group" is generally identified by evidence, not co-presence |
| S5 | If the post-recovery household income remains above the adequate-standard threshold for ≥95% of affected households, the family-protection concern is bounded |
| S6 | If attendance is unchanged in treated vs. comparison jurisdictions, the chilling hypothesis is rejected |
| S7 | If independent review finds ≥95% of takedown requests target unlawful incitement, the overbreadth concern is bounded |

These implement the audit's Discipline 4 (falsifiability).

### §5.4 Baselines

The Hollow attribution model is compared against three baselines:

- **Baseline 1: simple proximity.** Every person present is liable for every damage. This is the "collective punishment" baseline. S1 = 0, S2 = 0, S3 = 0, S4 = 0.
- **Baseline 2: strict causation.** Only persons with a proven causal edge are liable. This is the ordinary civil-liability baseline. S1 = 1, S2 = 1, S3 = 1, S4 = 1.
- **Baseline 3: group-liability.** Persons who are proven members of an identified violent group are liable for the group's damages. S1 < 1 (membership ≠ individual causation for every damage), S4 = 1 (group proven).

**The Hollow model is retained only if it occupies a position between Baseline 1 and Baseline 2 that is defensible on the bill's own terms** — that is, only if its S1–S4 values are demonstrably higher than Baseline 1's and its S5–S7 safeguards are demonstrably stronger than Baseline 1's. If the model's practical effect is indistinguishable from Baseline 1, the Hollow framework has added nothing and the bill should be evaluated on Baseline 1's terms (which are likely unconstitutional). If the model's practical effect is indistinguishable from Baseline 2, the bill's joint-liability provision is doing no work and should be struck as redundant.

This is the framework's most important discipline: **the Hollow model must earn its place between the two baselines, or be simplified to one of them.**

---

## §6 France v0.1 application

### §6.1 What the source data supports

The input text supplies the following, all Track A (cited journalism) unless marked:

| Claim | Status |
|---|---|
| Senate advanced the bill at first reading on 28 Oct 2026 | cited; further review pending |
| Joint liability up to €10,000 for specified conduct | cited |
| Liability routes include continued voluntary participation after warnings, with knowledge of violence/theft/damage | cited |
| Exclusions for legitimate reasons to remain | cited |
| Benefits (housing assistance, family allowances) recoverable | cited |
| Online content provisions with 24-hour takedown | cited (details of oversight not supplied) |
| French constitutional protection of expression and assembly | Track A (established doctrine) |
| ECHR Arts. 10 and 11 standards | Track A (established treaty) |
| Code civil art. 1240 et seq. requires fault, damage, causation | Track A (established law) |
| The bill's compatibility with these standards is unsettled | Track A (correct statement of the legal position) |

### §6.2 What the source data does not support

The following are Track C or simply unsupported and are removed from the model:

- **"Shared coordinates = shared intent" is a homological identity.** It is not. It is a legal principle (ECHR Art. 11 jurisprudence) stated in Track A. The homological language is illustrative only.
- **"The police warning is a covering-space projection."** It is not. It is a factual and legal question about audibility, clarity, and opportunity to comply.
- **"The crowd is a $\pi_1$ object."** It is not. A crowd is a set of persons with a spatial and temporal relation; it has no natural fundamental group, and none is used in the model.
- **"The 60/11 ratio" or its French analog is the degree of a cover.** Any such ratio is a discrepancy rate between two counts with different definitions. It is a Track B measurement problem, not a topological invariant.

### §6.3 The five-layer model

**Layer 1 — Incident ledger.** The schema of §5.1, populated from police reports, video evidence, witness statements, and court filings. Missing data is marked missing, not zero.

**Layer 2 — Attribution graph.** The bipartite graph $G = (P, D, E)$ of §5.2, with the three predicates evaluated.

**Layer 3 — Diagnostics.** S1–S7 of §5.3, computed for each incident and aggregated at the jurisdiction level.

**Layer 4 — Legal evaluation.** The Track A standards (constitutional, ECHR, Code civil) applied to the Layer 3 diagnostics. This is a legal analysis, not a topological one. The framework supplies the inputs; the legal evaluation supplies the conclusion.

**Layer 5 — Track C interpretation.** Only after Layers 1–4, ask whether the pattern is usefully described as an attribution hollow. The interpretation must add explanatory or predictive value to remain in the model.

### §6.4 Predeclared predictions (v0.1)

Written before outcome data are inspected, as required by Discipline 4:

1. **S1 prediction.** In the first year of implementation (if enacted), S1 will be low — below 0.3 for the class of persons accused solely on the basis of continued presence after warnings.
   - **Falsifier:** If S1 ≥ 0.5, the bill is applied mostly to persons with proven causal connection, and the attribution-hollow concern is bounded.

2. **S5 prediction.** For households receiving housing assistance or family allowances, recovery amounts will in some cases exceed the amount by which the household's income exceeds the adequate-standard-of-living threshold.
   - **Falsifier:** If recovery is systematically capped below that amount for ≥95% of households, the family-protection concern is bounded.

3. **S6 prediction.** Lawful demonstrations on contested political topics will show a measurable attendance decline in jurisdictions where the bill applies, relative to matched comparison jurisdictions.
   - **Falsifier:** If attendance is statistically indistinguishable, the chilling hypothesis is rejected.

4. **S7 prediction.** Independent review of takedown requests will find that a non-trivial fraction (≥5%) target protected expression rather than unlawful incitement.
   - **Falsifier:** If the fraction is <1% across a representative sample, the overbreadth concern is bounded.

5. **S4 prediction (negative).** If the bill's "group" definition is operationalized as co-presence, S4 will be approximately 0 — the group will be identified by the state's presence criterion, not by evidence of coordination.
   - **Falsifier:** If S4 ≥ 0.5, the group is generally identified by evidence, and the membership-attribution concern is bounded.

### §6.5 What the model cannot do

Stated explicitly, as required by Discipline 5:

- The model cannot determine whether the bill is **unconstitutional**. That is the Conseil constitutionnel's question, under the Track A standards.
- The model cannot determine whether the bill violates the **ECHR**. That is the Strasbourg court's question.
- The model cannot determine whether the **24-hour takedown provision** is lawful under Article 10. That requires a content-by-content review that no structural model can perform.
- The model cannot determine whether a specific person **knew** what was happening around them. That is a factual question for the trier of fact, based on evidence.
- The model cannot determine whether a specific person had a **meaningful opportunity to leave**. That is a factual question, and it is the heart of the voluntary-participation predicate.

The framework supplies structure. The legal system supplies judgment. The framework's value is in making the structure of the judgment explicit and the falsifiers of the structural claims predeclared.

---

## §7 Theorem registry (France application)

| # | Theorem | Hypotheses | Application |
|---|---|---|---|
| F1 | Hall's marriage theorem | bipartite graph | §5.3, S1–S4 (matching deficiency) |
| F2 | Connected components of a graph | graph | §5.3, S4 (group identification) |
| F3 | Persistent homology of a graph filtration | filtration, coefficient ring | §5.3, S4 (robustness of group identification) |
| F4 | Torsion-free $\beta_1$ for graphs | graph | §3.2, negative result: torsion diagnostic is zero |
| F5 | ECHR proportionality test (four-part) | treaty, jurisprudence | §3.1, legal standard |
| F6 | French constitutional proportionality review | constitutional doctrine | §3.1, legal standard |
| F7 | Code civil art. 1240 et seq. (fault, damage, causation) | statute, jurisprudence | §3.1, ordinary liability baseline |

No theorem is used outside its hypotheses. No theorem is used to derive a legal conclusion without the legal analysis of §6.3 Layer 4.

---

## §8 Release gates (France application)

| Gate | Acceptance test |
|---|---|
| **Legal** | Every legal claim is sourced to the constitutional text, a treaty, a statute, or a published judicial decision |
| **Mathematical** | Every formula passes review; every theorem in the registry states its hypotheses |
| **Semantic** | Every real-world variable (knowledge, voluntary participation, group) has a declared operational definition |
| **Evidence** | Every incident-level claim links to a source with an evidentiary grade |
| **Causal** | The bill's effect on attendance, benefit adequacy, and content moderation is evaluated with an identification strategy |
| **Falsification** | Every Track B claim has a predeclared falsifier |
| **Benchmark** | The Hollow model outperforms Baseline 1 (simple proximity) and Baseline 2 (strict causation) on the declared diagnostic tasks, or is simplified to one of them |
| **Replication** | An independent analyst reproduces the S1–S7 diagnostics from the incident ledger |
| **Communication** | Every metaphor is labeled Track C; every legal conclusion is labeled Track A; every testable hypothesis is Track B |

A claim that fails any gate is not "validated." It is "rejected" or "pending."

---

## §9 What was removed, and why

| From the input text | Status in v0.1 |
|---|---|
| Axiom #1 (proximity ≠ personality) | Retained as Track A legal principle, not as a homological identity |
| Axiom #2 (joint liability ≠ personal guilt) | Retained as Track A legal principle; modeled as the causal-attribution hollow |
| Axiom #3 (warning ≠ magical guilt ray) | Retained as Track A legal principle; modeled as the knowledge-attribution hollow |
| Axiom #4 (benefits ≠ infinite debit card) | Retained as Track A constitutional standard; modeled as diagnostic S5 |
| Axiom #5 (24h ≠ complete standard) | Retained as Track A expression standard; modeled as diagnostic S7 |
| "A crowd is not a hive mind" | Retained as Track A principle; the model does not posit a crowd mind |
| "Shared coordinates ≠ shared intent" | Retained as Track A principle; the model requires evidence of intent, not presence |
| "Senate approval ≠ constitutional immunity" | Retained as Track A statement of the legal position; the model does not adjudicate |
| `shared_location ≠ shared_intent` (slogan form) | Retained as Track C signature; not used in argument |
| Any claim that topology adjudicates the legal question | Removed; the model supplies structure, not verdicts |

The three attribution-hollow types (causal, knowledge, membership) are v0.1's principal contribution. They separate concerns that the input text's five axioms separate legally but not structurally. The framework's value is in making the separation formal, so that a safeguard for one type is not mistaken for a safeguard for another.

---

## §10 The next milestone

The next deliverable is not a longer document. It is a small, executable benchmark.

**Hollow France v0.1 Attribution Benchmark.**

1. A public dataset of reported incidents, with the schema of §5.1, drawn from court filings, police reports, and (where admissible) witness statements, with evidentiary grades.
2. An implementation of S1–S7 of §5.3.
3. A Baseline 1 (simple proximity) implementation and a Baseline 2 (strict causation) implementation.
4. A pre-registered prediction task — e.g., for each incident, predict which persons will be made liable under the enacted rule, and compare to the set with a causal edge.
5. A comparison report: does the Hollow model add diagnostic value beyond the two baselines? By how much? With what confidence interval?
6. A public dataset of the comparison, with the pre-registration archived.

If the Hollow model adds diagnostic value, retain the framework. If it does not, simplify to Baseline 2 (strict causation) — which is the ordinary civil-liability rule, and which the bill's joint-liability provision exists to depart from. **The framework's credibility depends on being willing to conclude that the bill, if it does not outperform Baseline 2, should be evaluated on Baseline 2's terms.**

That is not a political conclusion. It is a methodological one, and it is the only conclusion a structural framework is entitled to reach.

---

## Appendix A: The three attribution hollows, stated plainly

**Causal-attribution hollow.** The state proposes to make person $p$ pay for damage $d$ without proving that $p$ caused $d$. The framework asks: for what fraction of $(p, d)$ pairs does this occur? (Diagnostic S1.)

**Knowledge-attribution hollow.** The state proposes to make person $p$ pay for damage $d$ on the basis of what $p$ should have known, without proving what $p$ did know. The framework asks: for what fraction of pairs is knowledge evidenced rather than presumed? (Diagnostic S2.)

**Membership-attribution hollow.** The state proposes to make person $p$ liable for the group's damages without proving that $p$ was a member of the group rather than a co-present bystander. The framework asks: for what fraction of pairs is group membership evidenced by more than co-presence? (Diagnostic S4.)

These three are distinct. A safeguard that bounds one does not automatically bound the others. The framework's principal contribution is to keep them distinct.

## Appendix B: The five axioms, restated as diagnostics

| Axiom | Structural form | Diagnostic |
|---|---|---|
| #1 Proximity ≠ personality | Presence does not entail participation | S1 |
| #2 Joint ≠ personal | Liability does not entail causation | S1 |
| #3 Warning ≠ guilt ray | Warning does not entail knowledge or voluntary choice | S2, S3 |
| #4 Benefits ≠ debit card | Recovery must not push households below an adequate standard | S5 |
| #5 24h ≠ complete standard | Takedown must target incitement, not protected expression | S7 |

The framework does not say whether the safeguards are adequate. It says what would count as evidence that they are, and what would count as evidence that they are not. That is what a structural framework can do, and what it cannot do is decide the constitutional question.

## Appendix C: The slogan, for the record

`shared_location ≠ shared_intent` is a Track C signature. It is true as a slogan, it is supported by Track A legal principles, and it is not a homological identity. The framework records it here, in the appendix, where it cannot be mistaken for a result.

The result is in §5.3. The slogans are in Appendix C. The distinction between them is the framework's discipline.
