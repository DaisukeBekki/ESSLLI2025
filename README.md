# ESSLLI2025 course: Composing Meaning via Dependent Types

by Daisuke Bekki (Ochanomizu University, Faculty of Core Research) [website](https://github.com/DaisukeBekki)

## Abstract

This course provides a comprehensive overview of Dependent Type Semantics (DTS), a proof-theoretic semantics of natural language based on dependent type theory. DTS marks a departure from the traditional model-theoretic semantic frameworks, with its uniform analysis of projective contents such as anaphora, presupposition, and conventional implicatures through the process of proof construction. I will also reflect on the extensive research and developments of DTS over the past decade, from empirical linguistic research to computational research.  The latter includes discussion on the integration of DTS and neural networks, which will shed light on our future prospects and provide insights into DTS's potential applications in computational linguistics.

# Course information

## Motivation and description

This lecture will provide a comprehensive overview of Dependent Type Semantics (DTS: Bekki (2014), Bekki and Mineshima (2017), Bekki (2023)), a proof-theoretic semantics of natural language based on dependent type theory.  DTS marks a departure from the traditional model-theoretic semantics
in that the meaning of a sentence is given by its verification condition, which is represented by a type interpreted via Curry-Howard isomorphism where propositions are types and proofs are terms.
In particular, DTS employs a type theory called \textit{underspecified dependent type theory} (UDTT), that is an extention of Martin-L\"of type theory (Martin L\”of 1984) with *underspecified types* (Bekki 2023).  An underspecified type corresponds to an open proof in type theory, and to a semantic representation of anaphora and presupposition triggers in linguistics.  This establishes a new correspondence between the meaning of natural language and type theory, shedding new light on both fields.

An underspecified type requres a proof of a given type (corresponding to the presupposition content) in its formation rule, and it substitutes a variable with the proof found in the proof search.
This mechanism of DTS serves as an uniform analysis of anaphora and presupposition through the process of underspecification, inheriting the ‘presupposition is anaphora’ paradigm (van der Sandt and Geurts 1991, van der Sandt 1992) and the anaphora resolusion is proof construction'' paradigm (Krahmer and Piwek1999, Piwek and Krahmer 2000).

This DTS setting not only provides a compositional semantic theory with descriptive power enough to cover a wide variety of linguistic phenomena but also gives novel explanations for classical puzzles such as anaphora accessibility and anaphoric potentials.
For example, the E-type anaphoric link in (1) is predicted to be accessible since a proof from _someone bought a car_ to the existence of a non-human entity is constructable in UDTT.

(1)  Someone bought [a car].  It is parked outside.

Meanwhile, anaphoric links, as listed in (2), are predicted to be inaccessible because the required proofs are not constructable:
This is because universal quantification, implication, and negation are represented by Pi-types, data types of functions from which the intended antecedents cannot be picked up.  This is an explanation purely based on the structures of proofs, fundamentally different from dynamic semantics.

(2) a. Everyone bought [a car].  *It is parked outside.
     b. If John bought [a car], it must be a Porsche.  *It is parked outside.
     c. John didn't buy [a car].  *It is parked outside.

Moreover, discourse theories such as DRT need to introduce an extra representational layer such as DRSs to distinguish the anaphoric potentials of (3a) and (3b), since the first sentences of (3a) and (3b) are truth-conditionally equivalent in model-theoretic semantics.

(3) a. A linguist was not present at the class.  He/she must be overslept.
      b. Not every linguist was present at the class.  *He/she must be overslept.

In DTS, (3a) and (3b) have different proof-theoretic statuses: The proof construction in (3a) is intuitionistic while that in (3b) is classical, the latter of which is not allowed in the intuitionistic setting of UDTT.  In other words, DTS explains the different anaphoric potentials of (3a) and (3b) by means of proof construction without assuming an extra semantic layer such as DRSs.

I will also reflect on the extensive research and developments over the past decade.
Given that the empirical coverage of DTS is getting broader, we will discuss, among other things, representations of generalized quantifiers in Sundholm (1989), Fox and Lappin (2005), and Tanaka (2014a); modality and factivity discussed in Ranta (1994), and Tanaka (2014b); the phenomena of coercion discussed in Luo (2010,2011,2012a,2012b), Asher and Luo (2012) and Kinoshita, Mineshima and Bekki (2018); a unified analysis of conventional implicatures and presuppositions in Bekki and McCready (2014) and Matsuoka, Bekki and Yanaka (2023).

## Course plan

### Monday

Overview of DTS as a compositional theory of meaning in terms of dependent type theory, including a theory of anaphora resolution and presupposition binding by combining type-theoretical notions such as underspecified types, type inference/checkuing, proof search, and proof conversions.

- Overview [Slides](Bekki2025ESSLLIday1.pdf) (27 pages)

Additional material:
- Pi-types (proposition depending on proofs) [Chapter 06](DTSbookChapter06.pdf)
- Sigma-types [Chapter 07](DTSbookChapter07.pdf)
- Enumeration types [Chapter 09](DTSbookChapter09.pdf)

### Tuesday

Introducing the semantic composition via DTS, starting from the type mismatch problem and inverse scope readings of quantifiers, we will reach the notion of _continuation_ to remedy the problems.  
Then, we will discuss the classical crossover paradigm and its interaction with quantifier raising.

- Syntax-Semantics transparency (from CCG to DTS) [Chapter 15](DTSbookChapter15.pdf)
- Quantification [Chapter16, section 3-4](DTSbookChapter16.pdf)
- Star-CCG [Chapter 17](DTSbookChapter17.pdf)

Take away message: Combination of continuation, CCG and DTS gives a unified solution to the scope and binding  

### Wednesday

This is an introduction to a unified analysis of the use of pronouns, or _dynamics_ of natural language.
We will start from introducing an extended logical language "Underspecified dependent type theory (UDTT)" and analyze the dynamics in line with "anaphora resolution as proof construction paradigm."

- UDTT and the underspecified types [Chapter 21](DTSbookChapter21.pdf)
- Coreference and BVA [Chapter 22](DTSbookChapter22.pdf), section 2-
- E-type anaphora [Chapter 23](DTSbookChapter23.pdf)
- Accessibility: universal, negation, conditional [Chapter 24](DTSbookChapter24.pdf)

Take away message: Anaphora accessibility is the derivability of a proof

### Thursday

We will discuss the analysis of presupposition and conventional implicature in DTS, including the theory of projection and accommodations.  I also compare DTS and dynamic semantics, particularly the two-dimensional semantics that suffers from the binding problem.  
Also planning to invite a 30-minute guest talk on the analysis of CIs in DTS.

- Presupposition [Chapter 26](DTSbookChapter26.pdf) [Slides](2025ESSLLI_matsuoka.pdf)
- 30 minutes guest talk on conventional implicatures by [Daiki Matsuoka](https://daiki-matsuoka.com/)

### Friday

Planning to invite two guest talks on implementations: the first talk will go over the current implementation of CCG parser and an automated theorem prover for DTS using the Haskell programming language.  The second talk will investigate the implementation of Neural DTS, an integrated framework of DTS and neural networks.  This will provide insights into the potential applications of DTS in computational linguistics.

- 30 minutes guest talk on the implementation of CCG and DTS by [Asa Tomita](https://morning85.github.io/) 
- 30 minutes guest talk on the neural approach toward CCG and DTS by [Sora Tagami](https://bluesky0906.github.io/) 
- 30 minutes lecture on the computational verificatoin of linguistic theory by Daisuke Bekki [Slides](Bekki2025ESSLLIday5.pdf) (26 pages)

### Alternative materials

- Disjoint union types [Chapter 08](DTSbookChapter08.pdf)
- Accessibility II: Disjunction paradigm and killer examples [Chapter 24](DTSbookChapter24.pdf)
