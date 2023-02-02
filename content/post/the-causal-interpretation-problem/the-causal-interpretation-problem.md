+++
title = "The Causal Interpretation Problem"
date = "2023-01-04T00:22:37+01:00"
draft = "false"
math = "true"
tags = ["Causality", "Broadbent", "Causal Models", "DAG"]
+++

This post is a rewritten version of a paper I wrote for the *Philosophy of Science* course I took during my Master's Degree.

## Abstract

In support of a solution based on contrastive explanation, Broadbent
[Broadbent, 2013] argues that causal models cannot aspire to a solution of the
Causal Interpretation Problem ({{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}).
The {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}} can be stated
as such: &ldquo;How are we to interpret statistical measures of association as
causal measures of effects of exposures?". In this post I'll discuss Broadbent's theory
and his objections to a causal models based solution to the 
{{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}.
I will next attempt to
demonstrate why his arguments fall short and why even his method cannot be said
to have resolved some of the issues he identifies in the causal models approach.

## Broadbent's Diagnosis (and Treatment)

According to Broadbent, epidemiologists are interested in causality for a variety of reasons, including to influence policymakers, to distinguish between different types of associations, to give their research a strong theoretical foundation, etc. Despite this, they avoid using causal concepts as much as they can. However, it is impossible for an epidemiologist to not indicate or make an implicit causal assumption while discussing associations, even when this avoidance is properly employed. Both practically speaking and theoretically speaking, this conclusion is essential. This leads to a problem that various authors, including Pearl, claim to have solved. Broadbent disagrees and offers a thorough analysis of the issue at hand, which is handled in the section after this one.
### The CIP
In  [Broadbent 2013] the author presents an interesting challenge that epidemiologist constantly face, named the Causal Interpretation Problem ({{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}):

>    [...]how to understand the causal import of a measure of association on those occasions when it is used to express a causal fact, as well as a fact about an association. [Broadbent 2013]


This is a really interesting problem which fundamentally rests on the fact that mathematical measures of association are causally neutral. As Cartwright points out: &ldquo;No causes in, no causes out", so we are facing the challenge to propose an account capable of interpreting measures of association as measures of causal strength. Broadbent proposal in based on an explanatory approach to the problem.

### The Explanatory Approach
Broadbent's aim is not to propose a general theory of causation, but &ldquo;an account of what measures of strength of association means [&hellip;] when they are used to represent [&hellip;] causal facts"  [Broadbent 2013]. His proposal is the following:

> A measure of strength of association is a measure of causal strength if and only if the exposure explains the measured net difference in outcome. [Broadbent 2013]


The notion of explanation used here is based on the idea of contrastive explanation developed by Lipton, which make use of a *Difference Condition* as a necessary but not sufficient condition to characterize a good contrastive explanation. This condition is a sort of reverse of the &ldquo;difference making" condition used by counterfactual theories: the difference lays not in the cause, but in how the effect is displayed, in the sense that

> [A] cause makes a difference in that had it is a difference between the effect
> being as it is and the effect being different or
> absent. [Broadbent 2013]


This idea is cashed out with the following counterfactual:

*Reverse Counterfactual* If 
{{< math "inline" >}}
c
{{< /math >}} causes {{< math "inline" >}}e{{< /math >}} then
{{< math "inline" >}}\neg Oe \mathrel{\mathop\Box}\mathrel{\mkern-2.5mu\rightarrow} \neg Oc{{<
/math >}}. [Broadbent 2013]


Broadbent then uses this framework to propose a solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}, stating
that we must explain difference in outcomes in two population citing a
difference in exposure, which causes at least degree {{< math "inline" >}}n{{< /math >}} of the outcome in the exposed group, with degree {{< math "inline" >}}n{{< /math >}} being any
measure of strength of association  [Broadbent 2013].

This solution seems to beg the question regarding causality (since &ldquo;to cause at least degree {{< math "inline" >}}n{{< /math >}}" appeals to the notion of causation), but Broadbent states that, while this is true if we take &ldquo;to cause at least degree {{< math "inline" >}}n{{< /math >}}" to be a general causation claim, this is not a problem if we interpret this statement as a quantification over individual cases, reducing general causal claims to quantitative claims about singular causation, avoiding circularity.


## Causal Models

In this section I will briefly describe and define causal models and their features. I will then present Broadbent's argument against the causal models approach for solving the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}.

### What a Causal Models Is

A causal model is a mathematical model that represents causal relationships
within a system, thus enabling to predict, or infer, it's behaviour. It
consists of a causal structure (a set of variables {{< math "inline" >}}=V{{<
/math >}} and a set of pairs {{< math "inline" >}}\{\langle X, Y \rangle
; \ldots\}{{< /math >}}, where {{< math "inline" >}}X, Y \in V{{< /math >}}, with
the latter representing direct functional relationships between variables) and
a set of parameters assigning values to the functional relationship of each
variable based on its parent: {{< math "inline" >}}x_i = f_i(pa_i){{< /math >}}
where {{< math "inline" >}}pa_i{{< /math >}} are the parents of {{< math
"inline" >}}x_i{{< /math >}}[^5]. [Pearl 2009]

A causal model can assign probability values to counterfactual claims about the system, predict effects of interventions and entail probabilistic (in)dependence between variables [Hitchcock 2020]. It can be used in a reverse fashion too: given a probability distribution and some constraints is possible to determine a unique causal model (or, missing the constraints, a family of causal models) that fits the data and describes the system[^6]. Causal models can be represented via direct graphs, where arrows between variables represent causal relationships. An example is given in [Figure 1](#DAG).


{{< rawhtml >}}
<a name="DAG"></a>
<figure style="text-align: center;">
<img class="toinvert" src="cn1-1.svg" alt="DAG1">
<figcaption style="font-size: 80%">A Direct Acyclic Graph (<abbr title="Dyrect Acyclic Graph">DAG</abbr>)</figcaption>
</figure>
{{< /rawhtml >}}
    

Where arrow tips represent the causal relationship between variables as prescribed by the set of pairs: {{< math "inline" >}}\langle A,B\rangle; \langle A,C\rangle; \langle B,D\rangle{{< /math >}}. Causal models have seen, since the advent of the multi-causal model of disease and the development of a complex and effective framework (mostly thanks to Pearl), a surge in popularity in the context of epidemiological research: thanks to their features, causal models are the best way to represent complex systems, in which multiple interaction contribute to the onset of a disease or a state of ill health. They are seen by some authors as the best way to make causal inferences and to analyze the causal dynamics of a system or phenomenon [Pearl 2009].

Broadbent argues for the incapability of the causal models approach to solve the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}, laying out some of its problems. In the next section I will present Broadbent's analysis of causal models approaches to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}.

### Causal Models and the CIP
Causal models can, in principle, offer a solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}, namely, they can interpret causal claims about population as a claim about

>    [&hellip;]what would happen *under the assumption that certain variables have certain values and that certain relations between variables hold.* [Broadbent 2013]



We can easily see that this kind of claims are quite easily yielded by causal models simply by modifying a structural equation from {{< math "inline" >}}x_i = f_i(pa_i){{< /math >}} to {{< math "inline" >}}x_i=\mathbf{x}{{< /math >}} and calculating the resulting probability distribution or the values of the descendant variables.


Broadbent points out two primary problems of causal models relating to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}.
The first one is an epistemological problem: the question regarding what would happen translates to a question regarding the actuality of the model. If more than one model fits the data and only some of them satisfy the conditions for causation specified by the modeller, we cannot tell the correct causal interpretation until we decide which is the correct model. This is a kind of under-determination problem.

