# Chapter 9: Simulation and Planning
## The Rat That Regretted

---

### Learning Objectives

By the end of this chapter, you should be able to:

1. **Distinguish** model-free from model-based reinforcement learning and explain what each can and cannot do that the other cannot
2. **Describe** hippocampal forward and reverse replay and connect each to a specific computational function in the planning-and-learning cycle
3. **Explain** why the Steiner-Redish result qualifies as evidence for counterfactual reasoning rather than merely for prediction-error processing, and identify the neural dissociation that supports this claim
4. **Apply** Pearl's three-rung ladder of causation to categorize the cognitive operations in a given planning task
5. **Evaluate** the corvid planning evidence and use it to argue that mental simulation is a functional capacity rather than a substrate-specific one

**Prerequisites:** Chapter 7's treatment of hippocampal place cells and the cognitive map; Chapter 8's account of model-free reinforcement learning, temporal-difference learning, and the dopamine prediction-error signal. The present chapter builds directly on both.

**Where this fits:** Chapter 8 showed how the brain learns from experience by caching the values of past actions and updating those values when outcomes surprise it. This chapter asks what happens when the brain needs to act in situations it has not yet encountered — and discovers that the mammalian answer is to simulate the situation before acting in it.

---

### Chapter Opening: The Choice Not Taken

It is evening in Minneapolis. In a laboratory on the University of Minnesota campus, a rat is running.

The track is circular, perhaps a meter across, with four distinct stations placed at intervals around the rim. Each station has its own smell, its own flavor, its own chime. The chime tells the rat, the moment it arrives, how long it will have to wait if it wants what is being offered. One second sometimes. Forty-five seconds other times. The rat has an hour. It is always deciding.

The rat has preferences. Chocolate is preferred. Cherry is acceptable. The others less so. Over weeks of running the track, each rat has developed a threshold for each flavor: the longest wait worth enduring for that particular payoff. Below the threshold, stay. Above it, move on.

Now watch what happens when the rat makes a mistake.

It arrives at a chocolate station. The chime plays. The wait — twelve seconds, say — is within this rat's threshold for chocolate. The rat should stay. For reasons that the experiment does not and cannot control, it doesn't. It moves on. Thirty seconds later it arrives at the cherry station. The chime plays. The wait is twenty seconds — longer than this rat's threshold for cherry. It has skipped a good deal and walked into a bad one.

The rat pauses. It turns its head back in the direction it came from.

Not always. Not in every trial. Specifically and reliably in this kind of trial — the one where it had a good option in its threshold and passed it up, and then walked into something worse. Not in the trials where both stations were mediocre. Not in the trials where skipping was the right call and the next station confirmed it. In the regret-eligible trials, with the regret-eligible rats — the ones with high enough standards that the math of the mistake actually stings — the head turns back.

While the head turns, specific neurons in the rat's orbitofrontal cortex are firing. Not the neurons that encode the disappointing cherry now in front of it. The neurons that, in earlier sessions, fired when the rat was at the chocolate station it just left.

The rat is replaying the road not taken. In a brain the size of a walnut, in a creature we have been conditioned to think of as a reflex machine, something is happening that Judea Pearl reserved for the top rung of his ladder of causation: *if I had done otherwise, it would have gone like this.*

The chapter is what is happening under that head-turn.

---

## 9.1 Two Ways to Learn, One Way to Plan

Chapter 8 introduced the distinction between model-free and model-based reinforcement learning as a difference in *what gets stored* and *how new situations get evaluated*. The distinction matters enough here to make it precise before building on it.

**Model-free learning** stores the *cached value* of an action in a state: *in situation S, action A has been worth roughly V*. When the animal finds itself in S again, it consults the cache and picks the highest-valued action. Updating the cache requires physically experiencing outcomes — the dopamine prediction-error signal fires, the weights change, the cache updates. This is fast to execute once learned, and relatively cheap computationally. Its limitation: the cache can only be updated by direct experience. The model-free agent cannot learn anything about a situation it has not been in. It cannot evaluate a novel option. It cannot recover gracefully from a change in the world that makes old values wrong.

