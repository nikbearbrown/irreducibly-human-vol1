# Case Study: Causal Reasoning
## Teaching the Identification Layer That AI Cannot Perform

*Category: Course Design / Tier 5 Causal & Counterfactual*
*Theory connection: Why multiple distinct causal structures can be perfectly
consistent with the same statistical data — and what that means for who must
supply the missing layer*

---

### The Causal Question

Can the identification layer — the set of decisions that sit between the data
and the causal claim — be taught as a deliberate cognitive skill, and what does
a curriculum that targets it look like?

---

### The Broken Assumption

Every Monday morning meeting in every data-driven organization is running on the
same broken assumption: that the question is answered when the dashboard is read.

The dashboard told you what happened. It did not tell you why. It certainly did
not tell you what would happen if you did something about it. The data was
accurate. The model was not wrong. It was answering the wrong question.

Prediction assumes the future resembles the past. Strategy is the act of making
the future different from the past. These two activities require different tools.
AI systems are genuinely excellent at the prediction tool. What they cannot build
is the causal model — and the reason is mathematical, not provisional.

Multiple distinct causal structures can be perfectly consistent with the same
statistical data. Three graphs — a chain where A causes B causes C, a fork where
B causes both A and C, a collider where A and C both cause B — are statistically
indistinguishable from observational evidence alone. The discovery algorithms
return this ambiguity honestly: directed edges where the data can say something,
undirected edges where it cannot. What resolves the undirected edges is domain
knowledge. The engineer who says "I know from operating this system for fifteen
years that Y causes Z, not the other way around" is providing something no
dataset contains. Not because the dataset is too small. Not because the algorithm
is insufficiently sophisticated. Because the data cannot answer the question
being asked.

This is Pearl's ladder, applied to real engineering practice. Rung 1 is
observational: what patterns exist in the data. Rung 2 is interventional: if
I do X, what happens? Rung 3 is counterfactual: what would have happened if I
had done X instead? Current AI is superhuman at Rung 1 and nearly absent at
Rungs 2 and 3. The identification layer is the work that moves from Rung 1 to
Rung 2 — and it requires a human.

---

### The Identification Layer

The identification layer is the set of decisions within a causal analysis that
require domain expertise, that no algorithm supplies, and that determine whether
the result should be trusted. It includes:

Which variables to include in the model. Which arrows to draw and which to omit
— because every missing arrow is an assumption by omission, not an absence of
data. What to condition on, and what not to condition on. Whether the result,
given all of the above, should be believed.

Causal AI tools are powerful at everything that comes after this layer: fitting
the model, computing estimates, calculating confidence intervals. What they
cannot do is perform the identification layer. The engineer who delegates that
layer to the tool is not using the tool well. She is delegating herself out of
the only work the tool cannot do.

The three fundamental structural positions — confounder, mediator, collider —
illustrate why:

A **confounder** causes both treatment and outcome, opening a backdoor path that
contaminates the causal estimate. Conditioning on it closes the path. Not knowing
it exists means not conditioning on it, and the estimate is biased in ways the
tool cannot detect because the tool does not know the variable was missing.

A **mediator** sits on the causal path between treatment and outcome. Conditioning
on it blocks the very mechanism you were trying to estimate. A model that
controls for a mediator because it "reduces variance" has destroyed the causal
answer it was trying to find. The tool will run the regression either way.

A **collider** is caused by both treatment and outcome. Conditioning on it creates
a spurious association where none existed. The path was closed. Conditioning
opens it. Selection bias — restricting to a non-representative population — is
collider bias by another name, and increasing the sample size within the
restricted population makes the bias worse, not better. The tool does not know
it is sampling from a collider-selected population.

In each case the structural error is invisible in the output. The estimates are
clean. The confidence intervals are narrow. The identification decision was wrong,
and nothing the tool produces signals that.

---

### The Course Architecture

Causal Reasoning is a four-credit graduate seminar at Northeastern University,
College of Engineering, designed for engineers and applied technical
practitioners who use data to make decisions and have never been taught the layer
of reasoning that sits between the data and the claim.

