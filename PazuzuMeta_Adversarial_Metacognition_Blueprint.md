# PAZUZUMETA 1.0

## Adversarial Metacognitive Control Architecture  
### PazuzuCore 2.0 Shell + Game-Theoretic Strategy Layer

| Field | Value |
|---|---|
| Version | 1.0 |
| Basis | PazuzuCore 2.0 outer shell (critical band, receding-horizon MPC, typed Merkle ledger, Pareto hypervolume, triple-signature diagnostics) |
| Scope | Pure metacognition: monitor, model, commit, conceal, revise. **No parameter training.** |
| Domain | Closed-world multi-agent simulation, tabletop wargame umpires, red-team decision aids |
| Non-goals | Weapons design, targeting of persons, network intrusion, real-world covert action |
| License posture | Specification only; any implementation must keep effectors offline |

---

## 0. Design law

PazuzuCore already separates a **control shell** from an **inner engine**. This blueprint keeps that split and replaces the inner “96 φ-enhancements” catalog with a smaller set of **falsifiable metacognitive operators**.

Golden-ratio constants are **not** used as a universal spice. Where a scale factor is required it is a calibrated hyperparameter \(\phi \in [1.2, 1.8]\), default \(\varphi = (1+\sqrt{5})/2\), and every claim that depends on it has a disable-switch and a null model with \(\phi = 1\).

Mythic names (Pazuzu, rite, fog) are interface labels. Each label maps to a state variable, an estimator, or a constraint.

**Military-grade** here means: append-only provenance, fail-closed band control, deterministic replay, separation of *assess* from *act*, and explicit refusal to bind the controller to live weapons or live networks.

**Machiavellian** here means: nested opponent models, preference concealment, coalition value, and commitment credibility — the standard toolkit of incomplete-information games — not a doctrine for harming people.

---

## 1. Layer map

```
┌─────────────────────────────────────────────────────────────┐
│  LEDGER & GOVERNANCE                                        │
│  Typed Merkle axioms • snapshots • kill / freeze • audit    │
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│  PAZUZU SHELL                                               │
│  Critical band on λ_meta • MPC • parity gate • Pareto HV    │
│  Triple signature: spectral + slowing + variance            │
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│  METACOGNITIVE CORE (this document)                         │
│  Self-model  •  Opponent tower  •  Fog / VOI                │
│  Commitment field  •  Signaling / concealment               │
│  Coalition tensor  •  Tempo / OODA residual                 │
│  Strategy simplex  •  Irreversibility ledger                │
└─────────────────────────────────────────────────────────────┘
                              │
┌─────────────────────────────────────────────────────────────┐
│  SANDBOX WORLD (optional)                                   │
│  Abstract extensive-form game, not a physical battlespace   │
└─────────────────────────────────────────────────────────────┘
```

There is **no training loop**. Adaptation is:

1. Bayesian update of nested models,
2. receding-horizon choice of a strategy weight vector,
3. optional irreversible commitment recorded on the ledger.

Weights are not gradient-descended against a loss on data. They are solved as a constrained control problem each cycle.

---

## 2. State

### 2.1 Self metacognitive state

\[
\mathbf{s}_{\text{self}} = \bigl(
\hat{\pi},\;
\kappa,\;
c,\;
\mathbf{u},\;
\rho,\;
\iota,\;
\tau
\bigr)
\]

| Symbol | Meaning | Type |
|---|---|---|
| \(\hat{\pi}\) | Current mixed strategy over a finite action catalog \(\mathcal{A}\) | simplex \(\Delta(\mathcal{A})\) |
| \(\kappa\) | Calibration of own confidence vs. realized outcome | \([0,1]\) |
| \(c\) | Coherence (phase-lock of internal modules, Pazuzu \(C_t\)) | \([0,1]\) |
| \(\mathbf{u}\) | Resource / energy / attention budget | \(\mathbb{R}_+^k\) |
| \(\rho\) | Reputation / revealed type (what others are estimated to believe) | simplex over types |
| \(\iota\) | Irreversibility mass (committed options already burned) | \([0,1]\) |
| \(\tau\) | Decision-cycle time (OODA residual) | seconds or ticks |

