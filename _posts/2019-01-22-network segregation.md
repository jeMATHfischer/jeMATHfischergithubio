---
layout: posts
author: Jens
title:  <html>&#91;RNS&#93;</html> Local Dynamics and Global Impact
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-01-22T10:20:00Z
---

Having set the tone in my previous two posts, I am happy to now introduce the dynamics enforcing segregation of the graph over time. I am going to describe the local behaviour of each node, which can be seen as a single agent, and its impacts on the whole structure, which takes the form of a graph. You are going to see that just some simple local preference of each agent leads to segregation in the network.

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>


# Outline for a baseline model with static world views

Recall that the basic setting was a graph consisting of a vertex set $$V$$ and an set of edges $$E$$. The vertex set is colored with two colors, such that we have two sets $$V_1$$ and $$V_{-1}$$ with $$V=V_1\cup V_{-1}$$.
I am going to use the interpretation that the agents, represented by vertecies of color $$1$$ and $$-1$$, have opinion $$1$$ or $$-1$$. This gives me the possibility to talk about actions that each agent performs based on his opinion. I hope that this way I can bring the process to a less abstract level. We look at the segregation process in a discrete time scale as mentioned in <a href="{{page.previous.url}}">my previous post </a>. This is a simplification that can be defended because we are interested in the phenomenon itself and not the real time speed. Essentially, dealing wiht the difficulties that come with the rate, at which agents change their relationships, does not give new insights at this point. 

Looking at two agents $$i$$ and $$j$$ one can see the edges in $$E$$ as the relationship between them. A relationship between agents of different opinion is shown in the next picture.    
<div class="img_container">
<img src="{{ site.url }}/images/Interacting_agents.png" height="50%" width="50%" />
</div>
The image shows a <span style="color:red">red</span> edge between the two vertices having different colors, namely, <span style="color:green">green</span> and <span style="color:blue">blue</span>. All the other edges lead to vertices which are not shown inside the frame. We, therefore, concentrate on this edge. Since there is conflict between the <span style="color:green">green</span> and <span style="color:blue">blue</span> agent, the <span style="color:red">red</span> edge linking them is may be erased. Their relationship might be broken up.
In every time step we draw randomly an edge from all edges in the graph. If it is a <span style="color:red">red</span> edge we keep it otherwise we advance one timestep and draw a new one. You can imagine it like drawing some colored ball from an urn of balls. Drawing an edge can be seen as an outbreak of an open conflict. The edge is then erased with some probability $$0<p<1$$. The interpretation is that with probability $$p$$ the relationship is broken up while with probability $$1-p$$ the  <span style="color:green">green</span> and <span style="color:blue">blue</span> agent decide to agree to disagree and keep their relationship intact. Subsequently one of the two agents seeks out a new relationsship with any agent she does not have a relationsship with, yet. This again happens by randomly choosing either the <span style="color:green">green</span> agent or the <span style="color:blue">blue</span> agent. The random factor is implemented to avoid micro-dynamics concerning the responsibilities in the break up and the agents' subsequent psychological needs.    
This way after one time step we have broken up one relationsship and created a new one. Keep in mind, that we can only erase <span style="color:red">red</span> edges but may create a <span style="color:green">green</span> or <span style="color:blue">blue</span> edge. If that happens there are less <span style="color:red">red</span> edges in the next timestep. The number of <span style="color:red">red</span> edges thus is monotonically decreasing under these dynamics. The process is depicted for some time steps in the following image.   
<div class="img_container">
<img src="{{ site.url }}/images/baseline_some_steps.gif" height="50%" width="50%" />
</div>
In fact, under these dynamics all red edges will be erased after finite time. Consequently, in the end there are no more conflicts and all agents are solely linked to their own kind. 
<div class="img_container">
<img id="gif-1" src="{{site.url}}/images/segregation_full.gif" alt="Full Segregation" height="50%" width="50%"/>
<p>
    <a href="#gif-1" 
      onclick="document.getElementById('gif-1').src='{{site.url}}/images/segregation_full.gif'">
     Show it again!</a>
</p>
</div>
To close, I want to remark that a single agent does not realize when or if there is segregation. By following her preferences to connect with agents of own kind the macroscopic pattern emerges even though it is not the agent's intention.

Next time I am going to give the full mathematical framework as a stepping stone to extend this model to non-binary opinions. But we will see that binary opinions are not the problem and segregation emerges also in related models.

I hope you enjoy the series so far and see you soon!
