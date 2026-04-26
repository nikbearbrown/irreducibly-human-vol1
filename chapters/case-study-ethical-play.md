# Case Study: Ethical Play
## Teaching Felt Moral Weight as a Design Problem

*Category: Course Design / Tier 3 Social & Personal*
*Theory connection: The audit gap — between what an AI can find in a consequence
structure and what a human player has to feel for moral experience to occur*

---

### The Causal Question

Can moral experience be designed — and if so, what is the design layer that AI
cannot perform?

---

### The Audit Gap

An AI given a game design document can identify which ethical framework is
encoded in the mechanics, trace the consequence structure, and return a
structural audit. It can do this reliably, quickly, and with precision.

What it cannot do is feel implicated.

That gap — between auditable architecture and felt moral weight — is not a
limitation that better models will close. It is the gap that defines what moral
experience is. A game that labels its ethics in text has done the easy work.
A game that makes a player feel the weight of a decision they would rather not
have made — that is where design and philosophy converge.

The distinction has a name in the course: implication versus smugness.
Implication is when the design transfers moral responsibility to the player.
Smugness is when the design tells the player what to think about a moral
situation. Papers Please is implication: when you stamp the visa, the weight
lands on you. A game that pauses the action to remind you that border policies
cause suffering is smugness. The mechanic transfers. The commentary describes.

This distinction is not detectable from the design document alone. A structural
audit can identify the consequence architecture, the ethical framework encoded
in the rule system, the causal chain from decision to outcome. What it cannot
identify is whether the player felt the weight or evaluated it. That requires
a player. It requires a human experience that the architecture either produces
or fails to produce. No algorithm can perform the relevant test.

---

### Why Games

Most courses that teach ethics teach description. Students learn to identify a
trolley problem. They argue about what the right answer is. They have never
driven the trolley.

Games make the gap visible because games are interactive. The player is not
watching someone make a moral choice. The player is making it, with their own
hands, with real consequences within the system, in real time. The gap between
describing moral weight and producing it is much harder to paper over when the
medium requires the player to act.

This is why *Papers Please* does what a novel about border bureaucracy cannot.
The novel can describe complicity. The game makes you complicit. The mechanic
transfers the moral experience. That transfer is what the course teaches
students to design, build, and evaluate — and it is precisely the layer that
AI cannot contribute to, because the test of whether the transfer worked
requires a human on the other end of it.

---

### The Course Architecture

Ethical Play is a four-credit graduate seminar at Northeastern University,
College of Engineering, designed as the synthesis volume of the Irreducibly
Human series. It has a minimal prerequisite — at least one programming course
at any level — because the build environment is Claude Code, which handles
implementation. The student's job is the ethical architecture.

The course runs in three acts.

**Act One — Philosophy as Design Vocabulary (Weeks 1–5)** teaches five ethical
frameworks as design constraints, not intellectual history. Each framework is
introduced through a case in *Voodoo Economics* — a web-based political satire
simulation built specifically for the course as a structural model: an ethical
argument encoded in design decisions, without the framework named anywhere
in the document. Students are not learning to argue about ethics. They are
learning to recognize how ethical positions become mechanics.

The sequence is deliberate. Consequentialism is introduced through the VE
causal chain display — four nodes, every consequence traceable to a decision.
The design question: is each node caused by the one before it, or does it only
follow plausibly? The difference between those two descriptions is the
difference between consequentialist architecture and the appearance of it.
Deontology is introduced through the VE bribe escalation — the moment where
the punishment doesn't track the violation. The definition is withheld until
Session B. Students spend Session A with the case before the structural
explanation arrives. The course wants experience before vocabulary, in the
same sequence as the Causal Reasoning course's collider week.

The five frameworks — consequentialism, deontology, virtue ethics,
contractarianism, care ethics — are taught in this order because the sequence
builds from the most legible mechanic (consequence chains) toward the most
difficult (care ethics, where the morally significant units are relationships
and people rather than resources and rules). The editorializing failure is
introduced last: the exact design decision that tells the player what to feel
rather than producing felt weight. It is introduced last because it is the
mistake most likely to appear in every student's first draft, and naming it
before students have built anything produces self-consciousness without the
experience that makes the distinction meaningful.

