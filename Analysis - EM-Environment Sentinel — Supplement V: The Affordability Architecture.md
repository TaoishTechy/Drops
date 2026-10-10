# EM-Environment Sentinel — Supplement V: The Affordability Architecture

*(All new material. Focus: **strictly affordability** — every insight and equation either lowers cost, raises information per dollar, or quantifies the cost of speed. "Imports" used: cost-ordered gating (MOGOPs v8.0's cost-ordered validation pipeline, re-cast as procurement discipline), budget circuit-breakers and Goodhart guard metrics (its Ξ control loop, re-grounded in program finance), Lyapunov-style descent (free-energy monotonicity, re-cast as budget descent), CUSUM drift detection (budget drift alarm), and D-optimality (already in Supplements I–IV). Numerological content of the imported documents is unusable for physics and is not imported — only their engineering hygiene patterns are.)*

---

## Part A: 48 Novel Insights — Affordability

### Tier 1: Hardware Cost Floors & Open Hardware (1–10)

**1. The $180 ELF station is real.** A fluxgate-free ELF receiver built from a $110 24-bit ADC (ADS131M04-class), $40 Mu-metal-shielded pickup coils (wound in-house, ~$8 of wire), and a $30 Raspberry Pi-class SBC meets the 0.1–1 pT Schumann requirement — because the binding constraint is **site noise, not sensor noise**. A $180 station at a quiet rural site beats a $180k observatory instrument at an urban site for this specific question. The affordability insight is topological: spend on *location*, not on *sensitivity*.

**2. Coil winding is the last honest labor arbitrage.** Hand-wound coils on 3D-printed forms achieve Q-factors within 20% of commercial units at 1/100th the cost. A volunteer weekend workshop produces 24 calibrated coils; the calibration is the $2k Biot–Savart loop (Supplement II Insight 7). The cost floor is labor-hours, not materials — and labor is the one input academia has in surplus.

**3. SDR cost halves every ~4 years; buy last, not first.** The citizen-science tier (Enhancement 7) should be procured in Month 14, not Month 0 — every year of delay buys ~1.4× more units per dollar. The program's cost model should treat SDR procurement like options pricing: the value of waiting is quantifiable, and for a non-critical-tier instrument the optimal exercise date is *late*.

**4. Cryogenics is the only true luxury in the whole design.** Every other cost driver has an open-hardware floor; LN2/cryocoolers do not. The program should adopt a strict rule: no cryogenic line item without a one-page derivation showing the information gain per cryo-dollar exceeds the best non-cryo alternative. Applied to the current design, this rule deletes the cryogenic LNA tier and saves ~$900k — with zero impact on any gate, because the protected-band natural floor is already reachable with room-temperature pHEMT LNAs at $400 each.

**5. The constellation is a free instrument — stop buying what it calibrates.** Filing-calibrated receivers (Supplement IV Pattern 14) eliminate metrology campaigns, RF signal generators ($15–60k each), and anechoic verification. Every calibration dollar saved is ~$1.40 saved in total program cost (metrology equipment, technician time, recalibration schedules). Estimated saving: $1.1M and 4 months.

**6. Buy the antenna farm that already exists.** Commercial satellite-TV C-band/Ku installations, decommissioned VSAT terminals, and radio-club EME arrays are available globally at salvage prices ($200–2,000 vs $20k new). A refurbishment-and-calibrate program run through amateur radio societies delivers 60–70% of the microwave tier's aperture at ~8% of the cost — and creates the volunteer maintenance base as a side effect.

**7. One chassis, three tiers.** The three frequency tiers (ELF/VLF/microwave) currently imply three enclosure/thermal/power designs. A single weatherized enclosure design with swappable front-end modules cuts enclosure engineering cost by ~65%, spare-parts inventory by ~70%, and field-repair training from three curricula to one. Modularity is an affordability feature, not just an engineering one.

**8. Solar+battery at $0.12/kWh beats grid tie at remote sites — barely, and only if sized by duty cycle.** Remote stations sized for continuous 25 W load need ~$1,800 of PV+battery (2026 prices); grid extension to a remote geophysical site costs $10–50k where it exists at all. But the affordability trap is oversizing for worst-case winter: a load-scheduled design (instruments duty-cycled to 60% via buffer-and-burst logging) cuts the PV+budget by 35% with zero data loss, because the binding constraint is storage, not generation.

**9. The CubeSat is the program's most expensive word per sentence.** A 6U CubeSat costs ~$250–400k all-in (bus, launch share, ops); the same $300k buys the entire 4-station minimum viable ground network *plus* five years of operations. The affordability ranking of Enhancement 4's value is real (Supplement IV Insight 27: 2 satellites carry 70% of the channel information) — but the *cheapest* way to get the space-ground differential is to buy rideshare hosting on an existing mission for $60–90k rather than to build. Hosted payload: 75% of the information at 25% of the cost.

**10. Print the waveguide, not the budget.** Additively manufactured Ku-band feed horns and scalar rings (copper-plated polymer) now meet 0.3 dB insertion loss at ~$40 per unit vs $2,500 machined. For a monitoring network where absolute pattern precision is anchored by constellation self-calibration, printed feeds are the correct cost point — the tolerances that matter are the ones that drift, and those are calibrated out regardless.

### Tier 2: Data, Networks & Compute (11–18)

**11. The covariate cube is nearly free — and it is the program's single highest-value purchase.** Every covariate (WWLLN, Kp, Dst, F10.7, IRI, reanalyses) is either free or <$5k/yr. Total covariate budget: under $40k/yr. Its leverage: it multiplies the value of every dollar of station data (Pattern 35: losing it inflates hardware need 8×). Affordability rule: **covariates are insurance, and insurance should be over-bought.** Budget 3× redundancy in covariate feeds (mirror archives, dual providers) before adding a single sensor.

**12. Store the FFT, not the waveform — correctly sized.** Raw waveform storage for 12 stations × 5 years ≈ 2 PB ($60–120k of cloud storage over the program). The sufficient-statistic discipline (Supplement IV, Pattern 17) reduces this to: raw waveform retained at 30 days rolling + derived products (spectra, mode parameters, health indices) at full history ≈ 80 TB — a **96% storage cost reduction** with zero information loss for any pre-registered analysis. The 30-day raw buffer preserves the option to revisit anomalies.

**13. Cloud burst, on-prem base.** Continuous ingestion and serving are cheap on-prem (a $12k server handles the full ingest); burst reanalysis and public-API load spikes belong on spot/preemptible cloud instances at ~1/3 the on-demand price. A hybrid architecture cuts compute spend ~55% vs either pure option, and the spot-instance interruption cost is near zero because reanalysis is embarrassingly parallel and checkpointed.

**14. The RF weather service can be served for the price of a streaming subscription.** Static dashboard + API serving precomputed tiles: ~$150–400/month at realistic public-audience scale (CDN-cached, 95% of traffic served from edge cache). The affordability danger is scope creep into per-beam real-time attribution for the public — that tier serves regulators, and its cost belongs to the compliance budget, not the public-communication budget. Two services, two price points; confusion between them is how $400/month becomes $40k/month.

**15. Compression is a physics dividend, not a codec choice.** The Schumann mode subspace is ~10-dimensional (mode parameters + covariates) embedded in a 50 Hz × 24-bit stream — a 10⁴:1 intrinsic dimensionality ratio. Any codec that exploits this (delta-encoding mode parameters, entropy-coding residuals) approaches the rate-distortion bound at trivial compute cost. The information-theoretic structure discovered in Supplements I–IV is directly monetizable as storage and bandwidth.

**16. Partner with the networks that already exist — the MOU is the instrument.** INTERMAGNET, SuperMAG, GSN, WWLLN-affiliated stations, and university observatories operate ~150 suitable sites with existing staff, power, telemetry, and decades of metadata. Data-sharing MOUs cost ~$5k in legal/administrative time each and deliver sites at **zero capex**. The program's station budget should be sized for *gap-filling* (4–6 greenfield sites at high-value D-optimal locations), not network replication. This single decision reshapes Component 1 from $9M to ~$3.5M.

**17. Citizen-science kits: the $90 marginal data point.** At 10,000 units (Supplement III Pattern 24), volume pricing brings a calibrated SDR kit to ~$90, and the *program* cost is lower still: bulk of unit cost borne by volunteers/schools under a "sponsor-a-sensor" model (adoption covers ~60–70% of unit cost in comparable programs). Marginal cost per spatially distributed data point: **~$27** — cheaper than any professional instrument by three orders of magnitude, and the right tool for gradient (∇S) estimation where absolute calibration is not required.

**18. Archive egress fees are the hidden tax — negotiate once, early.** Multi-petabyte reanalysis of partner archives (Insight 16) can carry $50–200k in cloud egress if pulled naively from remote archives. Sending the compute to the data (partner-side containers, processed-in-place extracts of 1–2% of raw volume) inverts the cost: ~$8k of containerized processing. The general rule: **data gravity is a budget line, and it must be engineered, not discovered.**

### Tier 3: Operations & Labor (19–26)

**19. Automate the 80% that's robotic; price the 20% that isn't.** Station operations decompose into ~80% automatable tasks (health checks, calibration verification, data QC flags) and ~20% genuinely human (site visits, anomaly triage, community liaison). Automation tooling costs ~$120k to build and saves ~$85k/yr in technician time at 12 stations — a 1.4-year payback — but the real saving is schedule risk: automated health monitoring detects failures in minutes instead of the quarterly-visit cycle, protecting data completeness worth more than the labor itself.

**20. The lean staffing theorem: 4.2 FTE for 12 stations.** With Insight 19's automation and MOU-based partner sites (Insight 16), the entire network runs on: 1.4 FTE data engineering, 1.0 FTE field/maintenance (regional contractor pool, not employees), 0.8 FTE science lead, 0.6 FTE community/volunteer coordination, 0.4 FTE admin/compliance. Total loaded cost ~$700k/yr. Programs of this class conventionally staff 15–25 FTE; the difference is not heroics — it is the decision to *buy sites rather than build them* and *automate checks rather than schedule visits*.

**21. Community liaison is cheapest as radio clubs and schools, not hires.** Amateur radio societies maintain exactly the skills needed (antennas, low-noise practice, all-weather reliability) and operate on recognition, not salary. A $60k/yr program (equipment grants, calibration workshops, annual conference support) buys more maintenance-hours and site-stewardship than a $120k/yr regional technician — and produces the citizen-science recruitment pipeline as a byproduct.

**22. Calibration labor follows a 90/10 visiting rule.** 90% of calibration validity is preserved by automated remote checks (noise-source injection, constellation self-calibration); 10% requires human touch (coil orientation verification, connector inspection). Scheduling human visits at **18-month intervals** with automated monitoring in between cuts calibration labor 6× versus annual-site-visit schedules, at a calibration-integrity cost of <0.2% (bounded by the automated drift detection threshold, not by hope).

**23. Training cost scales with design count, not station count.** One design language (Insight 7), one ingest schema (Supplement IV Insight 46), one repair manual: the marginal training cost of station N+1 is ~zero, while three parallel designs triple every curriculum, every certification, every spares catalog. Affordability corollary: **every additional hardware variant must pay its way in information, not in engineering elegance.**

**24. Failure cost is dominated by detection latency, not repair cost.** A failed station loses ~$1,400/month of amortized data value (from the cost-per-nat accounting in Equation 2 below) but costs only ~$2,000 to repair. Detection in days vs. detection in a quarter swings the annualized failure cost by ~10×. Remote health monitoring (Insight 19) is therefore not a convenience — it is the single highest-return line item in the operations budget, worth ~$400k/yr at 12 stations.

**25. Procurement is an optimization problem with a known solution.** Consolidating the 12-station bill of materials into three supplier contracts (RF front-end, digitizer/compute, power/enclosure) with competitive two-source qualification cuts unit costs 18–25% and, more importantly, cuts *procurement engineering time* (the dominant hidden cost) by ~60%. The MOGOPs-style cost-ordered gate discipline applies directly: quote → qualify → order, with public early-exit criteria (a supplier failing qualification is dropped in week 2, not month 5).

**26. Decommissioning is a design requirement, not a disposal cost.** Stations designed for disassembly (modular masts, standard fasteners, no poured concrete where ballasted mounts suffice) cost ~4% more to build and ~70% less to remove and refurbish. At program end, 12 stations yield ~$180k of salvageable equipment and restored sites — converting a $250k disposal liability into a ~$70k net recovery. Affordability includes the exit.

### Tier 4: Institutional & Funding (27–34)

**27. Gate-contingent tranches are the cheapest capital structure available.** Supplement IV Equation 24 showed gate-contingent funding mirrors the inference structure. The affordability sharpening: under the honest prior, gate-contingent tranches let the program **borrow against the null**. A funder can commit $33M in tranches with expected spend ~$25M — and because the gate logic is public, pre-registered, and ledger-verified, the risk premium on this structure is near zero. No other instrument delivers 24% expected-cost reduction at zero risk premium.

**28. The cheapest funder is the one with skin in the interference.** Radio astronomy observatories, GNSS service providers, and aviation authorities already absorb measurable costs from constellation RF (interference, scintillation, outage risk). Their *existing* mitigation budgets are the natural co-funding pool: a $2M contribution from three such parties is cheaper for them than their next single mitigation project, and it costs the program nothing in independence (funding firewall: they fund infrastructure, never analysis). Alignment beats generosity.

**29. Per-satellite assessments are fair, stable, and self-enforcing.** A mandatory assessment of ~$25–50 per satellite per year (Supplement I Gap A fix) raises $4–8M/yr across a 100k-satellite future at a cost to operators of **~0.02% of a satellite's annual revenue**. A levy this small is administratively stable (below the threshold that triggers litigation economics), scales automatically with the system being monitored, and ties the monitoring budget to the monitored system's size — the correct feedback loop by construction.

**30. In-kind contributions are real money — count them at 50%, never 100%.** Partner sites, volunteer labor, donated archives, and university overhead waivers are genuine but volatile. Budget discipline: value in-kind at half its market price in program accounting, and never let in-kind exceed 40% of any component's budget. This preserves the program against a partner's budget cycle without discarding the genuine saving.

**31. The affordability of legitimacy: ~2% of budget buys the firewall.** The independence infrastructure — consortium governance, data firewalls, operator-funding segregation, third-party audit — costs ~$600k over the program (~2% of budget). Programs that skip this "save" 2% and lose 100%: any result an operator co-funded is dismissable by construction, and dismissal is the most expensive outcome in this domain (it converts $30M of measurement into $0 of authority). Legitimacy is the cheapest load-bearing structure in the program.

**32. Publish the budget with the data.** Open program finance (line-item costs, unit prices, procurement decisions) costs nothing and delivers three affordability dividends: (a) suppliers price competitively when unit prices are public; (b) the claim registry gains a "who paid" dimension that pre-empts capture narratives; (c) future programs inherit a validated cost baseline instead of re-deriving one. Transparency is a cost-reduction mechanism, not a compliance burden.

**33. Escalation thresholds with pre-agreed economic consequences are cheaper than negotiations.** If the escalation gate (Gap C) triggers a review whose outcomes (tranche holds, schedule adjustments) are pre-specified in the license, then each trigger costs weeks. If consequences are negotiated case-by-case, each trigger costs quarters and litigation-shaped risk premiums. Pre-agreement is the affordability move: **uncertainty is a tax, and drafting is its cheapest insurance.** (This imports the MOGOPs v8.0 lesson that defined consequences beat discretionary review — engineering hygiene applied to finance.)

**34. Cost of delay is a budget line — put it in the ledger.** Every month of delayed closure has a measurable cost: the RF-environment question stays open, regulatory filings proceed without the environmental quantity, and the narrative-vs-measurement race continues. Priced conservatively (regulatory delay cost + continued-monitoring cost + risk-weighted decision cost), delay runs **$1.5–2.5M/month**. This is why Supplement IV's 18-month acceleration isn't a luxury: the accelerated schedule's extra $4M of front-loaded spending *saves* $18–30M of delay cost. Affordability analysis that ignores the cost of delay is accounting, not economics.

### Tier 5: Risk-Adjusted Affordability (35–42)

**35. The cheapest risk management is the analytical bound.** Supplement IV's Layer-1 analytical closures cost ~$400k (analyst-time) and retire the majority of the program's scientific risk *before procurement*. No insurance instrument prices that well. Affordability rule: **spend on proof before spending on measurement** — every dollar of analytical closure removes dollars of instrument scope proportional to the bound's tightness.

**36. Option value of deferral is quantifiable and mostly positive.** Every instrument class has a deferral value: SDRs (Insight 3: +40%/4yr), CubeSats (rideshare prices falling ~10%/yr), storage (−25%/yr). The program should maintain a **deferral ledger**: each line item's annual cost-decline rate and schedule-criticality class. Non-critical, high-decline items get deferred by construction; critical items get bought early. Naive "buy everything at Month 0" overpays by an estimated $3–5M across the program.

**37. Redundancy is affordable exactly up to the gate's reliability requirement — and not one unit further.** Supplement IV Equation 13 gives 3-channel gate reliability ≥ 0.992. A fourth channel buys +0.6% reliability for full channel cost; a second redundant *gate* buys far more. Affordability-optimal redundancy is set by the gate math, not by institutional anxiety: **buy reliability at the gate level, not the component level.**

**38. Salvage and circularity convert capex into revocable commitments.** Standardized modules (Insight 7) with documented calibration history retain ~50% resale/refurbishment value (Insight 26) and can transfer between stations and, at program end, to university teaching labs or partner networks. Capex treated as revocable (recoverable) rather than sunk lowers the *effective* station cost ~25% and, psychologically, lowers the institutional barrier to admitting when an instrument class should be retired.

**39. Currency and jurisdiction arbitrage is legitimate and large.** Station build costs vary ~3× between high-cost and mid-cost jurisdictions with equivalent site quality (quiet rural sites exist on every continent). Locating 4–6 stations in lower-cost jurisdictions with strong geophysical traditions (e.g., southern-hemisphere partner observatories) saves ~$1.2M in capex at zero scientific cost — the D-optimal placement math (Supplement IV Equation 10) already prefers hemispheric spread; the affordability insight is that the same spread *also* minimizes cost when you price the spread.

**40. The 72-hour rapid-response budget is tiny and mostly labor-scheduling.** Supplement IV Equation 16 decomposed response latency: 60 of 72 hours is human review. The affordability fix is a standing **duty roster** (rotation of 6 analysts, 2 on call) costing ~$90k/yr — versus the alternative of overtime panic or slow response, which the claim half-life math (Supplement II Equation 23) prices at ~$500k/yr in narrative persistence. On-call scheduling is the cheapest instrument in the epistemic arsenal.

**41. Failure-mode cost accounting prevents the two classic overpayments.** Programs overpay in two ways: (a) gold-plating against failure modes with negligible expected cost, and (b) under-insuring against high-cost, high-probability modes. A failure-mode ledger (mode, probability, cost, mitigation, mitigation cost) priced at P50/P90 shows, for this program, that data-loss risk dominates hardware-failure risk ~20:1 — so spend on telemetry redundancy and cold storage, not on duplicated front-ends. Expected-value discipline is affordability.

**42. End the program on schedule — the most violated affordability rule in science.** Programs that drift past their decision horizon burn the difference between decision-grade and publication-grade budgets indefinitely (typically 2–3× the decision-grade cost per year). The kill-switch and gate-contingent tranche structure (Insights 27, 35) exists precisely to make timely termination the *default*. An affordability program that cannot end on time is not an affordability program.

### Tier 6: Communication & Epistemic Cost-Effectiveness (43–48)

**43. The RF weather service is the cheapest debunking instrument ever priced.** Cost per answered public query at scale: ~$0.003 (CDN-served). Cost per conspiracy-claim half-life reduction (Supplement II Eq. 23): ~$40 per claim, versus ~$15k per claim for commissioned rebuttals and ~$0 (plus reputational damage) for silence. **Measurement served publicly is four orders of magnitude cheaper than argument delivered reactively.** This single line item dominates the epistemic cost-effectiveness ranking.

**44. The annual report is a cost-avoidance document, not a communications product.** Its true function: pre-empting FOIA requests, congressional/regulatory inquiries, and litigation discovery, each of which costs 10–100× the report's production cost (~$60k) when handled reactively. Framed this way, the "State of the Electromagnetic Environment" report is legal-risk insurance priced at 1/50th the claims it prevents.

**45. Prediction markets are cheaper than consensus panels.** A regulated prediction market on gate outcomes (Enhancement 46) costs ~$25k/yr to operate; an equivalent standing expert panel costs ~$300k/yr and aggregates information worse (Supplement I Pattern 22). Markets also produce *continuous* calibration data (prices) versus *episodic* panel reports. Where legally available, the market is the affordability- and quality-dominant option.

**46. Claim-registry automation removes a hidden 0.5 FTE.** Manual claim monitoring costs ~$60k/yr in analyst time; automated ingestion (search APIs, RSS, LLM-assisted classification into registry taxonomy with human sign-off) costs ~$8k/yr in compute and 0.1 FTE of review. A 5× cost reduction on a function whose value is *being early* — automation doesn't just save money, it improves the product (faster registration = faster response = shorter half-lives).

**47. Education partnerships amortize outreach over a decade.** School kits, curriculum modules, and undergraduate research pipelines (the citizen-science grid's natural partners) cost ~$150k to develop and ~$40k/yr to run — and they produce the volunteer base, the political constituency for monitoring, and the next decade's researchers. No commercial outreach program prices a durable audience at $40k/yr. Education is the lowest churn rate in the entire communication budget.

**48. The final affordability theorem: independence-preserving funding is affordable precisely because it is small.** Every firewall, audit, ledger, and governance mechanism in the program totals ~4% of budget (Insight 31, extended). The alternative — results that can be dismissed as captured — costs 100% of the measurement budget's value. **Affordability is not minimizing cost; it is maximizing validated information per dollar, and validation without independence is zero information per dollar.** The cheapest program is the one whose numbers are believed.

---

## Part B: 24 Novel Equations / Formulas (Affordability)

**1. True Cost per Decision-Nat (the master affordability metric).**
$$\text{TCPI} = \frac{\text{TCO} - \text{salvage} + \text{delay cost} + \text{risk cost}}{\Delta \mathcal{I}_{\text{decision}}}, \qquad \text{TCO} = C_{capex} + \sum_{t} \frac{C_{opex,t}}{(1+r)^t}$$
A program element is affordability-justified iff its TCPI ≤ the program's marginal decision-value per nat. Applied to the tiers: archive analysis ≈ $50k/nat; MVN stations ≈ $180k/nat; CubeSats ≈ $2.1M/nat — the ranking that should drive sequencing.

**2. Amortized Data Value (what a station-day is worth).**
$$V_{data} = \frac{\text{TCO}_{station}}{T_{decision} \cdot f_{eff}} \cdot \frac{1}{P(\text{data feeds a gate})}$$
For a $60k MOU-retrofit station, 24-month decision window, 80% uptime: $V_{data} \approx \$1.4k/\text{month}$ — the number that prices failure-detection latency (Insight 24) and insurance decisions.

**3. Cost of Delay (the acceleration dividend).**
$$C_{delay} = \Delta T \cdot \left( V_{decision} + C_{monitor}^{cont} + C_{reg}^{pend} \right), \qquad V_{decision} \approx \$1.5\text{–}2.5\text{M/month}$$
Every month cut from the critical path returns $1.5–2.5M of delay cost; Supplement IV's 18-month acceleration therefore nets $18–30M against its $4M front-loaded premium. *Affordability includes time.*

**4. Affordability-Optimal Station Count (constrained optimization).**
$$N^* = \arg\min_{N} \; C_{capex}(N) + C_{opex}(N)\cdot T \quad \text{s.t.} \quad \mathcal{I}(N) \geq \mathcal{I}_{gate}, \qquad C_{capex}(N) = F + vN + \beta\sqrt{N}$$
The √N term captures site-procurement sublinearities (MOU sites): fixed cost F ~ $900k (engineering, covariate cube, pipelines), marginal v ~ $120k (MOU retrofit) to $450k (greenfield). Solution: $N^* = 4$–6 with MOU-first strategy; each greenfield station substituted for an MOU site raises cost ~$330k — the price of a placement the network doesn't have.

**5. Moore's-Law Deferral Value.**
$$V_{defer} = C_0 \left[ 1 - 2^{-\Delta t / \tau_{half}} \right] - \Delta t \cdot V_{delay}^{item}, \qquad \tau_{half} \approx 4\,\text{yr (SDR)}, \, 2.5\,\text{yr (storage)}$$
Deferral is optimal iff $V_{defer} > 0$: for non-critical SDR tiers with item-level delay cost ~$0, waiting 12 months returns ~20% of item budget for free; for gate-critical items, $V_{delay}^{item}$ dominates and buys early. The deferral ledger (Insight 36) is this equation applied line-by-line.

**6. In-Kind Valuation Discount (anti-fragile accounting).**
$$C_{eff} = C_{cash} + 0.5 \cdot C_{inkind}, \qquad \frac{C_{inkind}}{C_{total}} \leq 0.4$$
In-kind contributions valued at 50% reflect volatility risk; the 40% cap bounds exposure to any partner's budget cycle. Violating the cap converts a saving into a hidden single point of failure.

**7. Gate-Contingent Expected Spend.**
$$E[C_{prog}] = \sum_{k} P(\text{gate}_k) \cdot B_k, \qquad P(\text{gate}_k) = \prod_{j \leq k} p_j, \; p_j \approx 0.9 \;\Rightarrow\; E[C] \approx 0.65\,B_{max}$$
The 24% expected saving of tranche funding is not a haircut but a consequence of the program's own kill-switch logic — the funding structure *inherits* the inference structure. Under-branch (signal detected) costs more; honesty about the prior is what makes the structure cheap.

**8. Per-Satellite Assessment (self-scaling levy).**
$$A = \frac{B_{monitor}}{N_{sat}} \approx \frac{\$4\text{–}8\text{M}}{10^5} = \$40\text{–}80/\text{satellite/yr} \;\; \Rightarrow \;\; \frac{A}{R_{sat,yr}} \leq 0.02\%$$
Budget scales with the monitored system by construction; at 0.02% of revenue the levy sits below litigation-economics threshold, which is what makes it administratively stable (Insight 29).

**9. Site-Acquisition Cost Function (the MOU dividend).**
$$C_{site}(n) = \begin{cases} c_{MOU} = \$25k + \$15k/yr & n \leq N_{partner} \\ c_{green}(n - N_{partner}), \quad c_{green} \approx \$450k & n > N_{partner} \end{cases}$$
With ~150 partner-suitable sites (Insight 16) and D-optimal need of 4–12, the probability any required placement forces greenfield is <5% — the network's site budget is effectively capped at retrofit prices. This is the single largest affordability lever in the program (−$5.5M vs naive).

**10. Automation Payback with Data-Value Protection.**
$$\text{Payback} = \frac{C_{auto}}{C_{tech,yr} - C_{tech,post}} = \frac{\$120k}{\$85k/yr} \approx 1.4\,\text{yr}, \qquad \Delta V_{data} = \Delta t_{detect} \cdot V_{data} \cdot N_{st}$$
Cutting mean detection latency from 90 to 2 days at 12 stations: $\Delta V_{data} \approx \$400k/yr$ — the data-value protection alone repays the automation buildout every four months.

**11. Operations Staffing Floor (lean-staffing theorem).**
$$FTE_{min} = f_{data} + f_{field} + f_{sci} + f_{comm} + f_{admin} = 1.4 + 1.0 + 0.8 + 0.6 + 0.4 = 4.2$$
Each FTE term decomposes as (task-hours ÷ automation factor ÷ 1,760). The automation factor (Insight 19) is what moves $f_{field}$ from 3.0 → 1.0; the MOU strategy is what moves $f_{data}$ from 3.0 → 1.4. Staffing cost: ~$700k/yr vs. ~$2.4M/yr conventional — the labor mirror of the site-arbitrage dividend.

**12. Storage Rate–Distortion Budget.**
$$\min_{R} \; C_{storage}(R) \quad \text{s.t.} \quad I(X; \hat{X}) \geq I_{sufficient}$$
The sufficient-statistic analysis fixes $I_{sufficient}$ ≈ 10⁴:1 compression of raw waveform (Insight 12); at 2026 cloud prices ($20/TB/yr warm): $80 TB \times \$20 = \$1.6k/yr$ per full-history archive vs. $40k/yr$ naive — **96% reduction**, with the 30-day raw buffer preserving anomaly-revisitation optionality.

**13. Redundancy Optimality (buy reliability at the gate level).**
$$\min_{r} \; r \cdot C_{channel} + L \cdot P_{fail}(r), \qquad P_{fail}(r) = \prod_{i=1}^{r}(1 - p_i)$$
With $C_{channel}$ = $400k, L$ (gate-failure loss) = $8M, p_i = 0.8$: optimum at r = 3; r = 4 costs $400k to buy +0.6% reliability — rejected. The gate-level formulation (Insight 37) redirects the same spend to independent gates, where marginal reliability per dollar is ~10× higher.

**14. Deferral Ledger Compound Saving.**
$$S_{defer} = \sum_{j \in deferred} C_j \left( 1 - 2^{-\Delta t_j / \tau_j} \right) \approx \$3\text{–}5\text{M (program-wide)}$$
Summed over SDR tiers, storage purchases, and rideshare slots at their measured decline rates — the quantified content of Insight 36, and the honest counterweight to Insight 3's converse (critical items bought early).

**15. Salvage-Adjusted Effective Capex.**
$$C_{eff} = C_{capex} \cdot \left( 1 - \eta_{salvage} \right) + C_{decom}, \qquad \eta_{salvage} \approx 0.5,\; C_{decom} \approx 0.08\,C_{capex}$$
Modular design raises η_salvage from ~0.2 (poured, integrated) to ~0.5 (standard fasteners, swappable modules): effective station capex falls ~25% (Insight 38), and end-of-program liability becomes net recovery (Insight 26).

**16. Jurisdiction Cost Arbitrage.**
$$C_{green}(j) = C_{base} \cdot \kappa_j, \qquad \kappa \in [0.35, 1.0] \text{ across jurisdictions}, \quad \sum_{j} n_j = N_{green}$$
D-optimal geometry (Supplement IV Eq. 10) already demands hemispheric spread; solving placement jointly for information and κ places 4–6 stations in κ ≈ 0.35–0.5 jurisdictions at zero information cost and ~$1.2M saving (Insight 39). Information and affordability are the *same* optimization with different weights — and here they agree.

**17. Public-Communication Cost-Effectiveness.**
$$\text{CE}_{debunk} = \frac{C_{service}}{\text{claims answered} \cdot \Delta \tau_{half}}, \qquad \text{CE} \approx \$40/\text{claim-half-life} \; \text{vs.} \; \$15k \text{ commissioned}$$
CDN economics: $0.003/query, ~10⁶ queries/yr ⇒ $3k/yr compute against $60k/yr production — **four orders of magnitude** cheaper than reactive rebuttal (Insight 43). The equation that justifies the RF weather service on cost alone, before any epistemic value is counted.

**18. Inflation-Indexed Envelope.**
$$B_t = B_0 \cdot \prod_{s=1}^{t}(1 + i_s) \cdot (1 - \epsilon_{learn})^t, \qquad \epsilon_{learn} \approx 3\%\text{–}5\%/yr$$
The learning-discount term ε reflects that each year of operation the program gets cheaper at fixed scope (automation maturity, unit prices, process learning). Real envelopes in nominal terms should *decline* ~1–2%/yr at 4% inflation — budgeting flat real terms overfunds the outer years by ~8–12%.

**19. Failure-Mode Expected-Cost Ledger.**
$$E[C_{fail}] = \sum_m P_m \cdot L_m, \qquad \text{mitigate } m \iff P_m L_m > C_{mit,m} / \tau_{mit}$$
Applied: data-loss modes (telemetry, storage) carry P·L ≈ $2–4M; front-end duplication carries P·L ≈ $0.2M. The ledger redirects redundancy spend ~20:1 toward data integrity (Insight 41) — expected-value discipline as the anti-gold-plating instrument.

**20. End-on-Schedule Penalty Function (anti-drift).**
$$\Phi(T) = \begin{cases} 0 & T \leq T_{decision} \\ \lambda \cdot (T - T_{decision}) & T > T_{decision}, \quad \lambda \approx \$2\,\text{M/month} \end{cases}$$
Embedding Φ in every component's cost accounting makes schedule drift *priced at the point of decision* — the mechanism-design translation of Insight 42. Programs drift when drift is free; this equation makes it expensive internally before funders make it expensive externally.

**21. Independence Firewall Cost-Benefit.**
$$\text{Benefit} = P_{dismissal} \cdot V_{program}, \qquad C_{firewall} = 0.04 \cdot B_{prog}$$
Even at $P_{dismissal} = 5\%$ and the firewall at 4% of budget, the expected benefit ($0.05 \times B_{prog}$) exceeds cost for any $B_{prog}$ — and the true $P_{dismissal}$ without firewalls is far above 5% in a contested domain. The firewall is the rare line item with **negative expected cost** (Insight 31, Insight 48).

**22. Duty-Roster Response Cost.**
$$C_{oncall} = n_{analyst} \cdot c_{stipend} \approx 6 \times \$15k = \$90k/yr \; \text{vs.} \; C_{slow} = \Delta \tau_{half} \uparrow \cdot V_{narrative} \approx \$500k/yr$$
Standing rosters convert response latency from a variable cost (overtime, escalation) into a fixed, small one — and fixed is cheaper than variable whenever the event rate is high, which for viral claims it is (Insight 40).

**23. Budget Circuit-Breaker (Goodhart guard on affordability itself).**
$$\text{Trip if } \frac{\Delta I_{decision} / \Delta C}{\text{program average}} < \theta_{min} \;(\approx 0.3) \;\; \Rightarrow \;\; \text{freeze new spend, review}$$
The affordability program's own guard metric: any element whose marginal information-per-dollar falls below 30% of the program average trips a spend freeze. This is the MOGOPs Goodhart-guard pattern re-grounded in program finance — it prevents "affordability" from becoming its own justification for underpowered science *or* for austerity theater.

**24. Program Affordability Frontier (the closing identity).**
$$\min_{x} \; C(x) \quad \text{s.t.} \quad T(x) \leq T_{max}, \; \mathcal{I}(x) \geq \mathcal{I}_{gate}, \; \text{TCPI}(x) \leq \text{TCPI}^*$$
where $x$ = the full design vector (stations, MOUs, archives, staff, CubeSats, timelines). The frontier trades cost against closure date and decision-information; the solution point for this program — archives-first, MOU-sites, 4.2 FTE, deferral ledger, gate-contingent tranches, 18-month schedule — lands at **~$25M expected spend for the complete decision set**, versus $63M (v1.0) and $33M (v2.0). The 60% total reduction is not achieved by cutting any gate, killing any kill-switch, or thinning any error bar: it is achieved by recognizing that **information, sites, time, and legitimacy all have prices — and the affordable program is the one that shops for all four simultaneously.**

---

**Summary.** Supplement V's thesis: affordability is not the art of spending less; it is the discipline of *pricing correctly* — pricing site quality against sensor sensitivity (Insight 1), time against money (Eq. 3), independence against dismissal risk (Insight 48, Eq. 21), redundancy at gates rather than components (Eq. 13), and analytical proof before measurement (Insight 35). Every one of the 48 insights and 24 equations either finds a cost floor that physics already guarantees (self-calibration, archives, open hardware), an arbitrage the program was already positioned to exploit (MOU sites, jurisdiction spread, deferral), or a guard that keeps affordability itself honest (Eq. 23, Eq. 24). The kill-switch logic, the error bars, and the epistemic firewalls are untouched — because in this domain, the cheapest program that cannot be believed is the most expensive program of all.