The second one is a metaphysical problem: causal models do not really answer the question regarding causation, and they
are at risk of circularity too.
The first claim is justified by the author by saying that 

> One can still seek to dream up unusual causal scenarios in which the conditions for causation specified by a given
> theorist are not satisfied. [Broadbent 2013]


This claim struck me as highly unspecific and I wouldn't regard it as a real argument, but I will discuss it nonetheless in the next section.

The risk of circularity, following Broadbent, is embedded in causal models because of their structure: causal models are never complete, the modeller need to make decisions about what factors to capture and to use in a model, excluding some others. Those decision rely on a notion of causation, since we are excluding factors that could causally influence the outcome, but, by stipulation, do not. Since the notion of influence on which the model relies is causal, we cannot treat causal models as a way to reduce causation and explain the interpretation of measures of association as causal.

I will discuss all those problems in the following section.



## Problems of Broadbent's Arguments and Account
In this section I will address the problems pointed out by Broadbent regarding causal models and try to show that they affect the explanatory approach too.
The discussion of those problems by Broadbent is vague and not in depth, so I will try to infer the underlying position and judgments that inform the arguments.

Besides, Broadbent's arguments do not really challenge the causal models-based proposal for solving the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}, but they aim directly at causal models, trying to undermine them. I do not really understand this line of discussion since it seems that Broadbent aim is to challenge causal models as methods for discovering causal relationships, instead it should be to dismiss the proposed solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}. Given that, I will try to defend the causal models approach taking for granted the validity of its solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}.

