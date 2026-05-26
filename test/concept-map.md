# Smoke Test Concept Map: Scientific Philosophy and Statistical Inference

## Discipline Scope and Central Question

This smoke test covers a small chain from philosophy of science to statistical evidence. The central question is: how can scientific knowledge grow when observation cannot prove universal laws, and how can data count as evidence rather than mere measurement?

## Global Structure

1. Epistemic foundation: induction and the limits of proof.
2. Popperian response: conjectures, falsifiability, and critical testing.
3. Probability foundation: probability as belief or long-run frequency.
4. Statistical evidence: p-values, Bayesian updating, and likelihood ratios.

## Dependency Overview

The induction problem creates pressure on simple verification. Popper's falsifiability answers by shifting science from proving theories to exposing them to possible refutation. Statistical inference then asks a parallel question: once data arrive, what exactly has been learned? The frequentist, Bayesian, and likelihood answers differ because they treat probability and evidence differently.

## Concept Entries

### C01 - Induction Problem

- ID: C01
- Summary: The induction problem says finite observations cannot logically prove a universal rule. Even many past successes do not guarantee future success. It matters because it blocks the simple idea that science grows by collecting enough confirming cases.
- Layer: Epistemic foundation
- Predecessors: None in this smoke test
- Successors: C02, C04, C05
- Historical or logical position: Starting problem for modern philosophy of science and statistical inference.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, First layer.
- Confidence: High
- Key relationships: Creates the need for falsifiability and motivates Bayesian responses to uncertainty.
- Common misunderstandings: It does not say learning is impossible; it says universal proof by observation is impossible.
- Fable hooks: A clerk cannot guarantee tomorrow's deliveries from yesterday's perfect ledger.

### C02 - Falsifiability

- ID: C02
- Summary: Falsifiability says a theory is scientific when it rules out some possible observations and therefore risks being wrong. This shifts science from verification to severe testing. It matters because it gives a demarcation rule and a story of knowledge growth through error removal.
- Layer: Popperian response
- Predecessors: C01
- Successors: C03
- Historical or logical position: Popper's answer to induction and logical positivist verification.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, Popper section.
- Confidence: High
- Key relationships: Depends on the asymmetry between confirmation and refutation.
- Common misunderstandings: Passing tests does not prove a theory true; it only shows it has survived those tests.
- Fable hooks: A recipe that forbids certain bad outcomes can be tested by trying to make them happen.

### C03 - Corroboration

- ID: C03
- Summary: Corroboration is the status a theory gains after surviving severe tests. It is not proof or final confirmation. It matters because it explains why scientists can provisionally rely on a theory while still treating it as fallible.
- Layer: Popperian response
- Predecessors: C02
- Successors: C04, C05
- Historical or logical position: Part of Popper's conjectures-and-refutations model.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, Popper section.
- Confidence: High
- Key relationships: Gives a temporary standing to a theory without solving induction by proof.
- Common misunderstandings: Corroboration is often confused with verification.
- Fable hooks: A chair that has held heavy sacks is trusted for now, but no one calls it unbreakable.

### C04 - P-value

- ID: C04
- Summary: A p-value is the probability of observing current or more extreme data assuming the null hypothesis is true. It is not the probability that the null hypothesis is true and not the probability that the result is a mistake. It matters because this confusion is common in empirical research.
- Layer: Frequentist statistical inference
- Predecessors: C01
- Successors: C05, C06
- Historical or logical position: Neyman-Pearson and frequentist testing tradition.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, Neyman-Pearson section.
- Confidence: High
- Key relationships: Relates data to a hypothetical long-run error procedure, not to belief in a hypothesis.
- Common misunderstandings: Treating p as P(H0 | data), evidence strength, or current error probability.
- Fable hooks: A warehouse alarm tells how often this alarm would ring under normal stock, not whether this box is certainly bad.

### C05 - Bayesian Posterior

- ID: C05
- Summary: A Bayesian posterior is the updated probability of a hypothesis after combining prior belief with the likelihood of the data. It directly answers how belief changes after evidence. It matters because it gives a mathematical response to learning under uncertainty but depends on prior choices.
- Layer: Bayesian statistical inference
- Predecessors: C01
- Successors: C06
- Historical or logical position: Bayesian answer to inverse probability.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, Bayesian section.
- Confidence: High
- Key relationships: Contrasts with C04 by asking P(H | D) instead of P(D | H).
- Common misunderstandings: Thinking the posterior comes from data alone.
- Fable hooks: A shopkeeper updates trust in a supplier after a delivery, but yesterday's trust still matters.

### C06 - Likelihood Ratio

- ID: C06
- Summary: A likelihood ratio compares how well two hypotheses predict the observed data. It treats evidence as relative support, separate from action decisions and prior belief. It matters because it clarifies what data alone say when comparing explanations.
- Layer: Likelihood inference
- Predecessors: C04, C05
- Successors: None in this smoke test
- Historical or logical position: Likelihood approach to evidence.
- Source evidence: `dev_notes/refs/科学哲学与统计推断.md`, Likelihood section.
- Confidence: High
- Key relationships: Separates evidence from frequentist decision rules and Bayesian belief updating.
- Common misunderstandings: Treating likelihood as posterior probability.
- Fable hooks: Two repair notes are compared by asking which one would have made today's failure less surprising.

## Cross-Branch Relationship Table

| From ID | Relation | To ID | Why it matters |
| --- | --- | --- | --- |
| C01 | motivates | C02 | Falsifiability answers the failure of verification. |
| C01 | motivates | C05 | Bayesian updating offers a formal answer to learning without certainty. |
| C02 | enables | C03 | Corroboration only makes sense after severe testing. |
| C04 | contrasts-with | C05 | P(D | H) differs from P(H | D). |
| C04 | contrasts-with | C06 | P-values track tail probabilities under a procedure; likelihood ratios compare hypotheses as evidence. |
| C05 | contrasts-with | C06 | A posterior mixes prior and data; likelihood ratios isolate relative data support. |

## Coverage Notes

This smoke test intentionally omits Kuhn, Lakatos, statistical power, confidence intervals, and likelihood intervals. The goal is to test skill workflow alignment, not full coverage.

## Concept ID Index

| ID | Concept | Layer | Summary cue |
| --- | --- | --- | --- |
| C01 | Induction Problem | Epistemic foundation | Observation cannot prove universal rules. |
| C02 | Falsifiability | Popperian response | Scientific theories must risk refutation. |
| C03 | Corroboration | Popperian response | Surviving severe tests is not proof. |
| C04 | P-value | Frequentist inference | Probability of data or more extreme data under H0. |
| C05 | Bayesian Posterior | Bayesian inference | Belief after prior and likelihood are combined. |
| C06 | Likelihood Ratio | Likelihood inference | Relative evidence between hypotheses. |