Act One closes with the midterm: a preliminary moral architecture specification.
Not a philosophical essay. A specification that names the ethical framework,
the primary mechanic that embodies it, the consequence structure that transfers
responsibility, and one specific design decision predicted to produce implication
in a human player. A specification that cannot name this has not designed an
ethical architecture.

**Act Two — Build (Weeks 6–11)** is where the game gets built. The first session
of Act Two teaches students to use Claude Code to separate content from logic
in the web-based game format. The Game Design Document is locked in Week 6
without the framework named anywhere in the document. The architecture must be
identifiable from the mechanics alone by a reader who was never told which
framework was chosen.

The build sequence surfaces the course's central pedagogical finding: AI tools
generate mechanically correct solutions that are ethically incoherent. A
consequence structure that runs correctly and fails morally. A rule-breaking
mechanic that produces cost calculation instead of felt violation. A dialogue
tree that comments on moral weight instead of producing it. Each instance is
documented. The student names the incoherence and the design decision required
to correct it. That documentation is the primary evidence that the student
performed the design layer the tool cannot perform.

The informal playtest in Week 9 surfaces the first real data: does the game
produce implication or something else? The VE player experience goals (eight
specific felt experiences the game was designed to produce) are the diagnostic
frame. Which goals did playtesters report, and which did they not? Three
revision changes are permitted in response. Prioritization is the graded skill.

Act Two closes with the Beta Build Checkpoint and a prediction: where will the
AI Ethical Auditor correctly identify the embedded framework, and where will
it fail?

**Act Three — Audit and Analysis (Weeks 12–15)** closes the loop. The VE GDD
is submitted to the Ethical Auditor as a shared class exercise first — live,
visible to everyone. The AI's structural competence is demonstrated at scale.
Its limits become visible in the same session: what it cannot find because
finding it requires a player.

Week 13 returns the Week 1 felt response journals — the paragraph students
wrote before they had any framework vocabulary, recording what they felt. The
gap analysis is constructed from that pre-vocabulary response through to the
AI audit findings, tracing specific design decisions to specific divergences
between structural analysis and human playtester experience, and naming the
human variable the audit could not reach.

The terminal deliverable is one sentence: the general design principle that
names the gap between AI-auditable architecture and human-felt moral weight
with enough precision to be useful to a designer who was not in this course.
Students write it before the final session. The final session is the attempt
to make the sentence precise enough to be useful.

---

### The Assessment Architecture

Every assignment requires an AI Use Disclosure. Not as compliance — as the
course's primary assessment instrument. Students document at least one design
decision that required their values, aesthetic judgment, or accountability for
a player's felt experience. A disclosure that cannot name one such decision has
not demonstrated that the student performed the irreducibly human design layer.

The grade reflects depth of ethical design reasoning, quality of gap analysis,
and evidence that the design decisions were made by the student. The terminal
deliverable — the one sentence — carries weight because it is the most
compressed version of the argument. A student who cannot produce a defensible
sentence has not yet understood what the course was building toward.

The Week 1 felt response journal has no formal grade. It is returned in Week 13
as evidence. What the student felt before they had vocabulary is the record of
moral experience that the frameworks are meant to explain — and sometimes fail
to explain. That gap between what was felt and what can be named is the data
the course is organized around.

---

### The Tier 3 Argument

The course's positioning within the Irreducibly Human framework is Tier 3:
Social & Personal. The tier description notes that AI simulates emotional and
moral outputs without feeling them, and that the danger is not that the
output is wrong. The danger is that the capacity atrophies in the person who
stops exercising it.

Ethical Play is the direct intervention at that atrophy. Not ethics as
intellectual analysis — ethics as felt experience, designed, tested, and
evaluated against whether a human player actually felt it. The course does not
teach students to identify ethical frameworks. It teaches them to produce moral
experiences in other people, to test whether the production worked, and to
name the gap between the structural audit and the human report.

That gap is where Tier 3 lives. The AI can audit the architecture. It cannot
sit in the playtest and notice when a player's expression changed. It cannot
distinguish the student who felt implicated from the student who evaluated
the implication at a remove. It cannot write the sentence that names the gap
with precision. Those are the capacities the course develops.

