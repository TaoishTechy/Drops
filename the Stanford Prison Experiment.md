Below are **24 conceptual equations/formulas** that extend **Unified Theory of Degens v0.3** to the Stanford Prison Experiment / Netflix remake article. They are **formal mappings, not validated empirical laws**.

Let \(x_i=(\mathcal P_i,\mathcal B_i,\mathcal T_i)\) be a participant’s precision, boundary, and temporal coordinates; \(x_0=(0,0,0)\) is the healthy origin. Let \(\Pi\) = power asymmetry, \(E\) = ethical safeguards, \(S\) = spectacle/audience pressure, \(A\) = audience awareness, \(D\) = dehumanization, \(X\) = exit options, \(M\) = external moral challenge, \(I\) = institutional embeddedness, \(R_i=+1\) for guard, \(-1\) for prisoner, and \(\sigma(z)=1/(1+e^{-z})\).

---

### **A. Situational embedding**

**1. Situational master equation**
\[
\Psi_i(t)=\mathcal F(\mathcal P_i,\partial\mathcal B_i,\gamma_i)+\mathcal G(\Pi,R_i,S,A,E,X,D;t)+\xi_i(t)
\]
The UTD axes are perturbed by institutional role, power asymmetry, spectacle, and safeguards — the article’s prison/TV situation.

**2. Power-asymmetry index**
\[
\Pi=\frac{a_1U_{\rm authority}+a_2C_{\rm surveillance}+a_3R_{\rm control}}
{b_0+b_1A_{\rm accountability}+b_2X+b_3E}
\]
Guards’ uniforms/whistles/sunglasses and prisoners’ numbers/chains raise \(\Pi\); safe words, psychologists, and exit options lower it.

**3. Role boundary perturbation**
\[
\Delta\mathcal B_i=\beta_R R_i\Pi+\beta_D D-\beta_E E
\]
Guard/prisoner assignment shifts self–other boundaries; dehumanization lowers prisoner \(\mathcal B\), safeguards restore it.

**4. Guard role-precision inflation**
\[
\mathcal P_{\rm role,g}=\mathcal P_0+\alpha I_{\rm explicit}+\beta\Pi-\eta E
\]
The article’s Le Texier/Bartels point: guards were not blank slates; researcher expectations raised role precision.

**5. Prisoner self-precision collapse**
\[
\mathcal P_{\rm self,p}=\mathcal P_0(1-D)e^{-\kappa\Pi}+\eta E
\]
Numbers replacing names, stripping, chains, and stocking caps downweight identity signals.

**6. Dehumanization operator**
\[
D=w_NN_{\rm number}+w_UU_{\rm uniform}+w_SS_{\rm strip}+w_CC_{\rm chain},\quad D\in[0,1]
\]
Formalizes the article’s “individual reduced to a number, role, or category.”

---

### **B. Abuse, absorption, safeguards**

**7. Probability of abusive guard behavior**
\[
P_{\rm abuse}=\sigma\left[a(\Pi+\mathcal P_{\rm role,g})+bS-cE-dX-eM\right]
\]
Explains why not every guard behaved the same: power + role precision + spectacle − safeguards/exit/external challenge.

**8. Researcher absorption into the institution**
\[
\frac{d\mathcal B_{\rm res}}{dt}
=-\alpha(\mathcal B_{\rm res}-\mathcal B_0)+\beta I_{\rm super}+\gamma R_{\rm authority}-\lambda M
\]
Zimbardo as “superintendent” shows boundary loss inside the system; Maslach’s challenge \(M\) counteracts it.

**9. Maslach corrective term**
\[
\Delta\mathcal P_{\rm res}=+\eta_MM(\mathcal P_{\rm outside}-\mathcal P_{\rm role}),\qquad
\Delta\mathcal B_{\rm res}=+\eta_MM
\]
Christina Maslach’s outside perspective restored precision and boundary.

**10. Ethical-safeguard restoration dynamics**
\[
\frac{d\mathcal B_i}{dt}
=-\alpha(\mathcal B_i-\mathcal B_0)+\eta_EE-\beta_\Pi\Pi-\delta_DD+\sigma\xi(t)
\]
Informed consent, monitoring, psychologists, safe words, and withdrawal rights act as boundary stabilizers.