**Model-based learning** stores a *model of the world's dynamics*: how states transition into other states under various actions, and what outcomes each transition produces. When the animal faces a choice, it does not consult a cached value; it *simulates* the likely chain of consequences under each candidate action and estimates the value from the simulation. This requires no additional physical experience with the options being evaluated. The agent can plan in entirely novel situations, combine known transitions in new ways, and update its behavior the moment the world-model updates — without needing to fail several more times to re-learn a cache.

The cost is real. Running simulations is metabolically expensive and time-consuming. For well-practiced, stable situations, the cached model-free value will be more accurate than any simulation, because it reflects actual outcomes rather than predicted ones. For novel situations, or situations where the world has recently changed, the model-based approach pays off.

Most animals use both. Habit systems (model-free) run on well-worn tracks. Planning systems (model-based) engage when the habit fails, or when novelty makes the cache obsolete. The balance between them is itself regulated — the brain allocates cognitive control resources between the two depending on uncertainty and stakes. We will see the neural architecture of this regulation when we reach the prefrontal cortex in later chapters.

What the rat at Restaurant Row is doing when it regrets is pure model-based: it is evaluating a trajectory it did not take, comparing the simulated outcome of that trajectory to the actual outcome of the one it did take, and using the comparison to update its future policy. None of this requires re-experiencing the chocolate station. It requires *simulating* what the chocolate station would have given.

This is Pearl's Rung 3. Rung 1 is *what is* — the correlational knowledge a bacterium uses when it swims up a sucrose gradient. Rung 2 is *what if I do* — the interventional knowledge a rat uses when it learns that pressing a lever produces food. Rung 3 is *what if I had done otherwise* — the counterfactual knowledge the rat at Restaurant Row uses when it runs the unchosen option in its head and measures the difference. The distinctions are not merely philosophical. Each rung requires a different neural architecture to implement.

---

## 9.2 What the Hippocampus Does Between Movements

The mechanistic case for biological simulation runs through the hippocampus, and the story begins with a behavioral observation that was decades ahead of its neural explanation.

Edward Tolman, running rats through mazes at Berkeley in the 1930s and 1940s, noticed that rats at decision junctions would sometimes *pause and look back and forth* between the available paths before choosing. He called this *vicarious trial and error*, or VTE, and argued in his 1948 *Psychological Review* paper "Cognitive Maps in Rats and Men" that the rat was, in some functional sense, rehearsing the alternatives in its head before committing. The claim was contested for decades — VTE could be attributed to indecision, noise, motor variability, or a dozen other things that do not require positing internal simulation. The neurophysiology eventually settled it.

Brad Pfeiffer and David Foster, recording from hippocampal place cells in 2013 in *Nature*, made the decisive observation. Recall from Chapter 7 that place cells are neurons each of which fires when the rat is in a specific location in its environment. The full population of active place cells at any moment gives a neural representation of where the rat currently is. What Pfeiffer and Foster found was that just before the rat began moving toward a remembered goal location, a brief fast sequence of place-cell firing swept across the hippocampal map — starting at the rat's current position and sweeping to the remembered goal, tracing the path the rat was about to take. The entire sequence completed in roughly a hundred milliseconds. The rat then walked the path the sweep had predicted. Sometimes the sweep predicted the path better than the rat's previous behavior would have suggested.

The hippocampus was generating the trajectory before the body executed it.

This is **forward replay**. The same neural substrate that, during active navigation, tracks the rat's current position is, during the pause before movement, running a fast compressed simulation of the upcoming path. The simulation is prospective: it previews a route, presumably allowing some evaluative process to assess whether the route is worth taking before the rat commits its body to it.

Foster and Matthew Wilson had reported the complementary phenomenon seven years earlier, also in *Nature*. After a rat ran a trajectory and received a reward, the hippocampal place cells fired in *reverse* — starting at the reward location and sweeping backward through each position the rat had just occupied. This **reverse replay** happened during the same class of neural events as forward replay: *sharp-wave ripples*, brief high-frequency bursts of synchronous activity in hippocampal regions CA3 and CA1. But the direction was opposite, and the timing was post-reward rather than pre-movement.

