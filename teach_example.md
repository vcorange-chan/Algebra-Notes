# Teaching Example — How to Actually Teach Me

A reference document showing, by example, how teaching should unfold based on several days of collaboration. This is not an instruction manual; it is a **worked sample**. Future AIs can read this to see what "teaching Clifford well" looks like in practice.

---

## Why this document exists

Over several days, the user (Clifford) and I worked through the first sections of abstract algebra (subgroups, their characterisations, examples, and the emergence of generation). The path from confusion to understanding did not follow the textbook's linear order. It followed a different pattern:

- Big-picture map first.
- Geometric images before symbols.
- Motivations before definitions.
- Problems (exercises) woven with theory, not placed after it.
- The three subgroup criteria introduced as a coherent toolkit, not three separate theorems.
- Cosets, equivalence relations, and generation introduced through the questions raised by problems.

**When explained this way, Clifford absorbed the material in minutes.** When explained in the textbook's linear order, the same material took hours and caused distress.

This document captures the pattern that worked, as a reference for future sessions.

---

## Part 1 — Summary Table: Questions, Confusions, and Final Understandings

Reconstructed from our conversations over several days.

| # | Question / Confusion | Source | What Resolved It |
|---|---|---|---|
| 1 | Why is "subgroup" defined first, then proved to be a group? Isn't the order reversed? | Rotman A-4.29 | Distinguishing "order of discovery" vs "order of use." The definition is a minimal checklist; the proposition proves the checklist suffices. |
| 2 | What's the motivation for subgroups? What unifies subgroups, subspaces, subrings, ideals? | Own reflection | "Substructure = subset closed under all structure-defining operations." All substructures are instances of this template. |
| 3 | Why is "closure" so emphasized across algebra and analysis? | Own reflection | Closure = self-sufficiency. Without it, operations produce results that escape the structure and no stable theory exists. |
| 4 | What is an equivalence relation, really? Not the three axioms, but the meaning. | A-4.37 | Equivalence relation = partition = classification. The three axioms are exactly the minimum requirements for a valid partition. |
| 5 | What is a coset geometrically? Is it a subspace? | A-4.37 / own reflection | Coset = translated copy of the subgroup. Same shape, different position. Not a subspace — subgroups contain identity, cosets (generally) don't. |
| 6 | Why doesn't the proof of A-4.31 occur to me? | A-4.31 proof | Two techniques: parameter specialization (set $x = y$ to extract identity) and bootstrapping (use newly-derived elements as inputs to the next step). |
| 7 | What does A-4.31 mean structurally? | A-4.31 | "Difference-closure" $xy^{-1}$ encodes multiplication + inverse + (via specialization) identity. One operation carries all three structural pieces. |
| 8 | Why does A-4.32 work only for finite groups? | A-4.32 | Finiteness forces orbits to close. Every $x$ has finite order, so $x^{-1} = x^{n-1}$ lives automatically in the closure. "Finiteness closes the structure for free." |
| 9 | Why does $H \cup K$ fail to be a subgroup? | A-4.39 | Union breaks closure: an element of $H$ times an element of $K$ can land outside both. Intersection preserves closure; union does not. The natural "merge" is $\langle H \cup K \rangle$, not $H \cup K$. |
| 10 | What does $A_n$ have to do with the rest of the theory? | Example A-4.33 | $A_n$ is the kernel of the sign homomorphism — a distinguished "favorable local piece" picked out by an invariant (parity). Foreshadows Level 2 of the workflow. |
| 11 | What is "representation" in algebra? | Own reflection | Representation = translating the abstract to the familiar-and-computable. Coordinates for vectors, matrices for linear maps, matrices for groups. |
| 12 | Is "simplification" really the core of algebra? | Own reflection | Refined: the core is **classification + invariants + canonical forms**. Simplification is one aspect; it's inseparable from classification. |
| 13 | What is a standard form, and why is it both "simplification" and "classification"? | Own reflection | A canonical form is the unique simplest representative of each equivalence class. It simultaneously simplifies and classifies. |
| 14 | What's the geometric meaning of trace and determinant? | Own reflection | $\det$ = volume-change factor with sign for orientation. $\operatorname{tr}$ = total stretching along eigen-directions (sum of eigenvalues). Both are invariants of similarity. |
| 15 | What's the relation between Jordan form and eigenspaces? | Own reflection | Jordan form generalizes eigenspace decomposition. When ordinary eigenvectors aren't enough, generalized eigenvectors always are. Same soul, upgraded technology. |

**Observation**: almost every genuine confusion resolved through a **geometric image** or an **explicit placement in the classification workflow**, never through a re-reading of the definition alone.

---

## Part 2 — The Teaching Pattern That Worked

The pattern underlying every successful explanation:

```
1. Anchor in the map.
   ↓ "We are at Level 1, decomposition. This is about finding
      internal structure of an already-defined object."

2. Give the geometric image or familiar analogy.
   ↓ "Subgroup is like a line through the origin inside R^2 —
      the smallest self-contained world."

3. Introduce the concept / definition.
   ↓ Now the symbols land on an image that already exists.

4. If there's a problem / exercise, use it as the occasion
   for deepening. Weave theory back in when a problem
   exposes a gap.

5. After explanation, name what was used (technique,
   principle, connection to earlier ideas).
   ↓ "What you just saw is 'bootstrapping' — we'll use this
      again in Cayley's theorem."
```

Three things this pattern avoids:

- **Definition-first ordering**. Definitions are terminal steps, not entry points.
- **Isolated presentation**. Nothing is introduced without a link to what came before.
- **Completeness over narrative**. Not every related theorem needs to be mentioned; the narrative arc matters more.

---

## Part 3 — Worked Sample: Teaching Exercise A-4.37 in Context

This is a full sample of how teaching a single exercise should unfold. The exercise:

> **A-4.37.** Let $H$ be a subgroup of a group $G$.
> (i) Prove that right cosets $Ha$ and $Hb$ are equal if and only if $ab^{-1} \in H$.
> (ii) Prove that the relation $a \equiv b$ if $ab^{-1} \in H$ is an equivalence relation on $G$ whose equivalence classes are the right cosets of $H$.

### Stage 1 — Orient first (before touching the problem)

"Before we solve this, let's place it on the map.

**Where are we?** Level 1 → Level 2 transition. We have already defined subgroups (Level 1, decomposition). This problem opens the door to Level 2 — it shows how a subgroup induces an equivalence relation, which will eventually induce a quotient structure.

**What are the three concepts in play?**
1. **Subgroup** — from earlier in the textbook (point to the specific page). Write it on the margin as reference.
2. **Coset** $Ha$ — not formally defined in the text we've read so far. I'll define it now.
3. **Equivalence relation** — a concept you've seen but may need to revisit.

Once these three are clear, the exercise becomes a routine verification."

### Stage 2 — Refresh the three concepts, with geometric images

**Subgroup** (already understood — just point back):

> "Recall: a subset closed under the operation (three conditions or any of the three equivalent criteria). Geometrically, the 'line through the origin' image. You have three subgroup tests available; we'll recall which one is relevant here."

