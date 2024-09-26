---
layout: page
title: Savings goal script
description: I have recently come back to Python to reinforce some of my knowledge. I'm in the process of saving up some cash to purchase a new car to replace my old one. I thought that I would take a programming approach to this by creating a simple Python script to show me much I currently have saved, and my target so I can track my progress.
img: false
importance: 1
category: programming
related_publications: false
---

I created a very simple Python script that will be stored locally on my Windows machine which will run on startup which will remind me of my savings target and how far I am off the target. I will employ the use of a seperate .bat file that will run on startup with the use of Windows Task Scheduler.
 
This script works by creating seperate functions for each component of this script's utility. These components include:

1. Loading the savings figures from savings.json.

2. Saving the updated values to savings.json.

3. Displaying the savings progress and current values.

4. Main menu.

Each of these functions are called before the main menu is presented. There is a function for the main menu which presents the user with some options to either edit the savings/goal values, give them a motivational speech or exit the script.

Feel free to check out my [Python script](https://github.com/v-azza/carsavingscountdown/), and it's [documentation](https://github.com/v-azza/carsavingscountdown?tab=readme-ov-file#readme) on how it works, and how to use it yourself.