Prerequisites are genuine: graduate-level applied statistics or machine learning,
working knowledge of regression. This is not the entry-point course in the
series. It assumes students can already build predictive models. It teaches them
why predictive models cannot answer the questions that strategy requires, and
what kind of thinking can.

**Act One — Establish (Weeks 1–4)** opens in the middle of a failure. Before any
definitions are introduced, students see a complete causal disaster — a decision
that looked right, made from data that couldn't support it. The vocabulary is
built to name what went wrong. The identification layer is introduced explicitly
in Week 4 as the act's closing move: this is what you must supply, this is what
the machine cannot supply, and this is the distinction the rest of the course
will teach you to perform.

The midterm at the end of Act One tests none of this as recall. Two unseen causal
scenarios. Draw the implied DAG. Diagnose the identification failure. Name the
domain knowledge required to address it. Application only.

**Act Two — Build (Weeks 5–11)** constructs the identification toolkit piece by
piece through domain cases students recognize. Confounders. Mediators. Colliders
— the hardest conceptual week in the course, where the definition is
deliberately withheld until students have felt the problem. The backdoor
criterion — the formal procedure for identifying valid adjustment sets. DAG
defense in two registers: technical for a statistician, plain-language for a
decision-maker.

The collider week is worth pausing on. Session A presents a hiring puzzle that
produces genuine discomfort — an analysis that seems reasonable, keeps returning
wrong results, and has no obvious explanation. Students are not given the
definition of a collider before Session A. They are given the experience of
collider bias and asked to diagnose it without the name. Session B names the
structure. The sequence is deliberate: vocabulary without prior experience
produces classification without intuition. Experience without vocabulary produces
intuition without the tool to use it. The course wants both, in that order.

**Act Three — Apply (Weeks 12–15)** stops giving well-formed single-structure
problems. The identification toolkit is deployed against cases that recombine
earlier concepts — harder in the way that matters. Students translate their
defended DAG into a complete estimation specification, evaluate tool output
against their own identification assumptions, conduct sensitivity analysis using
the E-value, and produce a qualified conclusion in two registers.

The terminal deliverable is a complete causal analysis plan for the student's
own domain problem. Every identification decision made explicitly. Every limit
named honestly. A qualified conclusion that states what the analysis supports
and what it does not — and defends that distinction to a skeptical reader.

---

### The Assessment Architecture

The course's assessment design is the Tier 5 argument made operational.

Every assignment requires an AI Use Disclosure. Not as compliance — as the
course's central analytical act. Students document what they used, how they
used it, what they changed, and at least one identification decision that
required the student's domain knowledge. A disclosure that cannot name one such
decision has not demonstrated that the student performed the irreducibly human
layer.

The grade reflects depth of causal reasoning, quality of domain judgment, and
evidence that the identification decisions were made by the student — not
delegated to a tool.

The weekly DAG assignments are not exercises in graph drawing. Each one requires
stating every arrow as a causal claim, listing missing arrows as assumptions by
omission, and naming unmeasured confounders with their bias directions. The
student is not demonstrating technical facility with a notation. She is
demonstrating that she has made the identification decisions explicitly and can
defend them.

The capstone — a complete causal analysis plan for the student's own domain
problem — is assessed on whether the identification layer is performed, not
whether the estimates are impressive. A student who correctly identifies a DAG
where no valid adjustment set exists, reports that honestly, and states what
follow-on study design would be required to answer the question — has done the
course's work. A student who produces clean estimates from a misspecified DAG has
produced confident noise.

---

### The Tier 5 Argument

The course's positioning within the Irreducibly Human framework is explicit.
Tier 5 is causal and counterfactual reasoning: the capacity to move from
observation to intervention, and from intervention to counterfactual inference.
Current AI is superhuman at Rung 1 (observational pattern matching) and nearly
absent at Rungs 2 and 3.

The identification layer is where Tier 1 ends and Tier 5 begins. The correlation
is in the data. The AI finds it efficiently. The causal claim requires someone
to say: this is the direction of the arrow, this is what I am conditioning on
and why, this is the assumption that makes the estimate interpretable as a causal
effect rather than a statistical association. That someone must be the engineer.
No tool makes that decision on her behalf.

