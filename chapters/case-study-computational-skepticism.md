# Case Study: Computational Skepticism for AI
## Teaching the Full Validation Pipeline as a Cognitive Discipline

*Category: Course Design / Tiers 4 & 5 — Integrative*
*Theory connection: The solve-verify asymmetry at full scale — what a complete
semester-long validation pipeline looks like when every component is designed
to develop the capacities AI cannot perform*

---

### The Causal Question

Can the cognitive disciplines of computational skepticism — plausibility auditing,
causal reasoning, bias detection, adversarial robustness, accountability — be
developed simultaneously across a semester, and what assessment architecture
makes the development visible rather than merely the artifacts?

---

### The Premise

The most dangerous AI failure is not the one that crashes visibly. It is the one
that produces a plausible answer to the wrong question — a statistically valid
output on a causally incoherent claim, a bias-amplifying model deployed by people
who had the technical skill to build it and the wrong conceptual framework to
question it.

This course is the conceptual framework.

The premise distinguishes Computational Skepticism from every other AI course in
the curriculum. Other courses teach students to build models. This one teaches
students to evaluate whether models should be trusted — and to name, precisely,
what trust requires and where it fails. The outcome is not a model. It is a
validated judgment about a model, with the reasoning documented and the
limitations acknowledged.

---

### The Course Architecture

INFO 7375 is a fourteen-week graduate seminar at Northeastern University,
organized in six parts tracking the arc from foundational skepticism through
the full technical validation infrastructure through the ethical and philosophical
territory the technical tools cannot resolve alone.

**Part I — Foundations of Computational Skepticism (Weeks 1–4)** establishes
the epistemological ground. The course opens with Descartes, Hume, and Popper
not as intellectual history but as working methodology: what does rigorous doubt
actually require, and what does it look like applied to AI systems? The
Solve-Verify Asymmetry — introduced at Week 1 and deepened throughout — is
the course's structural thesis: AI systems solve faster than any human, and
that gap will widen; what will not change is that verification requires exactly
the capacities AI cannot supply.

Week 4 introduces the Frictional framework directly as course content — the
GLP components, the prediction-lock mechanism, the neurobiological argument for
why genuine learning leaves traces that artifact quality alone cannot demonstrate.
This week is the course's explicit metacognitive mirror: before students can
apply computational skepticism to AI systems, they must apply it to their own
learning. The first complete GLP entry — reconstructing a prior prediction and
documenting the gap between prediction and outcome — is the Glimmer exercise
for this week.

**Part II — Data, Models, and Validation Systems (Weeks 5–8)** builds the
technical validation infrastructure piece by piece. Data validation (Week 5),
model explainability (Week 6), bias detection (Week 7), adversarial robustness
(Week 8). Each week has a specific Glimmer exercise that is not merely
technical — it requires a judgment that the technical tools cannot make.

The explainability week is the sharpest example. Students implement SHAP and
LIME explanations for a provided model, then are required to identify at least
one case where the explanation is technically accurate and practically misleading.
The deliverable is not the explanation. It is the documentation of why a
practitioner acting on this explanation would make a worse decision than one
who ignored it. Technically accurate, practically misleading is the failure
mode that most explainability training never surfaces — because most
explainability training stops at the technical layer.

Pearl's Ladder threads through Part II deliberately. Rung 1 (observation) and
Rung 2 (intervention) are introduced at Week 3. Rung 2 is deepened at Week 6
when the difference between an explanation and a causal claim is examined
directly. Rung 3 (counterfactual) is introduced at Week 8 through adversarial
robustness — the robustness counterfactual asks what would have happened if the
input had been slightly different, and why the model's answer to that question
reveals what it had not actually learned.

**Part III — Agency, Delegation, and Human-AI Systems (Weeks 9–10)** addresses
the delegation layer. Week 9 examines reinforcement learning and the reward
function as a moral structure — students design a reward function, predict what
emergent behaviors it will produce, then document the gap between intended and
actual emergence. Week 10 builds a delegation map for the research project using
the Gru tool: for every component of the validation pipeline, what does the AI
do, what does the student do, and what is the explicit, testable handoff
condition between them.

The delegation map is the course's most direct instantiation of the Botspeak
framework applied to technical work. The student who can specify, in advance,
the exact criterion that must be true about an AI output before they accept it
as input to the next step has developed a form of Tier 4 metacognitive control
that most technical training never requires.

**Part IV — Visualization, Communication, and the Epistemics of Presentation
(Weeks 11–12)** teaches computational skepticism applied to the presentation
layer. Week 11 requires students to build an honest visualization of their
research project findings — and then deliberately redesign it to be misleading
using the same data. The reflection on what the misleading redesign required
them to do is the exercise. Week 12 is a structured peer critique using the
course's validation framework.