After the discussion of Broadbent arguments, I will lay out some problems of Broadbent's proposal regarding the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}} and the general framework of the contrastive approach. The problems presented are general in nature and the argument are meant to be general arguments against some of Broadbent's positions, without a narrow focus.


### Responses to the Epistemological Problem
The epistemological problem of causal models regards the fact that we have no means to distinguish an actual causal model from a non actual causal model given that the data fits both of them, so we cannot be sure about the correctness of the causal interpretation.


While I recognize this as a big concern, I have doubts that the explanatory approach does not display the same sort of problem. It states that to explain a difference in outcome, we must cite a difference in exposure, which causes at least degree of {{< math "inline" >}}n{{< /math >}} of the outcome cases. 


The problem pointed out for causal models is translatable, for the explanatory approach, in the following: how do we know that an exposure is the actual cause of at least degree of {{< math "inline" >}}n{{< /math >}} outcomes? If is impossible to determine with certainty if some exposure is a cause or not in a causal model (since it's possible that some other model fits the data, in which some different factor acts as a cause, or there is no cause at all, etc.) how is it possible that we can determine a causal role of an exposure by appealing to the claim that exposure did cause the outcome in at leas degree of {{< math "inline" >}}n{{< /math >}} cases?
It is not useful to appeal to some effect-led difference making conditions, since the causal model would be able to capture those too, and if that was the way of discriminating between which variable is a cause and which is not, than we should be able to determine a unique causal model or, at least, a family of models all of which identify the same variable as a cause, but with some differences in respect of other variables' roles[^9].


I can see a lot of problems with Broadbent's claim. Causal models try to capture the underlying causal structure of the phenomenon. Imagine a case in which the observable variables underdetermine the models (in the sense that more models can fit the data). This is a case where the causal dynamics of the models are not clear at all, in the sense that we cannot determine with certainty which variable is causally related to another variable. If a causal models fails in this identification, how can the explanatory approach be sure that the exposure is the cause of at least degree of {{< math "inline" >}}n{{< /math >}} of the outcome observed, given that we cannot capture the underlying causal structure of the system? Could not there be another cause?

Overlooking this problem seems justified only if Broadbent gives his approach an unfair advantage: that the explanatory approach can be informed by causal judgment that humans constantly make, which can help determine the cause with more certainty, while the causal models approach is not granted this advantage. When a causal models fails to capture a system with certainty, it seems difficult to me that we could be able to identify the underlying causal structure. But the modeller can make informed guesses based on background knowledge, rules and principles, and the natural causal insight that humans possess, which can help to assign a greater probability of actuality to a specific model, not counting the already cited Minimality and Faithfulness conditions. The fact that variables can usually be time ordered helps too.

Besides, throughout the book, Broadbent is rarely concerned with truth (which seems what he means with actual). For example, truth is not the focus or the aim of good epidemiological research; instead stability is. I would argue that this sudden preoccupation for truth is instrumental for arguing against causal models. If we are faithful to the concept of stability, we should agree that if a causal model is hold to be stable then its output regarding what measure of association is to be interpreted causally must be accepted.



### Responses to the Metaphysical Problem

As we saw the metaphysical problem of causal models regards their inability to answer the question about causation. I partially agree with this claim, but I find the argument that Broadbent brings to the discussion not specific and vague.

It might be true that we can construct causal scenarios in which the condition for causation are not satisfied, but I would argue that a solid causal discovery framework (e.g. [Pearl 2009]).
Besides, for what I can think of, unusual causal scenarios are rarely found in nature, and a framework for causal interpretation of association measures is not meant to give a general account of causation, as Broadbent too points out when presenting the explanatory approach. Causal models achieve a good explanation of the causal import of a measure of association in the context of epidemiology, social sciences, economics etc., their aim is not to reduce causation in general.
Anyway, those kind of claims can be made for every approach to causality, so I'll dismiss it without further discussion[^10].


### Problems of the Explanatory Approach
Broadbent proposes the explanatory approach as a solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}. While I appreciate the novelty of the proposal and the focus on effect-led difference making and the contrastive approach, I have found some problems in the proposal.

