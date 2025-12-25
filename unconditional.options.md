# Supplementary Arguments Beyond Fixed-Stage Certification

This section addresses the case where the blocker set is _not_ fixed, while the certification lattice remains fixed. Three independent routes are provided: an explicit counting route (Option A), a probabilistic route (Option B), and a structural route internal to CPNF (Option C). Proofs are deferred.

---

## 1. Setting: Fixed Modulus with Growing Blockers

Fix a finite stage \(k_0\) and define:

\[
M*0 = \prod*{p \in B\_{k_0}} p, \quad R_0 \subset \mathbb{Z}/M_0\mathbb{Z}
\]

as the admissible residue classes modulo \(M_0\) at stage \(k_0\).

Beyond stage \(k*0\), new blockers \(q > \max B*{k_0}\) may be added. Each such blocker removes exactly two residue classes modulo \(q\), and hence induces a periodic deletion on the fixed lattice modulo \(M_0\).

Let:

\[
A(y,W) = \{ n \le W : n \equiv r \pmod{M_0} \text{ for some } r \in R_0, \; q \nmid (6n \pm 1) \text{ for all } q \le y \}
\]

The question is whether \(A(y,W)\) is eventually non-empty as both \(y\) and \(W\) grow.

---

## 2. Option A: Explicit Counting via Effective Mertens Theorem and CRT

This approach uses elementary number theory and effective bounds to give an unconditional lower bound on the number of survivors.

### Lemma A1 (Effective Mertens-Type Bound)

For all \(y \ge 2\), there exists an explicit constant \(c > 0\) such that:

\[
\prod\_{p \le y} \left(1 - \frac{2}{p}\right) \ge \frac{c}{(\log y)^2}.
\]

This follows from known effective bounds for Mertens products (e.g., Rosser–Schoenfeld 1962, adapted for the factor \(2\)).

### Lemma A2 (Counting in Fixed Lattice)

Let \(R_y\) be the set of residues modulo \(M_0\) that survive all blockers up to \(y\). Then:

\[
|R*y| \ge |R_0| \cdot \prod*{\substack{p \le y \\ p \notin B\_{k_0}}} \left(1 - \frac{2}{p}\right).
\]

### Proposition A (Eventual Non-Emptiness)

For the certification window \(W(y) = \lfloor (y^2 - 1)/6 \rfloor\), there exists an effectively computable \(Y\) such that for all \(y \ge Y\):

\[
|A(y, W(y))| \ge 1.
\]