### 2.2 Opponent tower (level-\(k\))

For each opponent \(j\) and nesting depth \(k = 0,\dots,K\):

\[
M_j^{(k)} = \bigl( \hat{\theta}_j^{(k)},\; \hat{\pi}_j^{(k)},\; \hat{u}_j^{(k)},\; \omega_j^{(k)} \bigr)
\]

- \(k=0\): opponent treated as a stationary distribution (fictitious play prior).
- \(k=1\): opponent is a best response to \(k=0\).
- \(k\ge 2\): opponent is a best response to \(M^{(k-1)}\).

Depth \(K\) is **not** grown without bound. Cost of one extra level is charged against the attention budget (formula M-04). Default \(K\le 3\).

### 2.3 Fog state

\[
\mathbf{f} = \bigl( H(W),\; I(\text{self};W),\; D_{\mathrm{KL}}(P_{\text{true}}\|P_{\text{bel}}),\; \chi \bigr)
\]

\(W\) is the hidden world state. \(\chi\) is a concealment effort allocated by self or inferred in others.

### 2.4 Jacobian for the Pazuzu band

Metacognitive dynamics are written in Pazuzu form:

\[
\dot{\mathbf{x}} = \bigl[\mathbf{J}_0 + \mathbf{M}_{\text{PZ}}(\mathbf{x},\boldsymbol\theta_{\text{PZ}}) + \mathbf{M}_{\text{META}}(\mathbf{x},\boldsymbol\theta_{\text{M}})\bigr]\mathbf{x} + \boldsymbol\eta
\]

\(\mathbf{x}\) concatenates \((\mathbf{s}_{\text{self}}, \{M_j^{(k)}\}, \mathbf{f}, \hat{\pi})\).

The **metacognitive dominant eigenvalue** \(\lambda_{\text{meta}}\) is the largest real-part mode of the linearized update of \((\hat{\pi}, \kappa, \mathbf{f})\). The shell enforces

\[
\lambda_{\min} < \lvert \operatorname{Re} \lambda_{\text{meta}} \rvert < \lambda_{\max}.
\]

Interpretation:

- below \(\lambda_{\min}\): freeze / rumination (no strategy revision),
- inside band: adaptive revision,
- above \(\lambda_{\max}\): panic switching; parity gate forces exploit-only or freeze.

This is the Pazuzu critical band applied to **decision revision rate**, not to a quantum Hamiltonian.

---

## 3. Operator catalog (metacognitive laws)

Each operator has: inputs, equation, units, fail condition, null model.

### M-01  Metacognitive residual

Prediction error on *one’s own last forecast*, not on the world.

\[
r_t = \lVert \hat{y}_{t\mid t-1} - y_t \rVert_{W_t},\qquad
R_t = \alpha r_t + (1-\alpha) R_{t-1}
\]

\(\hat{y}\) is the self-model’s forecast of own outcome (win probability, resource, revealed type).  
**Fail if** \(R_t\) is replaced by world-task loss. That would smuggle training back in.  
**Null:** \(R_t \equiv 0\) (no self-monitoring).

### M-02  Calibration debt

\[
\kappa_t = 1 - \bigl\lvert \mathbb{E}[\mathbf{1}_{\text{success}} \mid p] - p \bigr\rvert_{\text{binned}}
\]

Brier reliability component. High competence language is forbidden unless \(\kappa\) is reported with it.  
**Fail if** competence is defined as a raw success rate without calibration.

### M-03  Adversarial value of information (AVOI)

Standard VOI, but the downstream decision is a zero- or general-sum best response.

\[
\mathrm{AVOI}(z) = \mathbb{E}_{P(z)}\Bigl[ \max_{\pi} U(\pi; P(W\mid z)) \Bigr] - \max_{\pi} U(\pi; P(W))
\]

