---
layout: post
title:      "Ruby Iterators: Looping vs. Interation"
date:       2020-02-07 09:34:06 +0000
permalink:  ruby_iterators_looping_vs_interation
---


One of the most common tasks that we can perform in Ruby is Iteration. This task can also be performed in many other languages, so a good fundamental understanding is important. 

Let's imagine your a coach with a bunch of runner's on a track (eg. an array of runners). You want them to run 2 warm-up laps, With the second lap starting once everyone has completed the first. Would you tell each individual runner to run, or all of them at once? It makes the most sense to tell them all at once. This is how a loop works. The desired action is completed some number of times, or until a conditional is met. Below, we set a count of zero, and then puts out "Take a lap", then increase the count by 1. This continues once more (until we reach 2 in this case

`` runners = [ "Jane", "Jim", "John"]
    count = 0
		while count <= 2 
		puts  
    puts "Take a lap"
   count += 1
   end``

Great, so now the warm up is done. You'd like to hand out some cups of water to everyone. Now, EACH person needs to receive a cup, as they complete their warm up. In this instance it would be appropriate to use something like

``runners.each do | runner| put's  "Here is some water "#{runner}"``

In this statement, for the array #runners, we iterate over the runners using the #each iterator, and offer them some water, integrating their indiviual names by implementing "#{runner}" into our puts statement.

That's a short overview of the difference beteen looping and iteration. I like to remember them as a "grouping" methodology versus an "individual for each object in the group" methodology, respectively.
