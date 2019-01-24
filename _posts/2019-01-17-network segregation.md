---
layout: page
author: Jens
title: Randomized Network Segregation
description: This is the first of a series on Network Segregation as a result of agent based models.
---

# Schelling's Segregation model

Thomas Schelling proposed in 1971 a model to discribe the ethnical segregation in the larger cities of the US. 
<div style="text-align:center">
<img src="{{ site.url }}//images/chicago_seg.jpg" height="50%" width="50%" />
</div>
His agent based model showed that segregation also happens if the agents do not mind living next to agents of different kind. 
The basic concept was to put the agents on the nodes of a grid and allow in every time step a transition according to their current preference. 
One agent A's current preference was thereby defined as the proportion of agents of similar or dissimilar kind surrounding A. 
If the proportion dropped below a fixed threshhold then A starts to move on the grid trying to improve the proportion.
A gameified simulation can be found <a href="https://ncase.me/polygons/"> here </a>.

# Segregation of Networks

The main dynamics of Schelling's model is given by the agent's movement along the grid on which they are placed. Their movement is therefore inherently constrained by the structure of their environement.
When considering networks that connect agents which are not subject to this constraint, e.g., social networks on the internet, Schelling's model is no longer applicable. Nonetheless, we observe segregation in these networks where connections are given up due to diverging values or political views.
During this series I want to present a basic model for segregation in networks on which I am currently working on and hope to give live updates on the results. 
During the first few posts I am going to present my simplest model and introduce some extensions always paired with some simulations.  
