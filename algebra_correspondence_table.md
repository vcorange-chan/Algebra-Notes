# Algebraic Structure Correspondence Table

A cross-reference document for concepts across Group, Vector Space, Ring, and Field, each located on the algebraic workflow map.

---

## Table of Contents

1. [The Workflow Map (Quick Reference)](#the-workflow-map-quick-reference)
2. [Unifying Note: Modules](#unifying-note-modules)
3. [Level 0 — The Structure Itself](#level-0--the-structure-itself)
4. [Level 1 — Decomposition (Substructures)](#level-1--decomposition-substructures)
5. [Level 1 — Generation](#level-1--generation)
6. [Level 2, Stage 1 — Equivalence Relations](#level-2-stage-1--equivalence-relations)
7. [Level 2 — Quotient Structures (Compression)](#level-2--quotient-structures-compression)
8. [Level 2, Stage 2 — Invariants](#level-2-stage-2--invariants)
9. [Level 2, Stage 3 — Canonical Forms](#level-2-stage-3--canonical-forms)
10. [Level 3 — Homomorphisms](#level-3--homomorphisms)
11. [Level 3 — Kernel and Image](#level-3--kernel-and-image)
12. [First Isomorphism Theorem (the bridge)](#first-isomorphism-theorem-the-bridge)
13. [Full Condensed Table](#full-condensed-table)
14. [Key Asymmetries](#key-asymmetries)

---

## The Workflow Map (Quick Reference)

```
Level 0 — Abstract:   distill axioms from phenomena
Level 1 — Analyze:    decomposition (substructures) + generation (seeds)
Level 2 — Classify:   the five-stage classification workflow
                        Stage 1. equivalence relation
                        Stage 2. invariants
                        Stage 3. canonical form
                        Stage 4. compute in canonical form
                        Stage 5. translate back
Level 3 — Translate:  homomorphism, representation, computation
```

**Algebra's goal**: given a class of objects, answer "how many essentially different kinds are there, and how do I tell which kind a given object is?"

The table below locates every classical concept on this map.

---

## Unifying Note: Modules

Before reading the structure-specific entries, hold onto this unification:

> **Abelian groups and vector spaces are both examples of modules.**
> 
> - A vector space over a field $F$ is an $F$-module.
> - An abelian group is a $\mathbb{Z}$-module.
> - Ideals of a ring $R$ are $R$-modules.

This explains why so many rows in the table look parallel — they are literally instances of the same module-theoretic construction with different "scalar rings."

**Scope of the unification**: modules unify the *additive, commutative* side of algebra. Non-abelian groups are not modules and retain their own distinct theory (conjugation, non-normal subgroups, non-abelian quotients). The table below pairs *structures* with *analogous moves*, not identical objects.

---

## Level 0 — The Structure Itself

*Role in workflow: Level 0 (Abstract). Defines the object class.*

| Aspect            | Group $G$              | Vector Space $V$ over $F$ | Ring $R$                                | Field $F$                    |
| ----------------- | ---------------------- | ------------------------- | --------------------------------------- | ---------------------------- |
| Operations        | one: $\cdot$           | two: $+$, scalar $\cdot$  | two: $+$, $\times$                      | two: $+$, $\times$           |
| Identity elements | $1$                    | $0$                       | $0$ and $1$                             | $0$ and $1$                  |
| Inverses          | every $x$ has $x^{-1}$ | every $v$ has $-v$        | every $x$ has $-x$; not always $x^{-1}$ | every $x \ne 0$ has $x^{-1}$ |
| Commutativity     | sometimes (abelian)    | yes (addition)            | sometimes                               | yes (both operations)        |
| Extra axioms      | associativity          | distributivity of scalar  | distributivity, (often assoc./comm.)    | all ring axioms + division   |

**Geometric intuition**:

- Group: points with one reversible operation (rotations of a wheel).
- Vector space: points you can add and scale ($\mathbb{R}^n$).
- Ring: points with addition, subtraction, multiplication — but not always division ($\mathbb{Z}$).
- Field: ring + division ($\mathbb{Q}, \mathbb{R}, \mathbb{C}$).

---

## Level 1 — Decomposition (Substructures)

*Role in workflow: Level 1, Decomposition. Find self-contained smaller worlds.*

| Concept                                   | Group                                     | Vector Space                       | Ring                                  | Field                           |
| ----------------------------------------- | ----------------------------------------- | ---------------------------------- | ------------------------------------- | ------------------------------- |
| Substructure name                         | subgroup $H \le G$                        | subspace $W \le V$                 | subring $S$; **ideal** $I$            | subfield $K \le F$              |
| Closure conditions                        | $1\in H$; $xy\in H$; $x^{-1}\in H$        | $0 \in W$; $u+v \in W$; $cv \in W$ | $0,1\in S$; closed under $+,-,\times$ | subring + closed under inverses |
| Special substructure (used for quotients) | **normal subgroup** $N \trianglelefteq G$ | any subspace works                 | **ideal** $I$                         | none (trivial ideals only)      |
| Intersection of substructures             | is a subgroup                             | is a subspace                      | is a subring/ideal                    | is a subfield                   |
| Union                                     | generally NOT a subgroup                  | generally NOT a subspace           | generally NOT a subring               | generally NOT a subfield        |

**Geometric picture**: substructures are "lines/planes through the identity" — in a vector space, literally lines/planes through the origin. The identity/origin must be included; closure under operations is what makes the substructure self-contained.

**Why some substructures are "special"**: for groups and rings, only *special* substructures (normal subgroups, ideals) allow a well-defined quotient. For vector spaces, every subspace works — because the additive structure is abelian and the scalars come from a field.

---

## Level 1 — Generation

*Role in workflow: Level 1, Generation. Describe a substructure using minimal seeds.*

| Concept                         | Group                                               | Vector Space                                  | Ring                                   | Field                                       |
| ------------------------------- | --------------------------------------------------- | --------------------------------------------- | -------------------------------------- | ------------------------------------------- |
| Seed set                        | $S \subseteq G$                                     | $S \subseteq V$                               | $S \subseteq R$                        | $S \subseteq F$                             |
| Generated substructure          | $\langle S \rangle$                                 | $\operatorname{span}(S)$                      | $\langle S \rangle$ (subring or ideal) | $K(S)$                                      |
| Explicit form                   | all finite products $s_1^{\pm 1}\cdots s_n^{\pm 1}$ | all finite linear combinations $\sum c_i v_i$ | all finite sums of products of $S$     | all rational expressions in $S$ over base   |
| Minimal seed                    | generating set                                      | **basis** ¹                                   | generating set                         | transcendence basis + algebraic generators  |
| Uniqueness of minimal seed size | not unique in general                               | **dimension** is unique                       | not unique in general                  | **degree / transcendence degree** is unique |

### ¹ Note on "basis"

The concept of **basis** (= generating + linearly independent, with every element uniquely expressible) is special to **vector spaces** and, more generally, to **free modules**.

It does not exist in arbitrary groups or rings. The reason: a basis requires *scalars from a field*, so that linear independence behaves cleanly. Once scalars come from a mere ring, bases may fail to exist — some modules are not free.

The fact that every vector space has a basis is a **deep property**, not a general feature of algebra. It's one reason linear algebra is so computationally tractable and why it's taught first.

---

## Level 2, Stage 1 — Equivalence Relations

*Role in workflow: Level 2, Stage 1. Define "when are two objects essentially the same?"*

| Concept                       | Group                         | Vector Space                     | Ring                        | Field                         |
| ----------------------------- | ----------------------------- | -------------------------------- | --------------------------- | ----------------------------- |
| Equivalence from substructure | $a \sim b \iff ab^{-1} \in H$ | $u \sim v \iff u - v \in W$      | $a \sim b \iff a - b \in I$ | trivial (no nontrivial ideal) |
| Equivalence class name        | coset $aH$ or $Ha$            | affine subspace $v + W$          | coset $a + I$               | —                             |
| Geometric picture             | translated copies of $H$      | parallel translates of $W$       | parallel translates of $I$  | —                             |
| Partition property            | $G = \bigsqcup$ cosets        | $V = \bigsqcup$ affine subspaces | $R = \bigsqcup$ cosets      | —                             |

**Geometric intuition**: take a substructure (line through the origin). Translate it in all possible ways. Each translate is an equivalence class. The whole space is tiled by these parallel translates. This is the *coset decomposition* picture.

**Why fields are trivial here**: a field has only two ideals ($\{0\}$ and the whole field), so the equivalence relation either identifies nothing or everything. Fields don't get interesting quotient theory; they get interesting *extension* theory instead (Galois theory).

---

## Level 2 — Quotient Structures (Compression)

*Role in workflow: Level 2, compression. Fold the structure via an equivalence relation into a simpler one.*

| Concept            | Group                                                              | Vector Space                  | Ring                                  | Field   |
| ------------------ | ------------------------------------------------------------------ | ----------------------------- | ------------------------------------- | ------- |
| Quotient name      | quotient group $G/N$                                               | quotient space $V/W$          | quotient ring $R/I$                   | trivial |
| Elements           | cosets $gN$                                                        | affine subspaces $v+W$        | cosets $a+I$                          | —       |
| Operation(s)       | $(gN)(hN) = (gh)N$                                                 | $(u+W)+(v+W)=(u+v)+W$         | addition and multiplication of cosets | —       |
| Required condition | $N$ **normal**                                                     | any subspace                  | $I$ is an **ideal**                   | —       |
| Size formula       | $\lvert G/N \rvert = \lvert G \rvert / \lvert N \rvert$ (Lagrange) | $\dim(V/W) = \dim V - \dim W$ | $\lvert R/I \rvert$ if finite         | —       |

**Geometric picture**: quotienting is *folding* the space so that each coset becomes a single point. For $\mathbb{R}^2 / (x\text{-axis})$, every horizontal line becomes one point — the quotient is a one-dimensional space (the $y$-coordinate).

**Why fields have no useful quotients**: the defining property "every nonzero element is invertible" forces every ideal to be trivial. Fields are "too rigid" to be folded. Field theory works by *extension* (going up to larger fields), not by quotient.

---

## Level 2, Stage 2 — Invariants

*Role in workflow: Level 2, Stage 2. Find quantities that don't change under the equivalence.*

| Concept                          | Group                                                | Vector Space                                       | Ring                        | Field                                |
| -------------------------------- | ---------------------------------------------------- | -------------------------------------------------- | --------------------------- | ------------------------------------ |
| Coarse invariants                | order $\lvert G \rvert$                              | dimension $\dim V$                                 | characteristic, cardinality | characteristic                       |
| Intermediate invariants          | exponent, number of subgroups, abelianization        | rank of a linear map                               | —                           | degree $[F:K]$                       |
| Invariants of maps               | —                                                    | trace, determinant, characteristic polynomial      | —                           | —                                    |
| Full invariants (when available) | elementary divisors (for finitely generated abelian) | dim (for spaces); Jordan structure (for operators) | —                           | Galois group (for Galois extensions) |

**Geometric picture of invariants for matrices**:

- **Determinant** = volume-change factor (with sign for orientation). $\det A = 0$ means space is crushed flat.
- **Trace** = total stretching along eigen-directions. $\operatorname{tr}(A) = \sum \lambda_i$. Positive trace = net outward; negative = net inward or flipping.
- Both are invariants of the similarity class — they don't change under change of basis.

**Purpose of invariants**: tools for distinguishing equivalence classes. Different values of an invariant prove non-equivalence. Matching values are *necessary* but not always *sufficient* for equivalence.

---

## Level 2, Stage 3 — Canonical Forms

*Role in workflow: Level 2, Stage 3. Pick a unique simplest representative from each equivalence class.*

| Concept                                   | Group                                                      | Vector Space                                                  | Ring | Field                                    |
| ----------------------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------- | ---- | ---------------------------------------- |
| Canonical form of the structure           | elementary divisor decomposition (for f.g. abelian groups) | every $V$ is $\cong F^{\dim V}$                               | —    | —                                        |
| Canonical form of a map                   | —                                                          | **Jordan normal form** / diagonal form (over alg. closed)     | —    | —                                        |
| Two objects equivalent $\iff$             | same elementary divisors (for f.g. abelian)                | same dimension (for spaces); same Jordan form (for operators) | —    | same Galois data (for Galois extensions) |
| Three sub-moves fused in a canonical form | decomposition + compression + normalization                | same                                                          | —    | —                                        |

### Example: Jordan normal form (unpacked)

- **Decomposition**: $V = \bigoplus_i V_{\lambda_i}^{\text{gen}}$ — the space splits into generalized eigenspaces.
- **Compression**: within each generalized eigenspace, coalesce via Jordan chain structure.
- **Normalization**: each piece becomes a standard Jordan block $J_\lambda$.

Result: a unique (up to block ordering) canonical matrix representing the entire similarity class.

**Key insight**: *simplification* and *classification* are the same thing seen from two angles. A canonical form is simultaneously the simplest representative (simplification) and the complete invariant (classification).

---

## Level 3 — Homomorphisms

*Role in workflow: Level 3, Translate. Map the structure to another structure while preserving operations.*

| Concept                | Group               | Vector Space                        | Ring                                             | Field                   |
| ---------------------- | ------------------- | ----------------------------------- | ------------------------------------------------ | ----------------------- |
| Map name               | group homomorphism  | linear map                          | ring homomorphism                                | field homomorphism      |
| Preservation           | $f(xy) = f(x)f(y)$  | $f(cu+v) = cf(u) + f(v)$            | $f(x+y) = f(x)+f(y)$; $f(xy)=f(x)f(y)$; $f(1)=1$ | same as ring hom        |
| Automatic preservation | identity, inverses  | zero, negation                      | zero, additive inverses                          | multiplicative inverses |
| Special property       | —                   | —                                   | —                                                | **always injective**    |
| Isomorphism            | bijective group hom | bijective linear map (= invertible) | bijective ring hom                               | bijective field hom     |

**Why field homomorphisms are always injective**: the kernel is an ideal, and a field has only the trivial ideals $\{0\}$ and $F$. A nonzero field homomorphism must send $1 \mapsto 1$, so its kernel can't be all of $F$; hence the kernel is $\{0\}$.

**Geometric picture**: a homomorphism is a "structure-respecting translation" from one world to another. Some information is allowed to be lost (many-to-one), but the operations are preserved exactly.

---

## Level 3 — Kernel and Image

*Role in workflow: Level 3 (map the structure) + Level 1 (the kernel and image are substructures).*

| Concept         | Group                       | Vector Space                                  | Ring                        | Field                  |
| --------------- | --------------------------- | --------------------------------------------- | --------------------------- | ---------------------- |
| Kernel          | $\ker f = \{x : f(x) = 1\}$ | $\ker T = \{v : T v = 0\}$ (null space)       | $\ker f = \{x : f(x) = 0\}$ | $\{0\}$ (always)       |
| Kernel's nature | normal subgroup of $G$      | subspace of $V$                               | ideal of $R$                | trivial ideal          |
| Image           | $\operatorname{Im}(f)$      | $\operatorname{Im}(T)$ (range / column space) | $\operatorname{Im}(f)$      | $\operatorname{Im}(f)$ |
| Image's nature  | subgroup of target          | subspace of target                            | subring of target           | subfield of target     |

**Geometric picture**: for a linear map $T: \mathbb{R}^3 \to \mathbb{R}^2$:

- **Kernel** = the directions in $\mathbb{R}^3$ that get crushed to the origin (often a line).
- **Image** = the part of $\mathbb{R}^2$ that $T$ actually reaches (often the whole plane, sometimes a line).

The kernel measures *how much information the map destroys*; the image measures *how much target the map actually fills*.

---

## First Isomorphism Theorem (the bridge)

*Role in workflow: binds Level 2 (quotient) and Level 3 (homomorphism). The pivot of algebra.*

| Structure    | Statement                                                   |
| ------------ | ----------------------------------------------------------- |
| Group        | $G / \ker f \cong \operatorname{Im}(f)$                     |
| Vector space | $V / \ker T \cong \operatorname{Im}(T)$                     |
| Ring         | $R / \ker f \cong \operatorname{Im}(f)$                     |
| Field        | trivial: $F \cong \operatorname{Im}(f)$ (kernel is $\{0\}$) |

**What it says**: every homomorphism factors as "compress then embed":

$$
X \xrightarrow[\text{surjective}]{\pi} X/\ker f \xrightarrow[\cong]{\bar f} \operatorname{Im}(f) \xhookrightarrow[\text{injective}]{\iota} Y
$$

- $\pi$: compression (Level 2).
- $\bar f$: isomorphism (Level 2–3 bridge).
- $\iota$: embedding (Level 1).

**Consequence**: homomorphism, quotient, kernel, and image are **four faces of the same construction**. Understanding any one of them means understanding the others.

---

## Full Condensed Table

| Universal Concept             | Group                             | Vector Space                     | Ring                             | Field                      |
| ----------------------------- | --------------------------------- | -------------------------------- | -------------------------------- | -------------------------- |
| **Structure (L0)**            | group                             | vector space                     | ring                             | field                      |
| **Substructure (L1)**         | subgroup                          | subspace                         | subring                          | subfield                   |
| **Substructure for quotient** | **normal subgroup**               | any subspace                     | **ideal**                        | none                       |
| **Generation (L1)**           | $\langle S \rangle$               | $\operatorname{span}(S)$         | $\langle S \rangle$              | $K(S)$                     |
| **Minimal generating set**    | generating set                    | **basis** ¹                      | generating set                   | trans. basis + alg. gens   |
| **Size invariant (L2 S2)**    | $\lvert G \rvert$                 | $\dim V$                         | rank, cardinality                | $[F{:}K]$                  |
| **Equivalence (L2 S1)**       | $ab^{-1} \in H$                   | $u-v \in W$                      | $a-b \in I$                      | (trivial)                  |
| **Equivalence class**         | coset $aH$                        | affine subspace $v+W$            | coset $a+I$                      | —                          |
| **Quotient (L2 compression)** | $G/N$                             | $V/W$                            | $R/I$                            | (trivial)                  |
| **Map (L3)**                  | homomorphism                      | linear map                       | ring hom                         | field hom (injective)      |
| **Kernel**                    | $\ker f$ (normal subgroup)        | null space (subspace)            | $\ker f$ (ideal)                 | $\{0\}$                    |
| **Image**                     | $\operatorname{Im}(f)$ (subgroup) | range (subspace)                 | $\operatorname{Im}(f)$ (subring) | subfield                   |
| **1st Isomorphism Thm**       | $G/\ker \cong \operatorname{Im}$  | $V/\ker \cong \operatorname{Im}$ | $R/\ker \cong \operatorname{Im}$ | trivial                    |
| **Product/sum**               | $G \times H$                      | $V \oplus W$                     | $R \times S$                     | —                          |
| **Canonical form (L2 S3)**    | elementary divisors (f.g. ab.)    | Jordan / diagonal                | —                                | Galois data                |
| **Primary invariants**        | order, elem. divisors             | dim, Jordan structure            | char, cardinality                | char, degree, Galois group |

*L0 = Level 0, L1 = Level 1, L2 = Level 2, L3 = Level 3; S1/S2/S3 = Stage 1/2/3 of the classification workflow.*

---

## Key Asymmetries

**1. Fields are the most rigid structure.**
Fields have no nontrivial ideals, all homomorphisms are injective, and quotients are useless. Field theory works by **extension** (going up), not by quotient (going down). This is why Galois theory classifies field extensions rather than field quotients.

**2. Ideals are to rings what normal subgroups are to groups.**
Both are "substructures that are kernels of homomorphisms" and both are exactly what can be quotiented by. The parallel is exact.

**3. Vector spaces are the cleanest case.**
Every subspace gives a quotient; every finite-dimensional space is classified by dimension alone; every linear map has a clean kernel-image decomposition. Linear algebra is taught first precisely because it is the commutative, well-behaved instance where the general theory becomes fully computable.

**4. Modules generalize the abelian side, not everything.**
Modules unify abelian groups, vector spaces, and ring-acting structures into one theory. They do not unify non-abelian groups, which retain their own theory of conjugation, non-normal subgroups, and semi-direct products.

---

## One-line summary

**The same workflow — structure, substructure, generation, homomorphism, kernel, quotient, canonical form, invariants — plays out in every algebraic structure. Vector spaces are the cleanest case, fields the most rigid, groups and rings the main stage where normality and ideals do the heavy lifting, and modules are the unifying theory on the abelian side.**