minus the information-acquisition cost \(c_{\text{obs}}(z)\) and minus the **leakage penalty** \(\Lambda(\chi_{\text{self}}, z)\): observing can reveal type.

\[
V_{\text{obs}}(z) = \mathrm{AVOI}(z) - c_{\text{obs}}(z) - \Lambda(\chi_{\text{self}}, z)
\]

Observe iff \(V_{\text{obs}} > 0\).  
**Null:** observe at a fixed schedule.

### M-04  Nested-model divergence and depth tax

\[
\Delta_j^{(k)} = D_{\mathrm{JS}}\bigl(\hat{\pi}_j^{(k)}\,\big\|\,\hat{\pi}_j^{(k-1)}\bigr)
\]

Stop increasing \(k\) when \(\Delta_j^{(k)} < \varepsilon_k\) or when

\[
c_{\text{depth}}(k) = c_0\,\phi^{k-1} > u_{\text{attn}}.
\]

This is level-\(k\) reasoning with an explicit compute price. \(\phi\) here is only a cost multiplier.

### M-05  Theory-of-mind residual

\[
\varepsilon_j^{\text{ToM}} = \mathbb{E}\bigl[ D_{\mathrm{KL}}(\pi_j^{\text{act}} \,\|\, \hat{\pi}_j^{(k^\star)}) \bigr]
\]

If \(\varepsilon_j^{\text{ToM}}\) rises, either increment \(k\) (pay M-04) or widen the type prior.  
**Fail if** the system claims “the opponent is understood” while \(\varepsilon_j^{\text{ToM}}\) is unmeasured.

### M-06  Signaling / concealment channel

Treat public action \(a\) as a signal of hidden type \(\theta\).

Separating incentive (Spence / Cho-Kreps intuition, compact form):

