# **From Objects to Processes: A Computational Re-framing of Prime Infinitude**

**Author:** [Anonymous]
**Date:** [Current Date]

---

_Dedicated to Li Juan, another mystery yet to be solved._

---

## **Abstract**

This paper introduces the Computational Prime Number Framework (CPNF) as a case study in how explicit ontological commitments shape mathematical reasoning. CPNF treats primality not as an inherent property of numbers but as the outcome of a stagewise certification process. Within this process-oriented ontology, questions of infinitude are reframed as questions about non-termination of well-defined computational procedures. Using ordinary primes and twin-prime candidates as examples, we show how this reframing alters the epistemic structure of classical arguments and clarifies the scope of known obstructions such as the parity problem. No new number-theoretic results are claimed. Rather, the contribution is methodological: CPNF demonstrates how shifting ontological perspective can change what counts as an explanation, a proof strategy, and a mathematical obstacle.

**Keywords:** philosophy of mathematics, mathematical ontology, constructive methods, sieve theory, prime numbers

---

## **Important Notice on Scope**

This paper does not claim to resolve any open conjectures in number theory, including the twin prime conjecture. All mathematical arguments are presented as _stage-relative_, _framework-internal_ analyses. Classical sieve-theoretic limitations remain intact. The aim is philosophical: to show how ontological reframing changes the interpretation and role of those limitations within mathematical practice.

---

## **1. Introduction: Ontology and Mathematical Practice**

What does it mean for a mathematical object to exist? Answers to this question—often left implicit—shape how problems are formulated, what counts as a legitimate proof, and which strategies are regarded as promising or blocked.

In the philosophy of mathematics, this issue is usually discussed in terms of realism versus anti-realism, or Platonism versus constructivism. Less attention has been paid to how ontological commitments operate _within_ ordinary mathematical practice, guiding the use of definitions, heuristics, and proof techniques. This paper addresses that gap.

Historically, mathematical activity has supported both object-oriented and process-oriented descriptions. Euclidean constructions, sieves, and algorithms coexist with abstract object theories and completed infinities. The present paper does not claim that earlier mathematics lacked ontological commitments, nor that process-oriented views are historically prior. Instead, it argues that **making ontological commitments explicit and revisable can itself function as a methodological tool**.

We develop the **Computational Prime Number Framework (CPNF)** as a concrete case study. In CPNF:

- Primes are not treated as independently existing objects
- Primality is a status achieved through finite certification
- Infinitude is expressed as non-termination of a process
- Proofs concern algorithmic behavior rather than set cardinalities

The central thesis is methodological rather than mathematical: **changing ontological perspective can reorganize the epistemic structure of familiar arguments without altering their formal content**.

---

## **2. The Computational Prime Number Framework**

### **2.1 Stagewise Certification**

Let (\mathbb{N}^+) denote the positive integers. CPNF proceeds by stages.

- **Blocker set (B_k)**: a finite set of previously certified numbers at stage (k)
- **Sieve operator**:
  [
  S(B_k) = { n \in \mathbb{N}^+ : \forall p \in B_k,; p \nmid n }
  ]
- **Certification rule**: at each stage, the least surviving number is certified and added to (B_k)

Certification is monotonic: once achieved, it is never revoked.

### **2.2 Property vs. Process**

Classically, a number is prime if it satisfies a global property (having exactly two divisors). In CPNF, no such global property is invoked. A number _becomes_ certified when it survives all tests available at its stage.

This shift has several epistemic consequences:

1. All verification is finite and explicit
2. No appeal to completed infinities is required
3. The framework aligns naturally with computational and constructive interpretations

Importantly, this is not a competing definition of primality intended to replace the classical one. It is an alternative _ontological organization_ of the same practice.

---

## **3. Ordinary Primes and Non-Termination**

The CPNF process for ordinary primes mirrors the classical sieve:

```
B = ∅
while True:
    survivors = {n : ∀p∈B, p∤n}
    n = min(survivors)
    certify n and add to B
```