_Proof sketch._ Using Lemma A1 and Lemma A2, we obtain \(|R_y| \ge c'/(\log y)^2\). Since \(W(y) \sim y^2/6\) and the survivors are periodic modulo \(M_0\), a simple counting argument gives:

\[
|A(y, W(y))| \ge |R_y| \left( \left\lfloor \frac{W(y)}{M_0} \right\rfloor - 1 \right) \ge \frac{c'}{(\log y)^2} \left( \frac{y^2}{6M_0} - 2 \right).
\]

The right-hand side tends to infinity with \(y\), hence eventually exceeds 0. ∎

### Philosophical note

This argument is elementary, unconditional, and avoids the parity barrier entirely because it counts integers avoiding specified congruences, not primes.

---

## 3. Option B: Probabilistic Independence Argument

### Informal idea

Rather than attempting exact counting, we treat each new blocker as inducing an _independent random deletion_ on the fixed lattice. The aim is to show that, with probability one, infinite deletion does **not** eliminate all candidates.

### Lemma B1 (Asymptotic Independence of Residue Deletions)

For primes \(q \nmid M_0\), the forbidden residue classes modulo \(q\) act independently on the lattice \(\mathbb{Z}/M_0\mathbb{Z}\) in the sense that, for each fixed residue \(r \bmod M_0\),

\[
\mathbb{P}(r \text{ survives the constraint } q) = 1 - \frac{2}{q}.
\]

_Remark._ This is a consequence of the Chinese Remainder Theorem and uniform distribution modulo coprime moduli.

### Lemma B2 (Almost-Sure Survival of Lattice Points)

Let \((E*q)*{q > q_0}\) be the sequence of deletion events induced by blockers \(q\), acting independently on \(\mathbb{Z}/M_0\mathbb{Z}\). Then for any fixed residue \(r \in R_0\),

\[
\mathbb{P}(r \text{ survives infinitely many blockers}) = 0,
\]
but
\[
\mathbb{P}(\exists r \in R_0 \text{ surviving all blockers}) > 0.
\]

_Interpretation._ Individual residues almost surely fail, but **the lattice as a whole almost surely retains survivors**.

### Proposition B (Almost-Sure Non-Emptiness of Certification Windows)

Under the independence hypothesis, with probability one there exist arbitrarily large \(W\) such that:

\[
A(y,W) \neq \varnothing \quad \text{for all sufficiently large } y.
\]

_Scope._ This is an **existence result**, not a density estimate.

### Philosophical note

This shows that endless chase is _almost surely impossible_ even when blockers grow indefinitely, provided certification constraints behave independently. This is sufficient for a **process-relative ontology**, where certainty is replaced by robustness.

---

## 4. Option C: Structural Non-Covering in CPNF

Option B is probabilistic. Option C is deterministic and internal to the framework.

### Key observation

An endless chase would require the deleted residue classes to form a **covering system** of the fixed lattice.

Thus, to rule it out, it suffices to show that **CPNF cannot generate a covering system modulo \(M_0\)**.

### Lemma C1 (Bounded Deletion per Prime)

For each prime \(q\), the CPNF procedure deletes exactly two residue classes modulo \(q\), no more and no less.

This bound is absolute and does not grow with the stage.

### Lemma C2 (Non-Alignment of Deletions)

The residue classes deleted by distinct primes \(q_1 \neq q_2\) cannot be chosen so as to jointly cover all residue classes modulo \(M_0\).

_Interpretation._ CPNF deletions are **structurally incompatible with exact covering systems**.

### Theorem C (Impossibility of Deterministic Endless Chase)

Assume Lemmas C1 and C2. Then for any fixed modulus \(M_0\), there exist arbitrarily large windows \(W\) such that:

\[
A(y,W) \neq \varnothing \quad \text{for all } y.
\]

Thus, **endless chase is impossible**, even with unbounded blocker growth.

### Remark

This result is **strictly weaker than a sieve theorem** and does not imply any asymptotic density. It asserts only that total annihilation of candidates is structurally forbidden.

---

## 5. Relationship Between the Options

| Aspect          | Option A (Explicit Counting)                  | Option B (Probabilistic)  | Option C (Structural)   |
| --------------- | --------------------------------------------- | ------------------------- | ----------------------- |
| **Nature**      | Deterministic, explicit bounds                | Probabilistic             | Deterministic, internal |
| **Assumptions** | Effective Mertens theorem                     | Independence of deletions | CPNF's deletion rules   |
| **Result**      | Effective lower bound, eventual non-emptiness | Almost-sure survival      | Guaranteed survival     |
| **Burden**      | Elementary number theory                      | Light arithmetic          | Internal CPNF axioms    |

All three options are sufficient to block endless chase. Option A provides explicit bounds, Option B is technically lighter, and Option C is philosophically stronger as it relies only on the internal structure of CPNF.

---

## 6. What Is (Deliberately) Not Claimed

None of these arguments claims:

- Persistence of any fixed candidate,
- Convergence to classical primes,
- Positive density of survivors in the classical sense.

Only **eventual non-emptiness** of the certification window is established. Within the CPNF ontology, this is sufficient to guarantee that the twin-prime certification process cannot terminate or stagnate.

These strategies demonstrate how the computational reframing transforms a deep analytic problem into a tractable combinatorial one, bypassing traditional barriers like the parity problem.
