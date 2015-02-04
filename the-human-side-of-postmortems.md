# Reading notes from "The Human Side of Postmortems"

source: http://smile.amazon.com/The-Human-Side-Postmortems-ebook/dp/B00CLH38CM
tags: stress, postmortem, blameless, mindfulness

## Major themes

* Performance under stress
* Stress surface
* The effect of cognitive bias
* Mindful Ops

## Quotes and notes

> More specifically, there are four relative stressors that induce a measurable stress response by the body:
>
> 1. A situation that is interpreted as novel.
> 2. A situation that is interpreted as unpredictable.
> 3. A feeling of a lack of control over a situation.
> 4. A situation where one can be judged negatively by others (the “social evaluative threat”).

> Two effective ways to reduce the stress surface of an outage are training and postmortem analyses.

Game day exercises take the "novel"ness out of certain types of issues, thus reducing the stress.

> The most effective way of mitigating the effects of social evaluative stress is to emphasize the blameless nature of postmortems.

---

> In reality, blame is a shortcut, an intuitive jump to an incorrect conclusion, and a symptom of not going deeply enough in the postmortem investigation to identify the real conditions that enabled the failure, conditions that will likely do so again until fully remediated.

---

> A true mark of an expert is a realistic and humble assessment of the limitations of experience and the extent to which control over complex systems is actually possible. In contrast, less mature engineers tend to develop overconfidence in their own abilities after some initial success and familiarly with systems.

---

> This is not endemic to engineers: despite overwhelming evidence that inexperience is one of the main causes of accidents in young drivers, they consistently fail to judge the extent of their own inexperience and how it affects their safety.

---

> Similarly, it is the many years of seeing complex systems function and fail that allows experienced operations people to quickly identify and deal with conditions of an outage.

---

> Our preference for System 1 thinking, especially in stressful situations, can increase the effects of cognitive biases during outages.

Postmortems frequently suffer from hindsight bias.

> we evaluate what happened during an outage with the benefit of currently available information,

* Hindsight bias - using information that was not available at the time to assess the decisions made at that time
* Outcome bias - the worse the outage, the more we tend to blame the individual(s) involved
* Availability bias - overestimating the impact or frequency of something because of its recency (being able to recall it easily)
* Sunk cost bias - overvaluing an approach because of the time invested, "I almost have it working!"
* Confirmation bias - seeing "what you want to see" in events and data to it may be suggesting the contrary

> Furthermore, especially under stress, we often fall back to familiar responses from prior outages, which is another manifestation of the availability bias. If rebooting the server worked the last N times, we are likely to try that again, especially if the initial troubleshooting offers no competing narratives. In general, not recognizing the differences between outages could actually make the situation worse.

---

> There's certainly nothing wrong with maintaining a positive attitude during a stressful event, but it's worth keeping in mind that confidence is nothing but a feeling that is "determined mostly by the coherence of the story and by the ease with which it comes to mind, even when the evidence for the story is sparse and unreliable".

---

> The way that we can reduce the effects of cognitive biases is by engaging System 2 thinking in an effortful way.

---

> Discussing cognitive biases in PreMortem exercises will help improve their recognition — and reduce their effects — during stressful events.

---

> It’s often easier to recognize other people’s mistakes than our own. Working in groups and openly asking the following questions can illuminate people’s quick judgments and cognitive biases at work:
> 
> How is this outage different from previous outages?
> What is the relationship between these two pieces of information — causation, correlation, or neither?
> What evidence do we have to support this explanation of events? Can there be a different explanation for this event?
> What is the risk of this action? (Or, what could possibly go wrong?)

---

> The best way to work with mental phenomena is through mindfulness. Mindfulness has two components:... recognition of mental events in the present moment... an orientation that is characterized by curiosity, openness, and acceptance

---

> We can similarly mitigate the effects of cognitive biases through mindfulness — we can become aware of when we’re jumping to conclusions and purposefully slow down to engage our analytical System 2 thinking.
