---
layout: posts
author: Jens
title: A Baseline Model
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-01-19T10:20:00Z
---

In this post, I introduce a baseline model for segregation of graphs. In contrast to Schelling's model, which put the agent on the nodes of a grid in the center of attention, I am going to focus on the behaviour of the edges. The edges play the role of a social connection, say relationship, that may be broken up, if the two end nodes diverge too drastically in their world views.

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>


# Outline for a baseline model with static world views

The first and most simple framework is to look at a graph consisting of a vertex set $$V$$ and an set of edges $$E$$. One then colors the vertex set in two colors, i.e., we have two sets $$V_1$$ and $$V_{-1}$$ such that $$V=V_1\cup V_{-1}$$.
We can interpret the vertices of color $$1$$ and $$-1$$ as having opinion $$1$$ and $$-1$$, respectively. This is a very simplified model because our population exhibits two distinct opinions, exclusively, but this approach can serve as a baseline model.
Each edge $$e\in E$$ then displays the relationship between two individuals, given by the two end nodes of $e$.    
<div style="text-align:center">
<img src="{{ site.url }}/images/bimodal_population_init.png" height="50%" width="50%" />
</div>
The <span style="color:green">green</span> and <span style="color: blue">blue</span> edges between the <span style="color:green">green</span> and <span style="color:blue">blue</span> vertices in the preceding picture depict relationships between individuals of identical opinion <span style="color:green">green</span> or <span style="color:blue">blue</span>, respectively. They are not prone to conflict because both individuals are perfectly aligned.
In contrast, the <span style="color: red">red</span> edges are those that display potential conflict. They connect individuals, who have different opinions displayed by the vertices having different colors.  
There are two possible ways to go forth in the modelling procedure.
First, we can imagine agreement to occur such that both individuals find common ground and the conflict is resolved. Within the framework of two possible opinions, agreement is only possible, if one of the individuals takes the opinion of the other, i.e., one of the vertices swaps the color. This process does not lead to segregation, but to the spread of one opinion and fits rather in the setting of <a href ="https://en.wikipedia.org/wiki/Genetic_drift">Wright-Fisher type models</a>. We are going to come back to this process later on in the series.
<div style="text-align:center">
<img src="{{ site.url }}/images/contagion.gif" height="50%" width="50%" />
</div>

Since the last model could not capture segregation, we focus on a different approach. In this case, the conflicts are resolved by breaking up the relationships between the individuals of different opinion. This will necessarily lead to segregation. But what happens, if we allow forming of new relationships to compensate for the broken one? This is going to be our baseline model.

# Segregation in the baseline model

My proposed baseline model shows the following dynamical behaviour of our population. The population, represented by a graph, consists of <span style="color:green">green</span> and <span style="color:blue">blue</span> vertices as well as <span style="color:green">green</span>, <span style="color:blue">blue</span> and <span style="color:red">red</span> edges. 
The process runs in discrete time, so starting from $$t=0$$ we go to $$t=1$$ to $$t=2$$ and so on. In each step, we erase a <span style="color:red">red</span> edge and connect one of its end points randomly to another vertex. The process stops as soon as there are <span style="font-weight:bold">no</span> more <span style="color:red">red</span> edges. 
<div style="text-align:center">
<img src="{{ site.url }}/images/baseline_flip.gif" height="50%" width="50%" />
</div>

In the upcoming posts I am first going to discuss the concrete model and its mathematical properties. Afterwards, we are going to look at the convergence behaviour, to then advance the model to more opinions and, therefore, colors in the graph. Thus, with each subsequent post the complexity is going to increase.

See you on my next post! 