The implication/smugness distinction is the Tier 3 argument made concrete.
Smugness is Tier 1: pattern recognition, identification of ethical content,
structural analysis. Implication requires Tier 3: the capacity to produce
moral experience in another person, which requires understanding what moral
experience is, which requires having had moral experience oneself.

The AI Ethical Auditor finds smugness easily. It cannot detect whether
implication occurred. That asymmetry is the course's central finding.

---

### Three Design Decisions Only the Human Makes

Three specific decisions from the course curriculum illustrate where the
human's contribution is irreducible.

**The editorializing decision.** At some point in building every student's game,
the design introduces a moment that tells the player what to feel — a
narrative comment, a tonal cue, a consequence label that names the moral
weight rather than producing it. The AI does not flag this as a failure.
The mechanic runs correctly. The consequence fires. But the moment produces
evaluation rather than felt weight. Identifying this as editorializing, and
designing the alternative that produces implication instead, requires the
designer to have experienced the difference. The tool cannot make the call.
The tool is part of the problem.

**The worst-outcome player decision.** Contractarianism as a design constraint
asks the designer to build for the player who receives the worst outcome.
In practice this requires the designer to identify who that player is, what
their experience of the game will be, and whether the mechanic treats their
experience as morally significant. This is not a structural question. It is
a question about whose perspective the designer is capable of inhabiting.
The AI can identify whether a consequence structure has a worst outcome. It
cannot evaluate whether the designer considered that outcome or what moral
weight the designer assigned to it.

**The sentence.** The terminal deliverable. One sentence that names the gap
between AI-auditable architecture and human-felt moral weight with enough
precision to be useful to a designer who was not in this course. The AI can
produce candidate sentences from the course materials. None of them have been
tested against the experience of designing, building, playtesting, auditing,
and analyzing the gap firsthand. The sentence that comes from that experience
is different from the sentence that comes from pattern-completing the course
syllabus. The course bets its terminal deliverable on that difference.

---

### What the Course Claims and What It Doesn't

The course claims that felt moral weight can be designed as a deliberate
cognitive and technical skill, that the gap between auditable architecture
and felt experience is the course's subject matter, and that the design layer
required to close that gap is irreducibly human in the sense the taxonomy
specifies.

The course does not claim that AI tools are useless in ethical design. Claude
Code builds the games. The Ethical Auditor provides structural analysis that
would take a human reviewer hours. The tools are genuinely useful at the layers
they can perform. The course's argument is not against the tools. It is a
precise account of where the tools end and the designer's judgment begins.

The course does not claim that five ethical frameworks exhaust the space of
moral architecture. The Disco Elysium week explicitly raises the question of
whether any of the five frameworks captures what that game is doing — and
"requires a new category" is an acceptable answer if the student can specify
what the new category is. The frameworks are tools for making design decisions
visible. They are not the only tools.

The course does not claim that implication always produces morally better
outcomes than smugness. A game can produce genuine felt weight and use it
toward morally problematic ends. The capacity to produce moral experience in
another person is not itself a moral good. The course teaches the capacity.
The ethics of its use is the student's accountability.

---

### The Connection to the Broader Argument

The factory model curriculum taught students to identify and describe moral
positions. It did not teach them to inhabit moral positions, to produce moral
experiences in others, or to evaluate whether a designed system transferred
moral responsibility or merely commented on it. The difference between
identifying a trolley problem and driving the trolley is exactly the
difference between Tier 1 pattern recognition and Tier 3 social and personal
intelligence.

AI made this gap more expensive. A system that can identify ethical frameworks
in any text, trace consequence structures with precision, and produce fluent
commentary on moral weight can do the Tier 1 work of ethics at superhuman
speed. It cannot feel implicated. Every professional, educator, and engineer
who builds systems that encode values is in the gap between structural audit
and felt moral experience — and most of them were never taught that the gap
exists, let alone how to work in it.

Ethical Play is the intervention at that gap. The microscope that sits in a
box, in this domain, is the engineer who can audit consequence structures
and cannot feel their weight.

---

*Source: Brown, N.B. (2026). "Ethical Play: Irreducibly Human — What AI Can
and Can't Do." Course syllabus, Irreducibly Human series, Northeastern
University College of Engineering. Graduate seminar, 4 credit hours.*