\[
U(\theta, a^\star(\theta)) - U(\theta, a^\star(\theta')) \ge \Delta_{\text{mimic}}(\theta,\theta')
\]

Concealment effort \(\chi \in [0,1]\) mixes the signal toward the pooling distribution \(\bar{a}\):

\[
P(a\mid\theta,\chi) = (1-\chi)\,P_{\text{sep}}(a\mid\theta) + \chi\,\bar{P}(a)
\]

Cost of concealment: \(c_\chi(\chi) = \tfrac12 \gamma \chi^2 + \lambda_{\text{rep}} \lVert \rho_t - \rho_{t-1} \rVert\).

**This module does not output social-engineering scripts.** It outputs a weight on *which catalog action is less informative*, inside a declared game.

### M-07  Commitment credibility

A commitment \(C\) to future action \(a\) is an object on the ledger with burnt option set \(B(C)\).

\[
\Gamma(C) = \underbrace{\Pr(\text{follow}\mid C)}_{\text{consistency}} \cdot \underbrace{\frac{\lvert B(C)\rvert}{\lvert \mathcal{A}\rvert}}_{\text{sunk fraction}} \cdot \underbrace{\bigl(1 - \Pr(\text{renegotiate})\bigr)}_{\text{renegotiation risk}}
\]

Credibility rises when options are actually deleted (the cleaned “first blood” idea): an unused action is moved to \(B\) and cannot return without a ledger exception signed by the freeze authority.

**Null:** commitments are cheap talk (\(\Gamma = 0\)).

### M-08  Strategic irreversibility (cleaned rite)

\[
\iota_{t+1} = \iota_t + \eta \frac{\lvert B_{t+1}\setminus B_t \rvert}{\lvert \mathcal{A}\rvert} - \mu \mathbf{1}_{\text{authorized restore}}
\]

\(\iota\) enters the Pazuzu Pareto vector as a *cost* and as a *stabilizer*. High \(\iota\) shrinks \(\Delta(\mathcal{A})\) and lowers \(\lvert \operatorname{Re}\lambda_{\text{meta}}\rvert\) (fewer modes to switch among).

This is path dependence, not identity mysticism.

### M-09  Coalition value (restricted Shapley)

For a feasible coalition set \(\mathcal{S}\) of simulated agents:

\[
\Phi_i(v) = \sum_{S \ni i} \frac{\lvert S\rvert!\,(\lvert N\rvert-\lvert S\rvert-1)!}{\lvert N\rvert!} \bigl( v(S) - v(S\setminus\{i\}) \bigr)
\]

\(v(S)\) is evaluated only on coalitions the sandbox rules allow.  
**Fail if** \(N\) is mapped onto real persons or real units without an ethics gate.

### M-10  Center-of-gravity (information form)

Clausewitz CoG, rewritten as a sensitivity of the opponent value to a feature \(g\):

\[
\mathrm{CoG}_j(g) = \frac{\partial U_j^\star}{\partial g} \Big/ \lVert \nabla_g U_j^\star \rVert
\]

Features \(g\) live in the abstract game: supply node in a hex map, key information channel, a commitment that props up \(\Gamma\).  
**Not** a targeting list for physical systems outside the sandbox.

### M-11  Tempo / OODA residual

\[
\tau_t = t_{\text{observe}} + t_{\text{orient}} + t_{\text{decide}} + t_{\text{act}}
\]

Advantage versus opponent \(j\):

\[
\Theta_j = \log \frac{\tau_j + \varepsilon}{\tau_{\text{self}} + \varepsilon}
\]

The shell uses \(\Theta\) as a state cost in MPC: spend attention to cut \(t_{\text{orient}}\) (M-04, M-05) or cut \(t_{\text{observe}}\) (M-03).

### M-12  Fog index

\[
F = h_1 \frac{H(W)}{H_{\max}} + h_2 \bigl(1 - I(\text{self};W)/I_{\max}\bigr) + h_3 \min\bigl(1, D_{\mathrm{KL}}(P\|Q)/\delta\bigr)
\]

MPC may buy observations only through M-03. It may not invent omniscience.

### M-13  Exploitability gap

\[
\mathcal{E}(\hat{\pi}) = \max_{\pi'} U_{\text{opp}}(\pi', \hat{\pi}) - U_{\text{opp}}(\mathrm{BR}(\hat{\pi}), \hat{\pi})
\]

If \(\mathcal{E}\) is large, own mix is exploitable. Parity gate flips toward mixing / concealment (M-06) rather than pure best response.

### M-14  Preference-concealment capacity

Channel from true type \(\theta\) to public transcript \(T\):

\[
\Xi = I(\theta; T),\qquad \text{objective: keep } \Xi \le \Xi_{\max}
\]

subject to still achieving reservation utility \(\underline{U}\). This is a constrained information-flow problem, not an instruction to lie to humans.

### M-15  Machiavellian Pareto vector (no scalar “dominate”)

Never collapse strategy into a single “dominate” label. Maintain

\[
\mathbf{m} = \bigl( U_{\text{sec}},\; U_{\text{opt}},\; U_{\text{rep}},\; U_{\text{tempo}},\; -\,\Xi,\; -\,\mathcal{E},\; -\,\iota_{\text{excess}} \bigr)
\]

| Component | Meaning |
|---|---|
| \(U_{\text{sec}}\) | Survival / resource floor |
| \(U_{\text{opt}}\) | Option value of unburnt actions |
| \(U_{\text{rep}}\) | Consistency of revealed type with intended type |
| \(U_{\text{tempo}}\) | \(\Theta\) against the strongest modeled opponent |
| \(\Xi\) | Type leakage (minimize) |
| \(\mathcal{E}\) | Exploitability (minimize) |
| \(\iota_{\text{excess}}\) | Irreversibility beyond what \(\Gamma\) requires |

Pazuzu hypervolume \(\mathcal{A} = \mathrm{HV}(S_{\text{Pareto}}) - \mathrm{HV}(S_{\text{baseline}})\) is computed on \(\mathbf{m}\) plus the original five shell metrics \((N, EP, E, C, CI)\) if those are active.

A strategy that maximizes only \(U_{\text{sec}}\) under the name “dominate” is a **metric failure**, not a feature.

### M-16  Receding-horizon strategy program

Each tick solve

\[
\begin{aligned}
\min_{\pi_{0:T-1}} \quad
&\sum_{k=0}^{T-1} \ell(\mathbf{x}_k, \pi_k) + \phi_T(\mathbf{x}_T) \\
\text{s.t.} \quad
&\mathbf{x}_{k+1} = f(\mathbf{x}_k, \pi_k), \\
&\lambda_{\text{meta}}(\mathbf{x}_T) \in [\lambda_{\min},\lambda_{\max}], \\
&\Xi_k \le \Xi_{\max}, \\
&\pi_k \in \Delta(\mathcal{A}\setminus B_k), \\
&\text{no effector outside sandbox}.
\end{aligned}
\]

Stage cost:

\[
\ell = w_r R + w_F F + w_\mathcal{E} \mathcal{E} + w_\tau \tau - w_\Theta \Theta - w_\Gamma \Gamma
\]

Terminal cost \(\phi_T\) penalizes band violation and type leakage.

This **replaces** Pazuzu “retrocausality” the same way the shell already does: with MPC.

### M-17  Parity gate (explore / exploit / conceal)

Reuse Pazuzu hysteresis on coherence \(C_t\), extended with exploitability:

\[
\Pi_{t+1} =
\begin{cases}
+1 & C_t > \theta_+ \;\wedge\; \mathcal{E} < \varepsilon_{\mathcal{E}} \quad \text{(exploit)} \\
0  & F > F_\star \;\vee\; \Xi \text{ near cap} \quad \text{(conceal / observe)} \\
-1 & C_t < \theta_- \;\vee\; \mathcal{E} > \varepsilon_{\mathcal{E}} \quad \text{(mix / explore)} \\
\Pi_t & \text{else}
\end{cases}
\]

Refractory period \(T_{\text{ref}}\) unchanged.

### M-18  Morphodynamic ceiling on strategy churn

\[
\lVert \pi_t - \pi_{t-1} \rVert_1 \le \kappa\bigl(\lvert \lambda_{\text{meta}} \rvert + \epsilon\bigr)
\]

Prevents panic revision when the band is already high. Aligns with Pazuzu’s gradient ceiling.

---

## 4. Cycle (one tick)

1. **Observe (optional).** If \(V_{\text{obs}} > 0\), accept a sandbox observation; update \(P(W)\) and \(M_j^{(k)}\) by Bayes. No gradient step.
2. **Orient.** Compute \(R, \kappa, \varepsilon^{\text{ToM}}, F, \mathcal{E}, \Xi, \Theta, \Phi_i, \mathrm{CoG}\).
3. **Band check.** Estimate \(\lambda_{\text{meta}}\). If outside band \(>10\%\) of a window: freeze \(\pi\), write ledger alert, do not take new irreversible commitments.
4. **Decide.** Solve M-16. Apply M-17 and M-18.
5. **Commit (rare).** If \(\Gamma\) gain exceeds option-value loss, burn actions via M-07/M-08 onto the Merkle ledger.
6. **Act (sandbox only).** Emit \(\pi\) to the game umpire. Record \((s, a, o, R)\) for residual M-01.
7. **Audit.** Triple signature: spectral band, lag-1 autocorrelation of \(R_t\), variance of \(\pi\). Snapshot RNG.

There is no “learn weights from a dataset” step.

---

## 5. Mapping onto PazuzuCore objects

| Pazuzu 2.0 | PazuzuMeta 1.0 |
|---|---|
| \(\mathbf{x}\) qudit amplitudes | concatenated metacognitive state |
| \(\mathbf{J}_{\text{base}}\) | stable default policy (uniform or last committed \(\pi\)) |
| \(\mathbf{M}_{\text{PZ}}\) | band projector, MPC, parity, ceiling |
| \(\mathbf{M}_{\text{HOR}}\) 96 φ-ops | **replaced** by M-01…M-18 |
| Novelty \(N\) | compression of the opponent-tower description length |
| Entropic potential \(EP\) | fog \(F\) (aligned, not identical) |
| Elegance \(E\) | MDL of the active model depth \(K\) and burnt set \(B\) |
| Coherence \(C\) | module phase-lock + calibration \(\kappa\) |
| Criticality index \(CI\) | proximity of \(\lambda_{\text{meta}}\) to band center |
| Typed Merkle ledger | axioms + commitments + burnt options + snapshots |
| Falsification matrix | §7 |
| φ as universal motif | retired except cost slope in M-04 and optional anneal in horizon \(T\) |

HOR Groups V–XII (holographic bounds, anyons, φ-QAOA, AdS/CFT channels, NV-center mapping) are **out of scope**. They do not implement metacognition. If a later build needs a quantum inner engine, it must pass its own falsification suite and must not be wired to M-16’s action port.

---

## 6. “Military-grade” engineering bar

These are software-assurance requirements, not combat requirements.

1. **Deterministic replay.** Fixed seeds, ordered reductions, CPU reference path.
2. **Append-only ledger.** Every commitment, burn, band excursion, and freeze is hashed. Compaction only via signed snapshots.
3. **Fail-closed.** Band violation, ToM residual above cap, or missing umpire heartbeat → \(\pi \leftarrow \pi_{\text{safe}}\) (hold / resign / no-op), never a new irreversible act.
4. **Assess/act split.** Estimators (M-01–M-15) cannot call effectors. Only the sandbox adapter consumes \(\pi\).
5. **No live network, no live targeting bus.** The adapter interface is a local game object.
6. **Red-team metrics.** Exploitability \(\mathcal{E}\), type leakage \(\Xi\), and calibration \(\kappa\) are first-class. A run that prints “agency achieved” without these three is invalid.
7. **Human authority.** Freeze and restore of \(B\) require an external signature. The engine cannot unburn its own options.
8. **Classification of outputs.** Strategy weights are simulation artifacts. They are not orders.

---

## 7. Falsification matrix

| Claim | Falsified if | Action |
|---|---|---|
| Band control of revision rate | \(\lvert \operatorname{Re}\lambda_{\text{meta}}\rvert\) outside band \(>10\%\) of ticks | Freeze; rollback snapshot |
| Nested models improve play | Level-\(K\) loses to level-\(1\) on the same game after 30 matches | Cap \(K=1\); lower depth tax experiment |
| AVOI selects useful observations | Forced-observe schedule matches or beats AVOI utility | Disable M-03 |
| Concealment reduces \(\Xi\) at acceptable \(U\) | \(\Xi\) does not fall when \(\chi\) rises, or \(U < \underline{U}\) | Disable M-06/M-14 |
| Commitments are credible | \(\Gamma\) high but follow-through rate \(< 0.7\) | Treat as cheap talk |
| Irreversibility stabilizes \(\lambda\) | Burning options increases band violations | Stop M-08 |
| Pareto not gamed | HV gain from a single component of \(\mathbf{m}\) only | Use robust HV (\(A_{\text{robust}}\)) |
| “No training” invariant | Any update writes a learned parameter file or backprop tape | Hard fail the build |

Null models required in every report: random mix, fictitious play, myopic best response, and open-loop last-\(\pi\).

---

## 8. Minimal implementation (no training)

Suggested stack, all classical:

- State: dataclass / numpy, as in Pazuzu `SystemState`.
- Beliefs: discrete Bayesian tables or particle sets. \(K\le 3\), \(\lvert \Theta\rvert \le 8\) types, \(\lvert \mathcal{A}\rvert \le 16\) actions.
- MPC: SQP or projected gradient on the simplex, horizon \(T \in [5,15]\).
- Ledger: existing Pazuzu `Axiom` dataclass plus `Commitment` and `Burn`.
- Games for validation: matching pennies with cheap talk; signaling (Spence); colonel blotto (abstract force allocation); a small imperfect-information card game; a hex wargame with hidden units.

Reference tick budget on CPU: \(< 50\,\mathrm{ms}\) at the sizes above. If the tick exceeds \(\tau\) targets, cut \(K\) before adding “quantum acceleration.”

### 8.1 What not to implement first

- 96 HOR enhancements.
- Qualia / sentience scalars.
- Strings named `dominate` as terminal utilities.
- Any API that posts \(\pi\) to a broker, radio, or weapon interface.

---

## 9. Worked micro-example (matching pennies + talk)

Actions \(\mathcal{A}=\{\mathrm{H},\mathrm{T},\mathrm{talk}\}\). Types \(\{\mathrm{balanced},\mathrm{H\text{-}biased}\}\).

1. M-13: a pure H policy has \(\mathcal{E}=1\). Mix toward \(1/2\).
2. M-06: `talk` is a cheap signal. If \(\Gamma\) of “I play H” is low, treat as pooling.
3. M-03: peeking at opponent’s last action has AVOI \(>0\) in non-i.i.d. play, leakage \(\Lambda\) if peeking is public.
4. M-04: \(K=2\) is enough; \(K=5\) is wasted attention.
5. M-16: horizon 8, band on how fast \(\hat{\pi}\) may move (M-18).
6. Report \(\kappa\), \(\mathcal{E}\), \(\Xi\), not an emergence percentage.

If this loop cannot beat fictitious play by a pre-registered margin, the architecture is not ready for a larger wargame.

---

## 10. Relation to prior artifacts in this project

| Prior object | Disposition |
|---|---|
| `RiteOfChoiceAgency` energy / random Bernoulli tasks | Discard as capability evidence. Keep only the *burn unused option* primitive, under M-08 and a human-signed ledger. |
| `dominate` / `conserve` string goals | Illegal as terminal utilities. Replace with vector \(\mathbf{m}\). |
| Alignment PDF (MAGI, T+47.1 h, global decoupling) | Category error. Do not reuse its numbers or recommendations. |
| Sentiflow autograd | Unused. No training. |
| HOR φ-QAOA / anyons / AdS channels | Out of scope for metacognition. |
| Pazuzu critical band, MPC, ledger, Pareto HV, triple signature | **Keep.** These are the only parts that survive an engineering reading. |

---

## 11. Ethical and legal fence

This specification is a **controller for an abstract game**. It is not a plan for:

- attacking persons or infrastructure,
- producing biological, chemical, or explosive effects,
- writing malware or obtaining credentials,
- running influence operations against real populations.

Opponent models may represent *roles in a declared simulation*. They must not be bound to identified real individuals for the purpose of coercion.

If an implementation adds effectors, the design is no longer PazuzuMeta 1.0 and requires a separate safety review.

---

## 12. Delivery checklist

- [ ] `SystemState` includes \(\hat{\pi}, \kappa, R, F, \mathcal{E}, \Xi, \iota, \tau\)
- [ ] Opponent tower with hard cap \(K\)
- [ ] MPC with band constraint and no backprop
- [ ] Ledger burns are append-only and externally signed to restore
- [ ] Parity gate uses \(\mathcal{E}\) and \(F\), not a mythic “danger unlock”
- [ ] Reports print \(\kappa, \mathcal{E}, \Xi, \lambda_{\text{meta}}\); they do not print “MAGI”
- [ ] Null-model bakeoff on at least two textbook games
- [ ] Adapter refuses any non-sandbox sink

---

*PazuzuMeta 1.0 — metacognitive control under incomplete information*  
*Specification. Not a deployed agent. Not a weapons system.*