The two kinds of replay map onto two distinct computational functions.

Forward replay is for **prospective planning**: running a trajectory in advance of committing to it, so that its expected outcome can be evaluated before the body moves. The brain is asking, in effect, *if I go this way, where do I end up?*

Reverse replay is for **credit assignment**: after a rewarding outcome, propagating information about that reward backward through the chain of states that produced it. In the temporal-difference framework from Chapter 8, this is how the prediction-error signal $\delta_t$ travels back from the reward to update the value estimates $V(s_t)$ for each state in the sequence. Without reverse replay, the credit for arriving at a reward can only propagate backward one step at a time, one trial at a time. Reverse replay can do the whole trajectory in a hundred milliseconds.

Both kinds of replay are *prioritized*. The hippocampus does not replay every experience equally. It preferentially replays high-reward trajectories, novel environments, and paths through recently-changed regions of the learned map. The prioritization means the simulator is already making value judgments about what is worth rehearsing — another layer of the model-based optimization that the model-free cache does not have.

Replay also occurs during sleep, particularly during the slow-wave phases when sharp-wave ripples are most frequent. Whole behavioral sessions are compressed and replayed at accelerated rates during sleep, appearing to consolidate information from the hippocampus to the neocortex. The simulator does not shut down when the rat stops running. It processes the day's experience into a more durable form while the body is still.

[FIGURE: Schematic of forward and reverse replay. Left panel: during active navigation, place cells fire in sequence as the rat moves through positions A → B → C → D (goal). Middle panel: forward replay — before moving, a fast sweep of place-cell activity runs A → B → C → D in ~100ms. Right panel: reverse replay — after reward at D, a fast sweep runs D → C → B → A. Timeline at bottom shows the relationship between navigation events, forward replay (pre-movement), and reverse replay (post-reward). Students should notice: (1) both replays use the same place cells that encode actual position during navigation; (2) forward and reverse have opposite temporal orders despite using the same substrate; (3) both happen during sharp-wave ripple events, on timescales ~20-30x faster than actual movement.]

---

## Concept Worked Example: What the Simulator Actually Computes

The replay mechanism is elegant. To see why it produces something that deserves to be called simulation, it helps to trace the computation explicitly.

**Setup:** A rat has learned a maze with two routes from Start to Goal. Route A is longer but reliably delivers a high-value reward. Route B is shorter but delivers a lower-value reward, and was recently blocked for two sessions (though it is now open again).

**What a model-free agent does:** The cached value of Route A is high (accumulated over many successful trials). The cached value of Route B is lower (the blocking sessions generated prediction errors that downgraded its value, and the downgrade has not yet recovered). The model-free agent takes Route A. It does not know Route B is open again without physically trying it.

**What a model-based agent does:** Before moving, it generates a forward replay of both available routes. The Route B replay terminates at the Goal with a high-value reward (because the model includes the recent re-opening). The agent evaluates both simulated outcomes and identifies that Route B now has a higher expected value per unit time, given its shorter length. It takes Route B — without ever having physically run Route B since the re-opening.

**What the data show about the rat:** In exactly this kind of situation — environments where the structure of the maze changes and the animal has had an opportunity to observe the change but not physically re-run the updated routes — rats update their behavior faster than the model-free cache alone can explain. The behavioral flexibility is one of the original arguments for model-based processing in rodents.

**The key distinction:** Model-free value updates require the animal to run the route and receive the outcome. Model-based value updates require only that the animal's world-model be updated (it observed the route opening) and that it run the simulation. The simulator is applying the updated model to trajectories the animal has not recently walked.

This is what makes simulation valuable beyond what Chapter 8's reinforcement learning can do on its own. The dopamine system updates caches from experience. The hippocampal-cortical simulator can update expectations from *modeled* experience — from imagining what experience would deliver — without needing the body to be the experimental apparatus.

---