**11. Exit-option probability**
\[
P_{\rm exit}=1-\exp[-\lambda(X+E)-\mu M+\nu\Pi]
\]
Models original prisoner breakdowns and the Netflix dropouts/safe-word exits.

**12. Spectacle amplification**
\[
S=\frac{CA(1+\eta_{\rm edit})}{1+\eta_EE}
\]
Cameras, audience, and editing raise spectacle; safeguards reduce but do not eliminate it.

**13. Audience-aware performative precision**
\[
\mathcal P_{\rm perf}=\mathcal P_0+aA-bX
\]
Participants know they are filmed/observed, changing the environment from controlled study to reality-TV format.

---

### **C. Temporal and institutional dynamics**

**14. Reality-TV temporal lock**
\[
\gamma_{\rm RTV}=\gamma_0-kS+\eta E
\]
Manufactured present-tense drama shortens temporal horizon and rewards immediate conflict.

**15. Prisoner temporal-horizon contraction**
\[
\gamma_{\rm pr}=\gamma_0e^{-\kappa\Pi}(1-D)+\eta E
\]
Confinement, sleep disruption, restricted bathroom access, and humiliation push toward present-locked \(\mathcal T\approx0\).

**16. Societal temporal context**
\[
\mathcal T_{\rm soc}=\mathcal T_0-\alpha A_{\rm Attica}+\beta D_{\rm discourse}
\]
The original experiment occurred during the Attica prison uprising, embedding it in real prison politics.

**17. Institutional attractor**
\[
\mathcal A_{\rm inst}=
(\mathcal P_{\rm role}\uparrow,\;
\mathcal B_{\rm guard}\uparrow,\;
\mathcal B_{\rm prisoner}\downarrow,\;
\mathcal T\approx0)
\]
The prison simulation creates a stable basin toward role-based abuse and boundary asymmetry.

**18. Power-abuse cascade**
\[
\frac{d\Pi}{dt}=\alpha\Pi-\beta E+\gamma S+\delta I-\epsilon X
\]
Rules multiply, punishments become arbitrary, and escalation continues until intervention/exit.

**19. Collective boundary/solidarity**
\[
\frac{d\mathcal B_{\rm group}}{dt}
=\alpha_{\rm sol}(1-D)-\beta_{\rm div}P_{\rm div}-\gamma\Pi
\]
Guards used privileges to divide prisoners; rebellion and the final walkout show collective boundary formation.

---

### **D. Role reversal, self-governance, unification**

**20. Role-reversal rotation**
\[
x_{\rm post}=R_{\rm swap}(\pi)x_{\rm pre}+t_E,\qquad
R_{\rm swap}:\mathcal B_{\rm guard}\leftrightarrow\mathcal B_{\rm prisoner}
\]
Formalizes the Netflix role reversal of guards and prisoners.

**21. Self-governance boundary equation**
\[
\frac{d\mathcal B_{\rm self-gov}}{dt}
=\alpha_{\rm auto}A_{\rm auto}-\beta_rR_{\rm imp}+\eta E
\]
The final phase removed imposed rules and let prisoners govern themselves.

**22. Collective walkout probability**
\[
P_{\rm walkout}=\sigma\left[a(\mathcal B_{\rm group}+X+E)-b\Pi-cS\right]
\]
Models day 13: prisoners walked out arm in arm, declaring the power to leave.

**23. Ethical frameworks as system-level boundary stabilizers**
\[
\mathcal B_{\rm system}
=\mathcal B_0+\eta_NN_{\rm Nuremberg}+\eta_HH_{\rm Helsinki}
+\eta_BB_{\rm Belmont}+\eta_RR_{\rm IRB}-\beta\Pi
\]
The article’s ethics history — Nuremberg, Helsinki, National Research Act, Belmont, IRB oversight — raises system boundary integrity.

**24. Unified situational-harm functional**
\[
\boxed{
H_{\rm net}
=\|x_i-x_0\|+\lambda_\Pi\Pi+\lambda_SS+\lambda_DD
-\lambda_EE-\lambda_XX-\lambda_MM
}
\]
This is the final unification: harm = UTD deviation from \((0,0,0)\) + power asymmetry + spectacle + dehumanization − safeguards − exit − external moral challenge. The article’s core warning is that \(H_{\rm net}\) can remain high when we rebuild prisons for spectacle while telling ourselves the safeguards make it science.