The first problem regards the appeal to singular causation in the explanatory approach. It has been extensively argued about the difficulties of determining instances of singular causation, even with the contrastive approach that Broadbent uses throughout the book [Broadbendt 2013].


The problem with the explanatory approach is that we cannot determine that a token outcome has been caused by the exposure, since this knowledge is almost always epistemically inaccessible (we cannot claim that _this_ instance of smoking _did cause this_ lung cancer, since we do not have the means to determine if this is true or not).

Another problem is the primitiveness of the notion of singular causation that Broadbent states, without justification. This is a quite debatable choice. As Danks points out, claims of singular causation are usually rooted in general causation claims (we say that this instance of coffee drinking caused this tremors because we know that coffee may cause tremors, as Danks points out):

>    singular causation requires knowledge of (at least) both the general causation that applies in cases of this type, as well as details about this particular case. [Broadbent 2013]


So even Broadbent proposal is at risk of circularity, nevertheless he claims it is not and addresses the problem in few sentences. Broadbent needs to justify why quantifying over singular causal claims does not lead to circularity regarding general causal claims more in depth, otherwise his position is precarious.


Regarding the contrastive approach, it can be said that there are no clear boundaries for the selection of the contrast class. The selection is informed by background knowledge: to determine the cause of a fire in a spaceship needs a different contrast class than determine the cause of a fire in a house: namely, oxygen presence is relevant for one case but not for the other [Broadbent 2013]. The selection is itself informed by causal judgements too: if we are to explain why smoking causes lung cancer, our contrast class will not comprehend people that has been exposed to asbestos for example, because we know that asbestos has a causal relationship with lung cancer.


As stated earlier: it is always possible to imagine unlikely scenarios in which
the conditions for causality do not hold, and this is a problem encountered by every
account that tries to address the {{< rawhtml >}}<abbr title="Causal
Interpretation Problem">CIP</abbr>{{< /rawhtml >}} and causality in general. A clear
example of some headaches that the contrastive approach may cause is the notion
of disease as defined in  [Broadbent 2013], in which the selection of the
contrast class is fundamental for the correct definition of a disease but no
conditions are specified for the construction of this class, leaving no clear instruction regarding this selection.

Finally, the definition provided for the circumstances under which an exposure is deemed a cause is open to _not genuine causes_. There could be an infinite number of variables that, under this approach, could be regarded as causes. To function properly and be successful, for the explanatory approach some omitted clauses that permit us to distinguish between _causes_ and _non causes_ must be made explicit. Either a parasitic behavior toward causal models is required, so the model can skim and leave only actual causes for the explanatory approach to work on, or some sort of background-informed judgement is required to avoid the chance of non-causes being treated as causes.
The
former  would be basically a declaration of surrender since it would state the
necessity of causal models for the discrimination between genuine and non
genuine cause, giving them a strong position to argue for a causal models-based
{{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{<
/rawhtml >}} solution. The latter needs specification which is omitted and
should thus be produced. Besides, background-informed judgement are notoriously subjective and difficult to asses properly.

## Conclusions
We have seen how most of the problems highlighted by Broadbent regarding causal models and the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}} can be challenged and how even his own account suffers some of them.

I find Broadbent's approach really interesting and fecund: its intuitiveness and simplicity are surprising, and is absolutely effective. But the proposal is, in my opinion, still rather vague. It is in its early stages and still not thoroughly analyzed and challenged by the literature, which is mainly afferent to the epidemiological field or regards topics other than the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}} and causal interpretation.

