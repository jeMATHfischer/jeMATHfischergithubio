---
layout: posts
author: Jens
title:  <html>&#91;RNS&#93;</html> The Mathematical Formulation
description: This is the first of a series on Network Segregation as a result of agent based models.
date: 2019-01-28T10:20:00Z
---

In the previous post, I described the dynamics of our network in terms of agents and their individual opinions. Furthermore, I motivated the mathematical approach in terms of graphs and demonstrated via a simulation the segregation of the process. This post serves as a bridge to extend our discussion of segregation of networks further. To that end, I introduce the mathematical framework with all necessary notation. After having set this groundwork, we can easily extend the model, so bear with me.

<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>


# A Mathematical Formulation of Segregation
At the end of the previous post, we reached this depiction of the segregation behaviour.
<div class="img_container">
<img id="gif-1" src="{{ site.url }}/images/segregation_full.gif" alt="Full Segregation" height="50%" width="50%"/>
<p>
    <a href="#gif-1" 
      onclick="document.getElementById('gif-1').src='{{ site.url }}/images/segregation_full.gif'">
     Show it again!</a>
</p>
</div>

But how can we frame this behaviour mathematically? My approach of choice is to view the network as a graph with vertices colored with two different colors and define a suitable evolution on it. The central part are edges between vertices of different colors. I call these edges "bichromatic".

The process $$(G_t)_{t\in \mathbb{N}}$$, which represents the evolving network in form of colored graphs $$G=(V,E)$$, is defined by a erasing-and-rewiring procedure of the edges. Each time step of the discrete time process is subdivided into the following steps.
$$(G_t)_{t\in \mathbb{N}}=((V,E_t))_{t\in \mathbb{N}}$$ begins at time $$t=0$$ with the initial graph $$G_0=G$$. We set $$G_t^c= G_c\backslash G_t$$, i.e., the graph resulting when removing from the complete graph $$G_c$$ with vertex set $$V$$ all edges from $$G_t$$. Denote by $$E_t^c$$ the set of edges of $$G_t^c$$. Additionally, for any vertex $$i\in V$$ its color is written as $$c_i\in\{-1,1\}$$.

We define the following transition between graphs in terms of the edges denoted by $$E_t$$.
At each time step $$t\geq 1$$, assuming that $$G_{t-1}$$ is a simple graph, we draw uniformly a random edge $$(I,J)\in E_{t-1}$$. We then draw without replacement edges from $$E_t^c\cup\{(I,J)\}$$ until we draw one, which we call $$e^{\ast}$$, that has either $$I$$ or $$J$$ as endpoint. Note that this "or" is not exclusive. The endpoints of $$e^{\ast}$$ have the names $$e^{\ast}_1$$ and $$e^{\ast}_2$$. From this point on I assume for reasons of readability that $$e^{\ast}$$ and $$(I,J)$$ share the end node $$I=e^{\ast}_2$$.

If $$|c_I - c_J|\geq |c_I - c_{e^{\ast}_2}|$$, we remove the edge $$(I,J)$$ with probability $$p>0$$ from $$E_t$$ and add the edge $$e^{\ast}$$ to $$E_t$$. Thus,
$$E_{t+1} = (E_t\cup\{e^{\ast}\})\backslash\{(I,J)\}$$

# Remarks to take away

There are some remarks to be made, to take away the essence of this evolution process.

 - The vertex set $$V$$ stays the same throughout the process. No vertices are removed or added.
 - When starting with a graph $$G_0$$ that allows at most one edge between two vertices, this property is preserved for all times.
 - The probability $$p$$ to remove edges plays an important role in the speed of the segregation.
 - Once an edge between two identically colored vertices of color $$c$$ exists, it can only be replaced by an edge between two vertices of color $$c$$. 
 - The number of bichromatic edges is (because of the previous point) almost surely non-increasing.

When going through the definition of the evolution process, one may realize a pecularity regarding our current restrictions to two colors. When do the colors play a role? Is the number of different colors important? Why should they be discrete?

The answers to these questions will be the topics of the upcoming posts, so stay tuned!