**Part V — Ethics, Governance, and the Limits of the Technical (Weeks 13–14)**
completes Pearl's Ladder. Week 13 applies the counterfactual at the governance
level: for documented AI ethics violations, what governance mechanism, if
implemented earlier, would have caught the failure? The governance counterfactual
closes the arc that opened with bias at Week 3. Week 14 addresses what AI
cannot do — meaning, understanding, intentionality — not as a philosophical
coda but as the final safety mechanism: skepticism as a required operating
condition for AI deployment, not a temporary stance while better systems are
being built.

---

### The Frictional Journal and the Changelog History

The course's most structurally novel feature is the assessment architecture
built around process evidence rather than artifact quality alone.

Every Glimmer exercise submission has two required components: the artifact
(the analysis, documentation, or designed output specified in the exercise
prompt) and the Frictional Journal entry — a prediction made before the work
begins, a reflection completed immediately after, and a trace entry for certain
exercises. The prediction is timestamped before the student starts. It cannot
be written after the fact.

The prediction-lock mechanism addresses the decoupling problem directly. In
an era when AI can produce any artifact on demand, the artifact alone is not
evidence that the student understood what they were doing. The prediction is.
A student who predicted the correct failure mode before running an adversarial
attack has demonstrated something that cannot be produced by generating the
artifact without engagement. A student who predicted confidently and incorrectly
has produced equally useful evidence — of what their mental model of the system
got wrong, which is exactly the kind of evidence the course is designed to
surface.

The Changelog History performs the same function at the scale of the semester.
The research project is presented four times in increasingly developed versions.
Each version except the final requires a Changelog Slide: what changed since
the last version, what drove the change, what the previous version got wrong
or incomplete, and what still might be wrong in this version. The Changelog
History — all prior Changelog Slides collected and submitted alongside the
final paper — is a graded component of the final submission. A final paper
submitted without its Changelog History is an incomplete submission.

The Changelog History is the research project's Frictional evidence record.
It documents a semester of genuine engagement with a real system — the
predictions made, the failures encountered, the updates forced by evidence.
No AI-assisted workflow produces this document without the cognitive work
the document is designed to evidence.

---

### The Calibration Baseline

The Calibration Baseline runs three times — at Weeks 2, 8, and 14. Five
questions each time, each requiring a confidence rating before answering.

It is not graded. It produces a developmental portrait: a record of whether
the student is becoming better at knowing what they know, not just knowing
more. The trajectory across three administrations is returned to each student
individually at the end of the course.

The Calibration Baseline is the course's Tier 4 development instrument — a
direct measure of uncertainty calibration, the capacity to match expressed
confidence to actual accuracy. The student who arrives with high confidence
and low accuracy and leaves with calibrated confidence has developed exactly
the metacognitive capacity the course targets. The student whose calibration
has not changed has completed the technical work without developing the
judgment that makes the technical work trustworthy.

---

### The AI Use Disclosure as Assessment Instrument

The AI Use Disclosure is a graded criterion in every submission. The final
field is not optional:

> *What the AI could not do: at least one specific judgment call that required
> your values, domain knowledge, or accountability — not a category claim,
> a specific instance.*

The course specifies what this field requires: not "AI cannot understand
context" — that is a category — but something like "the model produced a
confidence interval that was technically correct but did not account for the
non-stationarity in the underlying data. It had no way to know that the
measurement protocol changed in Q3 — I know that because I designed the study."

That specificity is the assessment. A disclosure that cannot produce a concrete
instance has not demonstrated that the student performed the Tier 4 supervisory
layer. The disclosure is not a compliance checkbox. It is a supervisory capacity
log, repeated across every submission, building a semester-long record of what
the student supplied that the tool could not.

---

### The Quality Score Architecture

Twenty percent of every graded component is norm-referenced — evaluated relative
to the cohort, not against a fixed standard.

This design choice reflects a specific argument about how professional evaluation
works. Hiring committees, grant reviewers, peer review panels, and editorial
boards all involve relative judgment: how does this work compare to what others
produced with the same resources? Because every student in the course has access
to the same tools, the quality of work relative to peers is meaningful signal.

The quality score rewards evidence of genuine engagement: iteration, domain
judgment, validation rigor, thinking that visibly changed in response to the
material. Work that demonstrates minimal engagement — technically complete
artifacts without friction traces, Changelog Slides that record version numbers
without recording what changed or why — scores at the bottom. The Frictional
Journal entry is the primary evidence for the quality score: a submission without
a journal entry, or with a journal entry clearly written after the work was
finished, cannot demonstrate what the quality score is measuring.

---

### Pearl's Ladder as Course Arc