The course's central claim — "Is what your system is measuring actually causing
the outcome, or just correlated with it?" — is not answerable by better modeling.
It requires a different kind of work. The identification layer is not a harder
version of predictive modeling. It is a different cognitive operation, located
at a different tier, requiring domain knowledge that the algorithm does not
possess and cannot acquire from the data alone.

---

### Three Identification Decisions Only the Human Makes

Three specific decisions from the course curriculum illustrate the argument
concretely.

**The mediation decision.** Total effect or direct effect? If an intervention on
treatment affects outcome partly through a mediator — a workplace wellness
program improves productivity partly through reduced absenteeism — the analyst
must decide whether to estimate the total effect (leaving the mediator in the
causal path) or the direct effect (estimating the effect that doesn't run through
the mediator). This is not a statistical question. It is a question about what
the decision-maker needs to know, which requires understanding what decision is
being made. The tool will run either specification. Only the engineer knows which
one answers the question being asked.

**The collider recognition decision.** A sample restricted to ICU patients shows
that less severe presentations of a disease are correlated with worse outcomes.
This seems to contradict the biological mechanism. The analyst who adds more
data from the same ICU population gets a stronger result in the same direction.
The analyst who recognizes that ICU admission is a collider — caused by both
disease severity and other comorbidities — understands that the restriction
created a spurious path. The recognition requires domain knowledge about who
gets admitted to ICUs. No algorithm detects the collider from the data; the
collider's effect is visible in the data only as a pattern, not as a structural
flag.

**The honest no-go decision.** Sometimes no valid adjustment set exists. The
backdoor criterion, applied correctly, returns no set of observed variables that
blocks all backdoor paths. This is not a failure of method. It is an honest
result: the question cannot be answered from this data with this design. A
causal AI tool will still produce estimates. The engineer who understands the
identification layer recognizes that those estimates are not causal claims and
reports accordingly. The engineer who delegates the identification layer to the
tool does not know the estimates should not be trusted.

Each of these decisions is invisible in the tool's output. The honest result and
the confident wrong answer look identical downstream.

---

### What the Course Claims and What It Doesn't

The course claims that the identification layer can be taught as a deliberate
cognitive skill to engineers with applied quantitative backgrounds, and that
a curriculum structured around domain cases, structural intuition before
vocabulary, and two-register defense produces engineers who can perform it.

The course does not claim to produce statisticians or econometricians. The
identification toolkit taught — DAGs, confounders, mediators, colliders, the
backdoor criterion, sensitivity analysis — is a subset of the full causal
inference literature. Students who need instrumental variables, regression
discontinuity, or difference-in-differences will need additional study. The
course provides the conceptual foundation for those methods by teaching the
identification layer those methods are also solving.

The course does not claim that causal AI tools are untrustworthy. It claims that
their trustworthiness depends entirely on whether the identification layer was
performed correctly before the tool was run — and that the identification layer
is irreducibly the human's work.

---

### The Connection to the Broader Argument

The broken dashboard assumption — that the question is answered when the pattern
is found — is the Tier 1 trap stated in the language of data science. Every
organization that has invested in predictive modeling without also investing in
causal reasoning has built a very expensive Tier 1 tool and called it strategy.

AI made this gap more expensive, not less. Faster pattern recognition at greater
scale does not close the distance between correlation and causation. It widens
the reach of the mistake.

The Causal Reasoning course is the intervention at the identification layer — the
place where the data ends and the judgment begins. The engineer who completes it
can do something no dashboard can do: she can say, specifically and defensibly,
what the estimate means as a causal claim, what assumption makes it true, and
what would have to hold in the world for the estimate to support the decision
being made.

That is not a harder version of reading a dashboard. It is a different tier.

---

*Source: Brown, N.B. (2026). "Causal Reasoning: Irreducibly Human — What AI Can
and Can't Do." Course syllabus, Irreducibly Human series, Northeastern University
College of Engineering. Graduate seminar, 4 credit hours.*
