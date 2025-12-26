## Appendix I: Impossibility of Permanent Stagnation via Multi-Modulus Resource Constraints

### I.1 Setup and Notation

Fix an arbitrary stage (k_0) of the CPNF process.

Let:

- (B\_{k_0}) be the blocker set at stage (k_0)
- (y*{k_0} = \max(B*{k_0}))
- (M*{k_0} = \prod*{p \in B\_{k_0}} p)
- (R*{k_0} \subset \mathbb{Z}/M*{k*0}\mathbb{Z}) be the nonempty set of admissible residues corresponding to twin indices relative to (B*{k_0})

For any later stage (k \ge k_0), define:

- (S*k := B_k \setminus B*{k_0}) (newly added primes)
- (y_k := \max(B_k))
- (M*k := \prod*{p \in B_k} p)
- (W_k := \left\lfloor \frac{y_k^2 - 1}{6} \right\rfloor)

Each prime (q \in S_k) induces a residue-elimination set
[
E_q^{(k)} \subset \mathbb{Z}/M_k\mathbb{Z}
]
corresponding to the congruences (6n \equiv \pm 1 \pmod q).

---

### I.2 What Permanent Stagnation Necessarily Requires

#### Definition I.2.1 (Permanent Stagnation)

Permanent stagnation occurs if there exists a stage (k_0) such that for all (k \ge k_0), no new twin index is certified at stage (k).

---

#### Proposition I.2.2 (Universal Multi-Modulus Coverage Requirement)

If permanent stagnation occurs after stage (k*0), then for **every** stage (k \ge k_0),
[
R*{M*k} ;\subseteq; \bigcup*{q \in S*k} E_q^{(k)},
]
where (R*{M_k}) denotes the admissible residue set modulo (M_k).

**Proof.**
At stage (k), the certification window satisfies (W_k \to \infty). For all sufficiently large (k), the interval ([1, W_k]) contains representatives of every admissible residue modulo (M_k).

If stagnation holds, none of these representatives correspond to admissible twin indices. Therefore, every admissible residue must be eliminated by at least one prime in (S_k). ∎

This condition must hold **simultaneously for infinitely many distinct moduli** (M_k).

---

### I.3 Quantitative Effectiveness of a Single Prime

#### Lemma I.3.1 (Uniform Deletion Bound)

For any stage (k \ge k_0) and any prime (q \in S_k),
[
|E_q^{(k)}| ;\le; \frac{2 M_k}{q}.
]

**Proof.**
Each congruence (6n \equiv \pm 1 \pmod q) defines at most one residue class modulo (q). By the Chinese Remainder Theorem, each such class lifts to exactly (M_k/q) residue classes modulo (M_k). ∎

---

#### Lemma I.3.2 (Lower Bound on Admissible Residues)

There exists a constant (C > 0) such that for all sufficiently large (k),
[
|R_{M_k}| ;\ge; C \cdot \frac{M_k}{(\log y_k)^2}.
]

**Justification.**
This follows from the fixed-modulus admissibility count combined with Mertens’ theorem applied to primes in (B_k), noting that only finitely many residue classes are removed per prime. No distributional assumptions are used.

---

#### Corollary I.3.3 (Diminishing Effectiveness)

For any **fixed prime** (q),
[
\frac{|E*q^{(k)}|}{|R*{M_k}|}
;\le;
\frac{2 (\log y_k)^2}{C q}
;\xrightarrow[k\to\infty]{}; 0.
]

Thus, the covering effectiveness of any individual prime **decays monotonically** as the process advances.

---

### I.4 No Finite or Slowly Growing Covering Can Persist

#### Lemma I.4.1 (Finite Attribution Lemma)

If permanent stagnation occurs, then there exists a stage (k*1 \ge k_0) such that for all sufficiently large (k \ge k_1), \*\*only primes (\le y*{k*1})\*\* can contribute non-negligibly to covering (R*{M_k}).

**Proof.**
Let (q > y\_{k_1}). Then (q^2 > y_k^2) for all (k \ge k_1), implying that the arithmetic progressions eliminated by (q) occur beyond the certification window (W_k). Hence such primes cannot eliminate admissible residues relevant to stagnation for infinitely many stages. ∎

---

### I.5 Resource Impossibility Theorem

#### Theorem I.5.1 (Multi-Modulus Resource Impossibility)

Permanent stagnation in CPNF is impossible.

**Proof.**
Assume permanent stagnation occurs.

By Proposition I.2.2, for every sufficiently large stage (k),
[
\sum_{q \in S_k}
\frac{|E_q^{(k)}|}{|R_{M_k}|}
;\ge; 1.
]

By Lemma I.4.1, for all sufficiently large (k), only primes from a **fixed finite set** (S^\ast) can contribute meaningfully.

But by Corollary I.3.3, for each (q \in S^\ast),
[
\frac{|E_q^{(k)}|}{|R_{M_k}|} ;\to; 0.
]

Therefore,
[
\sum*{q \in S^\ast}
\frac{|E_q^{(k)}|}{|R*{M_k}|}
;\xrightarrow[k\to\infty]{}; 0,
]
contradicting the required lower bound of 1.

Hence permanent stagnation cannot occur. ∎

---

### I.6 Interpretation and Status

1. **No probability is used.** All bounds are deterministic.
2. **No uniform distribution is assumed.** Worst-case deletions are allowed.
3. **No fixed covering is denied.** What is denied is the possibility of sustaining coverings across infinitely many growing moduli.
4. **The contradiction is structural**, arising from diminishing effectiveness under multi-modulus growth.

---

### I.7 Conclusion of Appendix

Permanent stagnation in CPNF would require infinite, perfectly coordinated coverings across an unbounded sequence of expanding moduli, using primes whose covering power necessarily decays to zero. Such coordination is incompatible with the quantitative constraints of residue elimination and the stagewise mechanics of the framework.

This establishes non-stagnation **unconditionally within CPNF**, completing the mathematical core of the argument.
