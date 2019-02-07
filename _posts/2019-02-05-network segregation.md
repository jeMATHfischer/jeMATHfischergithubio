---
layout: posts
author: Jens
title:  <html>&#91;RNS&#93;</html> Segregation in Diverse Populations
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-02-05T10:20:00Z
---

Having set the mathematical framework for the baseline model, we can now talk about each step in the process and its influences on the process. This gives us the opportunity to extend the model in various ways from a mathematical perspective. The interpretation of the network as an interconnected population and agents of different opinion will be our main constraint. I am going to introduce two extensions to populations that exhibit way more than two opinions (even infinitely many). 

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>


We defined transition between graphs in terms of the edges at time $$t$$ as follows.
In the step from time $$t$$ to time $$t+1$$, an edge $$(I,J)$$ is removed and replaced by an edge $$(I,e^{\ast}_1)$$ with probability $$p$$ if $$|c_I - c_J|\geq |c_I - c_{e^{\ast}_1}|$$. The inequality reduces to the interpretation that the agent $$I$$ gives up the relation to $$J$$ in favor of the relation to $$e_1^{\ast}$$ if the opinions of $$I$$ and $$e_1^{\ast}$$ displayed by the corresponding colors exhibits a greater similarity.

I proposed some questions that one may pose when investigating this graph evolution.
 1. When do the colors play a role?
 2. Is the number of different colors important?
 3. Why do the colors have to be discrete?

# 1.) When do the colors play a role? 
The colors only come into play when we compare the color of the end points. BUT (a big one) they are only present in terms of their difference! This leads to a clustering of agents of similar opinion, i.e., edges between smiliarly colored nodes because $$|c_I - c_J|=0$$ only if $$c_I = c_J$$. That means only edges between nodes of the same color remain in the end because they cannot be replaced by edges which are conflict prone and that was the goal of the model. 

# 2.) Is the number of different colors important?
Using two colors allowed us to identify them with two integers in our case $$-1$$ and $$1$$. Each color was in that case representing a specific opinion. If we want to extend the model to more than two colors, we could just introduce more integers and continue to use the condition $$|c_I - c_J|\geq |c_I - c_{e^{\ast}_1}|$$ for erasing and rewiring edges. The problem or opportunity is that integers inherently carry an ordering. Thus, if we introduce for example colors ranging from $$-2$$ to $$2$$, we find that the similairy between $$-1$$ and $$-2$$ is larger than between $$-1$$ and $$1$$, identifying our measure of similarity by the difference of two integers $$|-1  - (-2)|=1< |-1 - 1|=2$$. But since the integers only represent colors and, therefore, opinions that we wanted to encode to fit our mathematical framework we cannot just arbitrarily assign  integers to opinions. The opinions should yield the same hierarchy that the integers suggest. Considering for example five different political parties ranging from far left to far right described by far left (fl), left (l), center (c), right (r) and far right (fr). Then fl and l have a higher similarity in terms of their opinions than fl and fr. This should also be reflected in our model in the form fl: $$-2$$, f:$$-1$$, c:$$0$$, r:$$1$$ and fr: $$2$$. So assigning the integers in a sensible way is an afford that has to be made to compare the model outcome to empirical data.    

# 3.) Why do the colors have to be discrete?
They don't. The model can be directly extended using $$|c_I - c_J|\geq |c_I - c_{e^{\ast}_1}|$$ to erase and rewire. The case made in 2.) stays valid, though, but is a bit more flexible since the minimal distance between two opinions can be modeled as infinitesimally small. A possible segregation may look as follows where the visualization is chosen to cluster colors which are highly interconnected.

<div class="img_container">
<img id="gif-1" src="{{ site.url }}/images/segregation_mult_color.gif" alt="Full Segregation" height="50%" width="50%"/>
<p>
    <a href="#gif-1"
      onclick="document.getElementById('gif-1').src='{{ site.url }}/images/segregation_mult_color.gif'">
     Show it again!</a>
</p>
</div>

So, you see there are various ways to extend the model fairly directly. Two other paths one could take is to focus on what happens if an edge is not split, i.e., what happens with probability $$1-p$$, or if one introduces <a href="https://en.wikipedia.org/wiki/Preferential_attachment">preferential attatchement </a> in the sense that each node tries to connect to nodes which increase the sum of their assigned integers. In the second case, the interpretation must change from opinions to for example wealth to arrive at the interpretation that each agent tries to form a relation to those who have more. In the model, this translates to changing $$\vert c_I - c_J\vert$$ into $$\vert c_I + c_J\vert$$. We are going to explore these extensions in the upcoming posts, but I am also going to post independent posts, which do not belong to any series in between. I hope, you find those interesting, as well.   

See you next time!