The course's deliberate threading of Pearl's Ladder across fourteen weeks is
worth describing as a pedagogical design decision rather than a content choice.

Most courses that teach causal reasoning introduce the framework and move on.
Computational Skepticism returns to Pearl's Ladder four times across the semester,
at increasing depth and in different applied contexts:

- **Week 3**: Rung 1 (observation) and Rung 2 (intervention) introduced through
  bias — where does bias enter, and what intervention at each point would and
  would not address it
- **Week 6**: Rung 2 deepened through explainability — the difference between
  an explanation that describes a pattern and an explanation that supports a
  causal intervention
- **Week 8**: Rung 3 (counterfactual) introduced through adversarial robustness —
  what would have happened if the input had been slightly different
- **Week 13**: The governance counterfactual — what mechanism, if implemented
  earlier, would have caught the failure

The arc is not incidental. It is the course's causal reasoning development
track, building from observation through intervention to counterfactual over
the full semester. Each return to the ladder adds a layer that the prior
encounters had not yet required. By Week 13, students who have been working
with Pearl's Ladder for ten weeks are applying it to governance questions —
the full Rung 3 capacity — in a domain where the stakes are not technical
but institutional and ethical.

---

### The Tier Mapping

Computational Skepticism is the integrative course in the series — the one
where the tier taxonomy is applied simultaneously across all the capacities
the other courses develop in isolation.

**Tier 1 (Pattern & Association)** is what the tools do. Students use them
freely. The course explicitly invites and requires it.

**Tier 4 (Metacognitive & Supervisory)** is the course's primary developmental
target. The Frictional Journal, the prediction-lock, the delegation map, the
AI Use Disclosure, the Calibration Baseline — all of these are Tier 4
instruments targeting plausibility auditing, problem formulation, tool
orchestration, and interpretive judgment.

**Tier 5 (Causal & Counterfactual)** is developed through Pearl's Ladder across
the full semester. The bias trace, the explainability critique, the adversarial
failure mode analysis, the governance counterfactual — each is a Tier 5 exercise
requiring the student to reason from observation toward intervention and
counterfactual.

**Tier 7 (Existential & Wisdom)** appears at the edges — in the accountability
week, in the philosophical limits week, in the AI Use Disclosure's accountability
field. The course does not claim to develop practical wisdom. It creates the
conditions in which students encounter its requirements under real stakes:
real AI systems, real failure modes, real validation claims they must defend
under adversarial peer critique.

---

### What the Course Claims and What It Doesn't

The course claims that computational skepticism — the cognitive discipline of
rigorous doubt applied to AI systems — can be developed across a semester through
a combination of technical validation exercises, process evidence documentation,
and repeated engagement with the causal reasoning infrastructure Pearl's Ladder
provides.

The course does not claim that a student who completes it is a finished AI
validator. The Calibration Baseline trajectory is the honest measure of what
changed. A student whose calibration improved — who became better at knowing
what they know — has developed a durable capacity. A student who completed
the technical exercises without friction traces has not demonstrated the same
development.

The course does not claim that its assessment architecture solves the decoupling
problem. The prediction-lock mechanism and the Changelog History are the best
currently available response to the problem — not a final solution. As AI systems
improve, the question of what constitutes genuine engagement will require
continuous redesign.

The most honest statement of what the course delivers is in the AI Use Disclosure
format it requires of students: at the end of the semester, can the student name,
concretely and specifically, what they supplied to the validation work that the
tool could not have supplied? If yes, the course worked. If the student can
only gesture at categories — "AI cannot understand context," "AI lacks domain
knowledge" — the development is incomplete.

---

### The Connection to the Broader Argument

The factory model curriculum produced engineers who could build models. It did
not produce engineers who could evaluate whether models should be trusted.
The distinction was costless when the models were narrow and the deployment
was supervised. It is not costless when AI systems are making consequential
decisions in medical, legal, financial, and governance contexts with minimal
human oversight.

Computational Skepticism is the course that treats the evaluation problem as
the primary engineering problem — not a secondary check to be run after the
interesting work is done, but the work itself. The validation pipeline is not
a quality control layer appended to the development process. It is the cognitive
discipline that determines whether the development process produced something
trustworthy.

The student who completes the course can stand in front of an AI system, apply
the full validation pipeline, and say — specifically, with evidence, with
acknowledged uncertainty — what this system can be trusted to do, what it
cannot, and what a practitioner deploying it needs to know that the performance
metrics alone would not tell them.

That is not a technical skill. It is a judgment capacity. It is what the course
is for.

---

*Source: Brown, N.B. (2026). "INFO 7375: Computational Skepticism for AI."
Course syllabus, Northeastern University, Khoury College of Computer Sciences /
College of Engineering. Graduate seminar.*