## 9.3 Disappointment and Regret Are Different Things

The Steiner-Redish result from 2014 is the cleanest behavioral and neural evidence for counterfactual reasoning in a non-primate mammal. But its interpretation requires care, because there is a subtler and a less subtle version of what might be happening.

The less subtle version: the rat arrives at a bad outcome, fires a prediction-error signal, and updates its values. Its head-turn is a motor artifact of the prediction error, or a scanning behavior triggered by any strongly negative outcome. This is *disappointment* in the functional sense — a generic worse-than-expected signal — and it does not require counterfactual computation.

The subtler version: the rat arrives at a bad outcome and specifically activates the neural representation of the *unchosen better option*, compares that representation to the actual outcome, and uses the comparison to update its future policy. This is *regret* in the functional sense — a specific better-option-was-available signal — and it requires the rat to have simulated the road not taken.

Steiner and Redish distinguished these two using neural recordings.

The non-regret interpretation predicts that OFC activity should correlate with the magnitude of the prediction error at the current station — bigger error, more OFC activation, directed at the current disappointing cherry. The OFC neurons should encode the cherry.

The regret interpretation predicts something different: that OFC activity should encode the *missed option* — the chocolate station the rat just left — and that this encoding should occur specifically in regret-eligible trials, not in trials where both options were similarly mediocre (where no counterfactual advantage was available).

What the data showed: during the head-turn, the OFC neurons that fired were the ones that had fired, in earlier sessions, while the rat was at the chocolate station. Not the cherry neurons. Not a generic prediction-error signal. The chocolate representation, reactivated in the aftermath of skipping it. And only in the regret-eligible trials.

The downstream behavioral signature confirmed the computation was doing real work. Rats that had just produced the OFC regret signature waited longer at *subsequent* stations than they would have otherwise. The missed-option comparison had updated their threshold behavior — made them more willing to accept deals they would previously have passed. The simulation changed the policy. A simulation that does not change behavior is philosophically interesting but cognitively inert. This one changed behavior.

The dissociation matters for the book's running argument. Prediction-error processing is a Rung 2 capacity — the brain is responding to the difference between what it predicted and what it got, and updating accordingly. Counterfactual processing is a Rung 3 capacity — the brain is constructing a *never-happened* trajectory and using it to inform future choices. The Steiner-Redish data place the rat at Rung 3. A creature with a walnut-sized brain, running a track for food pellets, is operating on the rung that Pearl associated with causal reasoning proper.

---

## 9.4 The Corvid That Planned for Tomorrow's Hunger

The mammalian story is half the chapter. The other half is a bird.

For most of the twentieth century, comparative cognition operated under the Bischof-Köhler hypothesis: that non-human animals cannot plan for motivational states they are not currently in. A satiated animal, on this view, could not cache food against tomorrow's hunger — it would have to actually be hungry before hunger-related behavior could engage. The hypothesis was not arbitrary; it was grounded in a reasonable reading of the learning literature, which had found that animals generally learn best when the training state matches the test state.

Nicola Clayton and Anthony Dickinson broke it in 1998 in *Nature*, with western scrub jays.

