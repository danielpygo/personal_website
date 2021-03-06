---
title: "Evolutionary Algorithms"
description: "Learning to play Pytux - a 2D platformer using gradient-free learning"
date: '2018-11-17'
layout: 'programming'
featured: "false"
---
Last night, for my neural networks class, we were told to make Tux (basically mario but a penguin)
complete all the levels using a gradient free method. It was interesting because it was fine tuning a model
that was able to get decently far into the level.


In my previous model I used convolutional neural network to feed
into the features of a GRU Recurrent network. Then, without needing backprop, I trained 20 models using some small deviation
on the parameters, and generated rewards for each of them. I noticed my stddev being too high would just destroy my
model so I had to tune the starting std down.


I kept the top 4 models around, and generated 16 new ones using the best offspring's genetics! I decided to keep the top 20% around, because I didn't want my model to get worse over time. That was
one optimization I used! Also used a hashmap to store indices -> (mean,stdev) in order to calculation the perturbation or noise on a parameter for fast lookup.


I used python3 and pytorch on this project and really enjoyed the visual element to it, I could see how the offspring were playing the level!