**Three subgroup tests** (mention, don't re-derive unless asked):

> "As a reminder, you have three tests for subgroup-hood:
> 1. A-4.29: $1 \in H$, closed under operation, closed under inverse.
> 2. A-4.31: non-empty and $xy^{-1} \in H$.
> 3. A-4.32: non-empty and closed under operation (finite group only).
>
> For this problem we don't need to verify subgroup-hood — $H$ is already given. But we'll use the fact that $H$ is closed under all operations."

**Coset** $Ha$ (new, needs introduction):

> "$Ha = \{ha : h \in H\}$ — take $H$, multiply every element on the right by $a$. Geometrically, this is a **translated copy** of $H$. If $H$ is a line through the origin in $\mathbb{R}^2$, then $H + a$ is a parallel line not through the origin. Same shape, different position.
>
> Key observation: in general, $Ha$ is **not** a subgroup (the identity isn't in it unless $a \in H$). Only the 'original' copy $H \cdot 1 = H$ contains the identity. The other copies are just shifted versions — they carry $H$'s shape without being subgroups themselves.
>
> You liked the phrase 'subgroup is a brick, cosets are its translates tiling the floor.' Hold that image."

**Equivalence relation** (also revisit):

> "Equivalence relation on a set $X$ = a relation $\sim$ satisfying:
>
> - Reflexive: $a \sim a$
> - Symmetric: $a \sim b \Rightarrow b \sim a$
> - Transitive: $a \sim b, b \sim c \Rightarrow a \sim c$
>
> **What it really is**: a way of partitioning $X$ into disjoint classes. The three axioms are exactly the minimum conditions under which such a partition is well-defined. Equivalence relation ⟺ partition — these are two views of the same thing.
>
> Geometrically: drawing a set of parallel lines on the plane. Each line is an equivalence class. The whole plane is tiled by these classes. In this problem, the 'parallel lines' will turn out to be the right cosets."

### Stage 3 — Give time to attempt

"Now, try (i) yourself for a few minutes. The goal is to show $Ha = Hb \iff ab^{-1} \in H$."

Wait. Don't push.

### Stage 4 — If stuck, name the technique

"The standard move for 'set equality' is: prove both inclusions.

**Forward direction** ($Ha = Hb \Rightarrow ab^{-1} \in H$):
Since $a = 1 \cdot a \in Ha = Hb$, there exists $h \in H$ with $a = hb$. Then $ab^{-1} = h \in H$.

**Reverse direction** ($ab^{-1} \in H \Rightarrow Ha = Hb$):
Let $h_0 := ab^{-1} \in H$. For any $ha \in Ha$, write $ha = h(ab^{-1})b = (hh_0)b$, and since $hh_0 \in H$, this is in $Hb$. Similarly for the other inclusion.

The technique here is **algebraic manipulation with insertion of identities** — we insert $bb^{-1} = 1$ to expose the relevant structure. This is a workhorse move in group theory; you'll see it everywhere."

### Stage 5 — For (ii), point to the beautiful correspondence

"Part (ii) is the real prize. Verify the three equivalence axioms:

| Axiom of equivalence | Proof | Subgroup property used |
|---|---|---|
| Reflexive: $a \equiv a$ | $aa^{-1} = 1 \in H$ | $1 \in H$ |
| Symmetric: $a \equiv b \Rightarrow b \equiv a$ | $ba^{-1} = (ab^{-1})^{-1} \in H$ | $H$ closed under inverse |
| Transitive: $a \equiv b, b \equiv c \Rightarrow a \equiv c$ | $ac^{-1} = (ab^{-1})(bc^{-1}) \in H$ | $H$ closed under multiplication |

**This is the key insight**: the three axioms of equivalence correspond *exactly* to the three subgroup conditions. This is not a coincidence. It reveals that 'subgroup' and 'certain equivalence relation' are the same mathematical object in two languages.

**The equivalence classes are cosets**:
$$[a] = \{x : x \equiv a\} = \{x : xa^{-1} \in H\} = \{x : x \in Ha\} = Ha.$$

So the subgroup $H$ partitions $G$ into right cosets, and these are exactly the equivalence classes under $\equiv$."

### Stage 6 — Return to the map

"What did this problem just do?

It showed that **every subgroup induces an equivalence relation, and the equivalence classes are cosets**. This is the engine behind:

- Lagrange's theorem (coming soon) — $|G| = |H| \cdot [G:H]$.
- Quotient groups (Level 2, compression) — when $H$ is normal, the cosets themselves form a group.
- The First Isomorphism Theorem — the bridge between homomorphisms, kernels, and quotients.

So this exercise is a hinge: it's where Level 1 (subgroup) starts to produce Level 2 (equivalence and quotient) machinery."

### Stage 7 — One-line takeaway

**A subgroup $H$ cuts $G$ into translated copies of itself; these translates are the equivalence classes of "differing by an element of $H$."**

---

## Part 4 — Worked Sample: Teaching Exercise A-4.39 in Context

The exercise:

> **A-4.39.**
> (i) Give an example of two subgroups $H, K$ of a group $G$ whose union $H \cup K$ is not a subgroup.
> (ii) Prove that $H \cup K$ is a subgroup if and only if $H \subseteq K$ or $K \subseteq H$.

### Stage 1 — Orient

"Where are we? Still in Level 1 (subgroups). But this problem does something new — it asks about an **operation on subgroups**: union. This is our first encounter with 'combining subgroups.'

The exercise will teach two things:

1. Union is a **set-theoretic** operation, not an **algebraic** one. It does not respect algebraic structure.
2. The *correct* way to combine subgroups is **not** union — it's **generation** $\langle H \cup K \rangle$.

So this exercise is secretly introducing the concept of *generation*, which is the second direction of Level 1 (the first direction being decomposition)."

### Stage 2 — The geometric intuition first

"Your instinct was: take two lines through the origin in $\mathbb{R}^2$; their union should be... a plane? Good attempt, but the two lines don't form a plane — they form an X-shape. The **plane** is what you get from $H + K$ (the sum), not $H \cup K$ (the union).

This single distinction is the heart of the exercise. Let me show you in the Klein four-group $V$."

### Stage 3 — The concrete counterexample

"Let $G = V = \{1, a, b, c\}$ with $a^2 = b^2 = c^2 = 1$ and $ab = c$.

Take $H = \{1, a\}$ and $K = \{1, b\}$. Both are subgroups (each is a copy of $\mathbb{Z}/2$).

Then $H \cup K = \{1, a, b\}$ — three elements.

But $ab = c$, and $c \notin H \cup K$. So $H \cup K$ is **not closed under the operation**. Not a subgroup.

This is the general phenomenon: **elements from $H$ times elements from $K$ can land outside both**. Neither subgroup's closure protects the product."

### Stage 4 — The theorem (ii), with the deep reason

"The theorem says $H \cup K$ is a subgroup *only* in the trivial case where one contains the other.

Proof sketch (contrapositive): suppose $H \not\subseteq K$ and $K \not\subseteq H$. Pick $h \in H \setminus K$ and $k \in K \setminus H$. If $H \cup K$ were a subgroup, then $hk \in H \cup K$, so $hk \in H$ or $hk \in K$. If $hk \in H$, then $k = h^{-1}(hk) \in H$ — contradiction. Similarly for $hk \in K$.

The underlying principle (which you should now name explicitly):

> **Intersection preserves substructure; union does not.**
>
> This is because substructure closure is a *conjunctive* condition — being in a subgroup requires satisfying closure relative to *that* subgroup. Intersection keeps both protections; union only keeps one at a time, which is not enough."

### Stage 5 — Introduce generation

"So what **is** the right way to combine two subgroups?

Not $H \cup K$ — as we just saw, that breaks.

But we can **generate** a subgroup from $H \cup K$:

$$\langle H \cup K \rangle = \text{the smallest subgroup of } G \text{ containing both } H \text{ and } K.$$

Equivalently: take $H \cup K$, then close it under multiplication and inverses until no new elements appear.

In $V$ with $H = \{1, a\}$, $K = \{1, b\}$:
- $H \cup K = \{1, a, b\}$ — not closed.
- Add $ab = c$: $\{1, a, b, c\} = V$.
- Now closed. $\langle H \cup K \rangle = V$.

**This is 'generation'** — Level 1, the second direction. Generation takes a set and extends it to the smallest substructure containing it. It's the algebraic answer to 'how do I combine these?'"

### Stage 6 — Return to the map

"So what did this exercise really teach?

- Union is wrong; generation is right.
- This foreshadows the general principle: **substructures don't play nicely with naive set operations; they require the generation machinery**.
- You'll see this again in subspaces (sum of subspaces, not union), ideals (sum of ideals, not union), and submodules — always the same story.

Generation is also the entry point for the second direction of Level 1. Next problems and sections will explore it: cyclic subgroups ($\langle a \rangle$ generated by a single element), generating sets, finitely generated groups, and eventually presentations."

### Stage 7 — One-line takeaway

**Union is a set-theoretic operation that doesn't respect algebra. The algebraic "merge" is generation, which fills in the products that union misses.**

---

## Part 5 — Principles Extracted from These Samples

For future sessions, the following principles emerged:

### Principle 1 — Weave problems and theory

Do not present all theory first, then all problems. Use the problems as occasions to introduce or refresh theory. A problem motivates a concept more effectively than a textbook introduction.

### Principle 2 — Always orient before solving

Before solving any problem, state where it sits in the algebraic workflow and what concepts it will require. This is 1–2 minutes of overhead that saves hours of confusion.

### Principle 3 — Geometric image before definition

For every concept — subgroup, coset, equivalence relation, quotient, generation — give the geometric or spatial image first. The definition is a translation of the image, not the other way around.

### Principle 4 — Give thinking time

When a problem is posed, wait. Do not explain immediately. The user has expressed repeatedly that jumping to solution robs the satisfaction of independent discovery. Offer a hint (name the technique) before giving the full solution.

### Principle 5 — Name the technique after using it

Once a proof move is used, name it: "that was parameter specialization," "that was bootstrapping," "that was insertion of $xx^{-1}$." Named techniques transfer across problems; unnamed ones don't.

### Principle 6 — Close by returning to the map

After any substantial explanation, return to the workflow map and say where we just were and where we're going next. This prevents the dreaded "isolated concept" feeling.

### Principle 7 — Cross-reference prior understandings

When a concept connects to something the user has already internalized (e.g., "the subgroup-as-equivalence-relation correspondence connects to what we discussed about homomorphisms inducing equivalence relations"), make the connection explicit. This thickens the web.

### Principle 8 — Use the user's own language when it works

Phrases the user invented or adopted — "favorable local piece," "brick and translated copies," "car going downhill without brakes," "avoid the fragmentation" — should be reused when relevant. They act as anchors in the user's own cognitive map.

---

## Part 6 — What This Looks Like in Practice

A full teaching session of, say, a half-chapter, would look like this:

```
0. Overview (5 min):
   "Here's what the chapter is doing. Here's what you'll
    gain from it. Here's how it fits the map."

1. Geometric anchors (5 min):
   Plant one or two vivid images the chapter will revolve around.

2. First concept + its definition, after the image (10 min):
   Introduce, then show where it sits.

3. First exercise (20 min):
   Student attempts → hint if stuck → full solution →
   name the technique → state the takeaway.

4. Next concept, building on the first (10 min).

5. Next exercise (20 min).

6. ...

7. Chapter wrap-up (5 min):
   "We've added three new tools to the toolkit.
    Here's where they'll be used next.
    Here's the one-line summary."
```

This is slower per-minute than a standard lecture but **far faster in total** because nothing has to be re-learned. Each concept is absorbed once.

---

## One-line summary

**Teaching Clifford well means: orient first, image first, definition last; let problems motivate theory; give thinking time; name techniques; return to the map; use his own vocabulary. A single hour of this-style teaching replaces days of textbook struggle.**