Scrub jays (*Aphelocoma californica*) are food-caching corvids — they store seeds and insect prey in hundreds of small caches distributed across their territory and return to them across days and weeks. Clayton and Dickinson used the dual-food paradigm: jays were given access to two kinds of cacheable food, wax-moth larvae (which the jays strongly prefer when fresh, but find inedible once degraded) and peanuts (which remain palatable indefinitely). Jays cached both types of food in different locations, then were given access to the caches after either a short delay (within the larvae's freshness window) or a long delay (after the larvae had degraded). After the short delay, jays preferentially recovered larvae. After the long delay — after learning that larvae go bad — jays *avoided* the larvae caches and went to the peanuts.

The jays knew not just *what* was cached and *where* it was. They knew *when* it had been cached, and what that timing implied about its current state. The what-where-when combination is what the episodic memory literature defines as episodic-like memory — the encoding of a specific past event as a coherent autobiographical record rather than a decontextualized fact.

Subsequent work from the Clayton laboratory tightened the case substantially. Jays cache more food in environments where they have experienced food unavailability the next morning — *even when tested while currently sated*. They are not caching because they are hungry now. They are caching because they have a model of how tomorrow's conditions will differ from today's, and they are acting on that model now. This is prospective planning across a motivational state boundary: planning for hunger from a state of satiety. The Bischof-Köhler hypothesis predicted this would not occur. It occurs.

A further result is the one I find most impressive. Jays that were observed by a competitor while caching a food item returned to that cache site in private later and moved the food to a new location — but *only* if the observer had been a competitor capable of stealing. They did not move caches observed by non-stealing individuals. And critically, jays that *had themselves been thieves* were more likely to engage in this protective re-caching than jays with no theft experience. The jays were modeling the knowledge state of potential competitors, projecting their own past behavior onto others, and taking preemptive action based on that projection. Theory of mind, or something functionally close to it, in a bird.

For the chapter's argument, the crucial observation is this: the corvid brain produces these planning capacities without a six-layered neocortex. Corvids have a pallium organized in discrete nuclei rather than laminar sheets — a structural arrangement that diverged from the mammalian plan more than three hundred million years ago. The nidopallium caudolaterale in corvids appears to be functionally analogous to mammalian prefrontal cortex in several respects, including its role in working memory and flexible decision-making, but it is built from a different anatomical blueprint.

The simulation capacity evolved at least twice. Two lineages, separated by three hundred million years of evolutionary history, arrived at the same computational solution to the same problem: how to act now on the basis of what will be true later. The substrate is radically different. The function is the same.

This is the book's comparative method at work. When a capacity appears in two distant lineages that share a common ancestor far too primitive to have had it, the most parsimonious explanation is convergent evolution: independent solutions to a shared problem. The problem here is clear — acting adaptively in environments where the relevant conditions at action-time differ from the relevant conditions at planning-time requires mental time travel, prospective simulation, or something functionally equivalent. Mammalian neocortex solved it one way. Corvid nidopallium solved it another. The solution space for Pearl's Rung 3 is larger than one anatomy.

---

## 9.5 The Architecture of the Simulator

Connecting the hippocampal replay mechanism to the corvid behavioral evidence requires a brief look at how the simulator is organized as a system rather than as individual components.

The hippocampus does not work alone. The forward and reverse replays described in §9.2 are generated in hippocampal CA3 (which has the recurrent auto-associative connectivity introduced in Chapter 6 for pattern completion) and propagated through CA1 to the neocortex. The neocortex receives these hippocampal sequences and, according to the predictive coding framework, continuously generates top-down predictions about what sensory input is expected. When the prediction matches the bottom-up signal, nothing much happens. When they diverge, a prediction-error signal propagates up the cortical hierarchy, updating the generative model.

The prefrontal cortex sits at the top of this hierarchy in mammals — the region that Chapter 11 will examine as the seat of executive control, working memory, and, in primates, the most flexible planning. Its role in the present chapter is as the *gating controller*: the prefrontal cortex determines when model-based simulation should override cached model-free habit. In low-stakes, familiar situations, habit is faster and accurate enough. In high-stakes or novel situations — situations where being wrong costs more than the efficiency savings of the habit system — the prefrontal cortex shifts the balance toward simulation. Patients with prefrontal damage are often described as pathologically habitual: they continue doing what worked before even when the world has clearly changed, because the mechanism that would disengage habit and re-engage the simulator is not functioning.

The orbitofrontal cortex, specifically, is where the *value of the simulated trajectory* is read out. Chapter 8 described the OFC as encoding expected value in a way that can be updated by changes in the world-model rather than requiring direct re-experience. The Steiner-Redish result adds a sharper characterization: the OFC encodes the value of *specific past and future trajectories*, including counterfactual ones, not just the value of the current option. It is the readout layer for the simulator, not just a passive register of cached values.

In corvids, the nidopallium caudolaterale appears to be doing something functionally similar to the mammalian OFC and lateral prefrontal cortex combined — holding items in working memory, updating representations based on incoming information, and supporting flexible choice between multiple candidate actions. The anatomical substrate is different but the functional role is recognizable. Convergent architecture in the service of convergent computation.

---

## 9.6 What Simulation Buys

I want to be explicit about what the simulation capacity adds to the cognitive repertoire of the animals that have it, because the addition is substantial and worth naming precisely.

An animal without simulation can only update its policy by physically experiencing outcomes. If the world changes, the animal must encounter the changed world repeatedly before its behavior adapts. Recovery from errors is slow. Novel situations are managed by habit, or by exploration that may be costly. The environment is always one step ahead of the cache.

An animal with simulation can update its policy by running the world forward in its head. When the environment changes, the animal can reason about the change, simulate the likely outcomes of various responses, and adjust its behavior before experiencing the new outcomes physically. Recovery from errors is faster — the Steiner-Redish rats corrected their threshold behavior after a single regret episode, not after many repeated failures. Novel situations can be evaluated prospectively.

By the Legg-Hutter operational definition the book runs on — the ability to achieve goals across a wide range of environments — the addition of simulation substantially expands the range. An agent limited to model-free learning can achieve goals in environments similar to those it has experienced. An agent with model-based simulation can achieve goals in environments that differ from past experience, as long as the simulator's world-model is accurate enough to produce useful predictions. The range is bounded by the quality of the model, not by the breadth of past experience.

There is a cost. Model-based simulation is metabolically expensive and cognitively demanding. Its advantages are greatest when stakes are high and situations are novel; its costs are highest in exactly those situations. The dual-system architecture — habit for the familiar and cheap, simulation for the novel and costly — is not a design flaw. It is the solution to a real optimization problem.

And there is a limit. The simulator can only produce useful predictions when the world-model it runs on is accurate. If the model is wrong — if the rat's representation of the maze does not include the recently-opened path, or if the scrub jay's representation of the cache site does not include the recent disturbance — the simulation will produce confidently wrong predictions. The accuracy of the model is the bottleneck. We will return to this limit in the final chapters, when we ask where AI simulators diverge from biological ones: both run the world forward in representation; only one of them has the embodied, consequence-bearing relationship with the actual world that keeps the model calibrated.

---

## Chapter Summary

**What you can do now that you could not before this chapter:**

The central skill this chapter adds is the ability to identify, in a behavioral result, whether the evidence supports model-free learning, model-based planning, or specifically counterfactual reasoning — and to connect each to the neural architecture that implements it.

Model-free: cached values, dopamine prediction error, fast but inflexible. The signature is that policy updates require repeated physical experience. Model-based: world-model plus prospective simulation, slower and more expensive but flexible. The signature is policy updates from observation or reasoning without repeated physical experience. Counterfactual: simulation of unchosen options and comparison to actual outcomes. The signature is neural encoding of missed alternatives during outcome evaluation, with downstream behavioral policy correction.

**The one idea that matters most:** The hippocampus is a trajectory simulator, not merely a memory store. It runs paths forward and backward through its place-cell map, on timescales far faster than physical movement, in the service of prospective planning and retrospective credit assignment. The same cellular machinery that encodes where the rat is during navigation encodes where the rat could have gone — or should have gone — during the pauses between movements. This is the neural substrate of Pearl's third rung.

**The common mistake to watch for:** Conflating disappointment with regret. Disappointment is a worse-than-expected outcome signal, present in any system with a prediction-error mechanism, including insects and fish. Regret is the specific activation of a better-alternative-was-available signal, requiring the simulation of the unchosen trajectory. The distinction matters for determining which rung of the causal ladder a species is actually on. The Steiner-Redish dissociation — OFC encoding the chocolate restaurant, not the disappointing cherry — is the specific piece of evidence that elevates the rat's behavior from Rung 2 to Rung 3.

**The Feynman test:** Without using the terms "model-free" or "model-based," explain to a friend why a rat that has just been offered a bad deal at a restaurant turns its head back toward the previous restaurant. Now explain why that head-turn must involve something more than a prediction-error signal. If you can give both explanations clearly, you understand the chapter's central argument.

---

## Exercises

**Warm-up: Direct Application**

1. A rat is trained on a simple T-maze with a food reward at the end of the left arm. When the reward is removed from the left arm and placed at the end of the right arm, a model-free agent would continue to go left for several trials before extinguishing that behavior and learning to go right. A model-based agent would switch faster. What behavioral signature in the transition period would distinguish these two learning strategies, and what would the neural evidence for each look like using what you know from this chapter?

2. The chapter describes forward replay as prospective (previewing future paths) and reverse replay as retrospective (anchoring credit for recent outcomes). What would you expect to happen to each type of replay if you blocked the rat's access to reward entirely — running the maze without any food at the end? Which type would be most affected, and why?

3. The Bischof-Köhler hypothesis states that animals cannot plan for motivational states different from their current state. The Clayton-Dickinson scrub jay result violated this hypothesis. Describe precisely what the jays would need to have in their cognitive repertoire for the experimental results to be explained *without* invoking prospective planning. Is that explanation parsimonious? Why or why not?

**Application: Translation**

4. A hedge fund uses an algorithmic trading system that caches the values of trade actions based on historical outcomes and executes whichever action has the highest historical return in the current market state. A competing fund uses a system that maintains a model of market dynamics and simulates the outcomes of candidate trades before executing them. Using the model-free/model-based distinction from this chapter, predict how each system would perform during a market regime change — a period when historical patterns no longer hold. What is the analog of "replay" in the model-based trading system?

5. A clinical neuropsychologist reports that a patient with bilateral hippocampal damage (similar to the famous patient H.M.) is unable to form new episodic memories but retains normal performance on well-practiced habit tasks. Using the chapter's framework, predict how this patient would perform on: (a) a task requiring learning a new motor skill through repetition; (b) a task requiring planning an unfamiliar route through a new city; (c) a task requiring the rat-style regret computation described by Steiner and Redish. Justify each prediction.

6. The Extension Note describes NASA's use of simulators during the Apollo 13 mission. Identify the specific computational parallel between NASA's ground team running simulations on spacecraft models and a rat running forward replay before choosing a path in a maze. What is the analog of the hippocampal sharp-wave ripple in NASA's operation? What is the analog of the orbitofrontal readout? What does the human simulation have that the rat simulation does not?

**Synthesis: Combining Concepts**

7. Chapter 6 described the hippocampus as an auto-associative memory that completes partial patterns using recurrent connections. Chapter 9 describes the hippocampus as a trajectory simulator that runs forward and reverse replay. Are these the same function or different functions using the same substrate? Argue that they are *the same function* applied to different kinds of patterns — and then argue that they are *different functions* that happen to share the same cellular machinery. Which interpretation is more parsimonious, and what experiment would distinguish them?

8. Chapter 8 described the dopamine prediction-error signal as a Rung 2 mechanism — it updates the agent's policy based on the difference between expected and actual outcomes in physical experience. Chapter 9 describes hippocampal replay as a Rung 3 mechanism — it enables the agent to update its policy based on simulated counterfactual trajectories. In principle, could replay provide input that generates dopamine prediction errors based on *simulated* rather than *actual* outcomes? What evidence exists for or against this? What would this imply about the relationship between the model-free and model-based systems?

9. The chapter claims that mental simulation evolved independently in mammals and corvids because both faced the same selection pressure: environments where the relevant conditions at action-time differ from conditions at planning-time. Identify two other species or lineages, from any chapter in this book, where you would predict some form of prospective simulation to have evolved, based on their ecology. For each, describe what behavioral experiment you would design to test for model-based planning.

**Challenge: Pushing Forward**

10. *(Open-ended)* The "still puzzling" note at the end of the author's draft highlights that hippocampal replay events compress whole spatial trajectories into roughly one hundred milliseconds — a compression of approximately twenty- to thirty-fold relative to actual movement speed. This compression ratio is set by sharp-wave-ripple dynamics, not by the spatial scale of the environment. Develop a hypothesis for why this particular timescale and compression ratio may be computationally optimal for the planning function replay is proposed to serve. Your hypothesis should make at least one testable prediction about what would happen to planning behavior if the compression ratio were experimentally altered (faster or slower replay). Consider: what constraints does the downstream readout system (orbitofrontal cortex, prefrontal cortex) impose on the timescale over which simulated trajectories must be presented to be useful?

---

## Connections Forward

Chapter 9 established that the mammalian brain simulates trajectories before and after acting on them, enabling model-based planning and counterfactual learning. The next chapters ask what happens when the thing being simulated is not a spatial path but a *social future*.

**Chapter 10** (*Social and Emotional Intelligence*) examines what the social simulator adds — the capacity to model not only one's own future trajectories but the intentions, beliefs, and likely behaviors of other agents. The prefrontal cortex, which appeared here as the gating controller between habit and simulation, will reappear there as the substrate for social modeling and the regulation of social behavior.

**Chapter 11** (*Theory of Mind*) takes up the question of false-belief attribution — the capacity to model what another agent *incorrectly* believes, and act on that model rather than on one's own correct knowledge. This is the social extension of counterfactual reasoning: not *what would have happened if I had done otherwise* but *what would happen if another agent acts on what they believe, not on what is true*. The structure is the same. The content is another mind.

The question this chapter leaves open: the rat's simulator runs on a world-model that was acquired through physical experience with the actual world. The rat's simulations are constrained to be roughly consistent with the physics it has inhabited. AI simulators — including the large models now used for scientific and engineering prediction — run on world-models trained on text and data. The question of how accurate a simulation can be, and what determines the boundary of that accuracy, is the open question that Chapter 17 will approach from the AI direction. The rat's puzzled head-turn and the engineer's digital-twin software are running the same algorithm. They are not running with the same fidelity.

---

*The rat at Restaurant Row did not think, in any language, that it had made a mistake. But something in its small brain lit up with the pattern of what it had passed up, and the next time the chime rang, it waited a little longer. That is what it looks like when the machine that imagines is the same machine that learns.*

---

**Chapter Notes and Primary Sources**

The Restaurant Row regret experiment was published by Adam Steiner and David Redish in *Nature Neuroscience* in 2014. The original vicarious trial and error observations were published by Edward Tolman in "Cognitive Maps in Rats and Men" in *Psychological Review* in 1948.

Forward hippocampal replay during goal-directed behavior was documented by Brad Pfeiffer and David Foster in *Nature* in 2013. Reverse replay following reward was documented by David Foster and Matthew Wilson in *Nature* in 2006. The prioritized replay result — that high-utility experiences are preferentially replayed — is reviewed in Mattar and Daw's 2018 *Nature Neuroscience* paper "Prioritized memory access explains planning and hippocampal replay."

The scrub jay episodic-like memory result was published by Nicola Clayton and Anthony Dickinson in *Nature* in 1998. The prospective food-caching result, showing planning for future hunger from a state of satiety, was published by Raby, Alexis, Dickinson, and Clayton in *Nature* in 2007. The protective re-caching result, demonstrating knowledge attribution and theory of mind, was published by Emery and Clayton in *Science* in 2001.

The neocortical rewiring result, demonstrating that cortical function is determined by input rather than intrinsic specification, was published by Mriganka Sur and colleagues in *Science* in 1988 and described more fully in Sur and Rubenstein's 2005 *Science* review "Patterning and Plasticity of the Cerebral Cortex."

The Bischof-Köhler hypothesis is reviewed in Thomas Suddendorf and Michael Corballis's 1997 *Psychological Bulletin* paper "Mental Time Travel and the Evolution of the Human Mind," which remains the standard reference for the claim and its subsequent revision.

The dual-system (model-free/model-based) architecture of mammalian reinforcement learning is reviewed in Daw, Niv, and Dayan's 2005 *Nature Neuroscience* paper "Uncertainty-based competition between prefrontal and dorsolateral striatal systems for behavioral control."
