---
layout: posts
author: Jens
title:  <html>&#91;RNS&#93;</html> Extended Local Behaviour
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-02-12T10:20:00Z
---

So far, the network's evolution over time was due to the behaviour of pairs of agents, which were linked by a conflict-prone relationship. When taking the whole network into account, one can say, that its evolution is driven by the local behaviour of the agents. So far, the local behaviour was given by two agents and their relationship. But what happens, if we take more agents into account by, for example, introducing preferences on how their neighbours should act in case of conflict? Maybe an agent does not approve that her neighbor agrees to disagree during a conflict and, thus, breaks up her relationship with said neighbour. This can be seen in polarizing discussions, where one can "either be with us or against us". We discuss a model for this situation in this post.     

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>

# Extending the Baseline Model

The situation discribed in the introduction extends our baseline model, in that it adds a new factor to the dynamics. Suppose a conflict-prone relationship exhibits an open conflict, i.e. a <span style="color:red"> red </span> edge is drawn from the set of all edges. Then with probability $$p\in(0,1)$$ the edge is erased and we continue with the baseline model. But with probability $$(1-p)$$ the baseline model just resets and nothing has happend in the time step. This gives us the opportunity to extend the model without changing the dynamics that led to segregation.  

# Ingroup-Outgroup View

This post aims at including an ingroup-outgroup view into the model, where the option to agree to disagree is being punished by the agents having the same opinion. You can see it as a strongly polarized society, where keeping relationships with "the others" is not accepted. 
To model this, we add an event to our evolution process. Instead of simply agreeing to disagree, with probability $$1-p$$ the <span style="color:red"> red </span>edge is still kept in tact but one of the end nodes is drawn randomly. Denoting the edge by $$(i,j)$$, we assume that the agent $$i$$ is chosen. Then, one of $$i$$'s neighbors is drawn randomly, which we call $$n$$ and the relationship between $$i$$ and $$n$$ is erased. Noone wants to be friends with a traitor in a polarized society. Finally, $$n$$ chooses a random new neighbour. I propose the interpretation for not choosing willingly an agent of same opinion as $$n$$ that before having any relationship with another agent one can not know their opinion. Therefore, one can form conflict-prone relationships. 
Let's look at some simulations. Proofs for the behaviour of the network are still open. 
First, I set $$p=0.75$$ and the simulation converged fairly rapidly to a segregated network. The following visualization shows the simulation aggregated over 10 time steps.
<div class="img_container">
<img id="gif-1" src="{{ site.url }}/images/segregation.gif" alt="Full Segregation" height="50%" width="50%"/>
<p>
    <a href="#gif-1"
      onclick="document.getElementById('gif-1').src='{{ site.url }}/images/segregation.gif'">
     Show it again!</a>
</p>
</div>
This seems somewhat sensible, because the probability $$p$$ that two agents agree to disagree is larger than the probability $$1-p$$ that this does not happen and thus one of the neighbors breaks up his relationship with the corresponding agent. The question then rises, what happens if $$1-p>p$$, i.e., $$p<0.5$$? The following simulation shows an episode from a very long simulation for $$p=0.25$$.       
<div class="img_container">
<img id="gif-2" src="{{ site.url }}/images/No_segregation.gif" alt="No Segregation" height="50%" width="50%"/>
<p>
    <a href="#gif-2"
      onclick="document.getElementById('gif-1').src='{{ site.url }}/images/No_segregation.gif'">
     Show it again!</a>
</p>
</div>
The simulation suggests that there is no segregation but rather a convergence towards a state where alot of edges are conflict-prone. Decreasing $$p$$ further and allowing not too many edges in the network indeed leads to intervalls in the simulation where all edges are conflict-prone. A possible interpretation would be that strong polarization within a society does not lead to segregation but to a rejection of agents of similar kind. Formal investigations of this model is an open question and I would love to discuss it with you! So contact me and we dive into it. 
Next time, I am going to introduce another option of how to deal with the probability of $$1-p$$, which is not less exciting and interesting. Spoilar alert: I am going to come back to a subject, which I touched upon in one of the first posts.

Looking forward to see you on my next post!