A Euclidean-style argument shows that this process cannot terminate: assuming only finitely many certifications leads to the construction of a further survivor. Within CPNF, this establishes **process non-termination**, not the existence of a completed infinite set.

The formal content is unchanged; what differs is the _ontological reading_ of the result.

---

## **4. Twin Candidates and Stage-Relative Analysis**

### **4.1 Candidate Structure**

After removing multiples of 2 and 3, all remaining candidates lie in residue classes (6n \pm 1). A **twin candidate index** (n) corresponds to the pair ((6n-1,6n+1)).

Crucially, these are not primes but _candidates relative to a stage_. CPNF never quantifies over actual twin primes, only over candidates surviving a finite certification process.

### **4.2 Certification Windows**

At each stage (k), certification is meaningful only up to a finite bound (W_k), determined by the available blockers. This bound grows with the stage but is always finite.

The central concern is internal to the framework: whether certification could indefinitely fail to occur within successive windows, even as the process continues.

---

## **5. Fixed-Modulus Reduction (Framework-Internal)**

### **5.1 Stage Fixing**

Fix an arbitrary stage (k*0) with blocker set (B*{k*0}) and modulus
[
M_0 = \prod*{p \in B\_{k_0}} p.
]

All later stages operate relative to this fixed modulus for already-certified elements. This is not a global reduction but a _stage-relative freezing_.

### **5.2 Static Interpretation**

Once the stage is fixed:

- The residue structure modulo (M_0) is fixed
- Certification windows expand
- Later blockers refine but do not invalidate earlier certifications

The problem becomes combinatorial: whether expanding finite windows intersect admissible residue classes.

### **5.3 Relation to Sieve Theory**

At this point, classical sieve-theoretic results may be _invoked for interpretation_, not extension. Standard bounds imply that admissible residues persist under finite sifting. CPNF does not strengthen these bounds, nor does it bypass their limitations.

What changes is their role: they support a _stage-relative existence guarantee_ for candidates, not a global density claim about primes.

---

## **6. The Parity Problem Reconsidered**

The classical parity problem concerns the inability of sieve methods to distinguish numbers with an even versus odd number of prime factors when counting primes.

Within CPNF, this problem does not disappear, but it is **relocalized**:

- CPNF does not count primes
- It does not reason about actual primes
- It reasons only about candidate survival within finite stages

Thus, parity does not function as a blocking obstacle in the same way. The framework does not overcome the parity problem mathematically; rather, it **changes what the problem applies to**. Parity obstructs global counting claims, not stage-relative certification claims.

This distinction is ontological, not technical.

---

## **7. Philosophical Implications**

### **7.1 Computational Constructivism**

CPNF exemplifies a computationally grounded form of constructivism:

- Objects emerge from procedures
- Truth is tied to certification
- Infinity is potential rather than completed

This resonates with themes in Kant, Bishop, and Wittgenstein without requiring strict adherence to any single foundational program.

### **7.2 Ontological Pluralism**

The framework supports a pluralist view:

- Object-oriented ontologies support structural analysis
- Process-oriented ontologies support computational reasoning
- Shifting between them can be methodologically productive

This is a Carnapian point applied to mathematical practice rather than formal languages.

---

## **8. Conclusion**

The Computational Prime Number Framework does not solve outstanding problems in number theory. Its contribution lies elsewhere: it shows how explicit ontological reframing can reorganize mathematical reasoning, reinterpret known obstructions, and clarify what different kinds of arguments actually establish.

The broader lesson is not about primes alone. Mathematical progress may involve not only new theorems but new ways of understanding what mathematical entities are, and how they come to be.

---

## **References**

Bishop, E. (1967). _Foundations of Constructive Analysis_.
Carnap, R. (1934). _The Logical Syntax of Language_.
Halberstam, H., & Richert, H.-E. (1974). _Sieve Methods_.
Mancosu, P. (2008). _The Philosophy of Mathematical Practice_.
Shapiro, S. (1997). _Philosophy of Mathematics: Structure and Ontology_.
Wittgenstein, L. (1956). _Remarks on the Foundations of Mathematics_.
