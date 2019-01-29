---
layout: page
author: Jens
title: Local Dynamics and Global Impact
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-01-22T10:20:00Z
---

Having set the tone in my previous two posts I am happy to now introduce the dynamics enforcing segregation of a graph over time. I am going to describe the local behaviour of each node which can be seen as a single agent and its impacts on the whole structure which takes the form of a graph. You are going to see that just some simple local preference of each agent leads to segregation in the network.

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>


# Outline for a baseline model with static world views

Recall that the basic setting was a graph consisting of a vertex set $$V$$ and an set of edges $$E$$. The vertex set is colored with two colors, such that we have two sets $$V_1$$ and $$V_{-1}$$ such that $$V=V_1\cup V_{-1}$$.
I am going to sometimes refer to the interpretation that the vertecies of color $$1$$ and $$-1$$ have opinion $$1$$ and $$-1$$, respectively. This gives me the possibility to talk about actions that each agent performs and might bring the process to a less abstract level. We look at the segregation process in a discrete time scale as mentioned in <a href="{{page.previous.url}}">my previous post </a>. This is due to the fact that the difficulties that come with the rate at which agents change their relationships are not of interest at this point. 

Looking at two agents $$i$$ and $$j$$ we say that edges in $$E$$ display the relations between them.    
<div style="text-align:center">
<img src="{{ site.url }}/images/Interacting_agents.png" height="50%" width="50%" />
</div>
The image shows a <span style="color:red">red</span> edge between the two vertices having different colors, namely, <span style="color:green">green</span> and <span style="color:blue">blue</span>. All the other edges lead to vertices which are not shown inside the frame.   


<html>
<div>
  {% if page.previous.url %}
    <a href="{{page.previous.url}}">&laquo; {{page.previous.title}}</a>
  {% endif %}
  {% if page.next.url %}
    <a class ="next" href="{{page.next.url}}">{{page.next.title}} &raquo;</a>
  {% endif %}
</div>
</html>