I showed why I believe causal models approaches are not as weak as Broadbent depicts them and can therefor aspire to a solution to the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}}, especially the solution proposed by Menzies [Menzies 2004].
I think it would be wrong not to treat causal models as a good approach to causality and the {{< rawhtml >}}<abbr title="Causal Interpretation Problem">CIP</abbr>{{< /rawhtml >}} only because they may fail in some really strange situations.
If we had a complete framework of causality, able to capture every kind of causation regardless of the causal scenario, it would be the case to advocate for it and let go causal models. But we still do not have this framework.

Disregarding causal models for this reason would be counterproductive, since they have proved themselves highly successful and an ever-growing research effort is put on them. The raising of AI and deep neural network has proved to be fertile territory for those kind of approaches, not only in epidemiology, but in all kinds of fields.
This kind of success is not explicable if they were not able to capture, at least partially, the hidden causal nets of complex systems and phenomena, and to make causal inference and explanation easy and accessible.

[^5]:Given the purpose of this post, disturbance components will be ignored.
[^6]:See [Hitchcock 2020], Section 4 for a thorough analysis.
[^7]:Broadbent, Alex. _Philosophy of Epidemiology._ London: Palgrave Macmillan UK, 2013. [http://link.springer.com/10.1057/9781137315601](http://link.springer.com/10.1057/9781137315601)
[^8]:_Ivi_
[^9]:In this case the Minimality and Faithfulness condition, plus Occam's Razor, can help us skim and identify which causal model to use. See [Pearl 2009],
[Hitchcock 2020],
[Halpern and Pearl 2005] for a detailed presentation of those conditions.

[^10]: Is always possible to construct an unlikely causal scenario which gives
  rise to problems given a definition of what a causal relation is, or what does it mean
  to interpret a measure of association as having causal import. I do not mean
  to dismiss this problem as not relevant. Research is always pushed by
  convoluted and clever counterexamples that philosophers are able to find, so
  I'd prefer to treat them as an occasion for striving for improvement and
  adjusting the account, and not as a serious undermining arguments, unless the
  flaw is displayed exclusively by said account. This is not the case here, so I
  will proceed bypassing this point [Danks 2017].
[^11]:See _ivi_.
[^12]:_ivi_.
[^13]:Example taken from _ivi_.


## Bibliography

Broadbent, Alex. “Causation and models of disease in epidemiology.” _Studies in History and
Philosophy of Science Part C :Studies in History and Philosophy of Biological and Biomedical
Sciences_ 40, 4 (2009): 302–311. [http://dx.doi.org/10.1016/j.shpsc.2009.09.006](http://dx.doi.org/10.1016/j.shpsc.2009.09.006).

------. “Causes of causes.” _Philosophical Studies_ 158, 3 (2012): 457–476.
. Philosophy of Epidemiology. London: Palgrave Macmillan UK, 2013. [http://link.springer.com/10.1057/9781137315601](http://link.springer.com/10.1057/9781137315601).

Danks, David. “Singular Causation.” In _The Oxford Handbook of Causal Reasoning_, edited by
Michael R. Waldmann. Oxford University Press, 2017, 202–219. [http://oxfordhandbooks.com/view/10.1093/oxfordhb/9780199399550.001.0001/oxfordhb-9780199399550-e-15](http://oxfordhandbooks.com/view/10.1093/oxfordhb/9780199399550.001.0001/oxfordhb-9780199399550-e-15).

Halpern, Joseph Y., and Judea Pearl. “Causes and explanations: A structural-model approach.
Part I: Causes.” _British Journal for the Philosophy of Science_ 56, 4 (2005): 843–887. [https://www.journals.uchicago.edu/doi/10.1093/bjps/axi147](https://www.journals.uchicago.edu/doi/10.1093/bjps/axi147).

Hitchcock, Christopher. &ldquo;Causal Models.” In _The Stanford Encyclopedia of Philosophy_, edited by
Edward N Zalta. Metaphysics Research Lab, Stanford University, 2020. Summer 2nd edition.
[https://plato.stanford.edu/archives/sum2020/entries/causal-models/](https://plato.stanford.edu/archives/sum2020/entries/causal-models/).

Menzies, Peter. “Causal models, token causation, and processes.” _Philosophy of Science_ 71, 5 (2004): 820–832.

Pearl, Judea. Causality. Cambridge University Press, 2009.

