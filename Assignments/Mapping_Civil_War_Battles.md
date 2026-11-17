# Mapping Civil War Battles with an AI Assistant

Nov 17, 2026 · @Trey

## Overview

This assignment is about using an AI assistant to work out **how to make a map in Python**. You will not be given steps or code. You will be given questions about the battles of the American Civil War. For each one, you ask the AI how you could answer it, decide which approach to take, and check that the result makes sense.

**Data:** `cwsac_battles.csv`, from Modules in Canvas. It is based on the Civil War Sites Advisory Commission battle summaries, now published by the American Battlefield Trust at [battlefields.org/learn/battles](https://www.battlefields.org/learn/battles). Each row describes one battle. Work in a Jupyter notebook.

**What you do with it:** load and understand the table, find where each battle took place as longitude and latitude, build a base map of the region, place battles on it, make the size and color of each dot show how many soldiers each side lost, and finally color each state by how much fighting it saw. This is **spatial analysis**: asking where things happened, and what the geography adds to the story.

**What you submit:** your notebook and an HTML copy of it.

## How to work

For every question below, do the same three things in your notebook.

1. **Ask the AI for a plan, not code.** Describe your data and your question, and ask: *what steps would I need, what tools (Python libraries) would I use for each step, and what choices will I have to make along the way?* Paste its answer into a markdown cell. Then edit it: cross out steps you do not need, and put a question mark by anything you do not understand and ask the AI to explain it.
2. **Run it one step at a time.** Ask for code for step 1, run it, look at the output, then move on. Do not ask for everything at once.
3. **Test it against something you know.** A map can be wrong without any error message. A dot can land in the ocean, or in the wrong state, and the code still runs. Always check a few points whose location you already know.

**An example first prompt:**

```markdown
I have a CSV file of US Civil War battles that I'm working with in a Jupyter notebook. Each row has a
battle name and a text description of where it happened. I want to put each battle on a map. Don't
write any code yet. What steps would I need, what Python libraries or tools would I use for each
step, and what choices will I have to make along the way?
```

You do not need to know the tools in advance. Asking which libraries the AI would use, and why, is how you find out what exists. Follow up with: *Are there other libraries that could do this? How do they differ?* Map-drawing tools can also be harder to install than most Python libraries, so ask the AI how to install what it suggests in your setup.

**If the AI does something you do not recognize,** ask it what that line does and why it is needed. You are allowed to question its code.

## Part A: Know your data

You have two kinds of files from Canvas: a table of battles (`cwsac_battles.csv`) and a set of map files with the extensions `.shp`, `.shx` and `.dbf`. Start with the table. Before each step runs, write one line saying what you expect to see.

**1. What is in the table?** Open `cwsac_battles.csv` in a text editor or spreadsheet *before* you load it into Python. What does a row represent? What columns are there? Then ask the AI how to load it into a notebook and what to check afterward (its size, its columns, what type each one is, a few random rows, anything missing). Write down what you learn.

**2. Can Python tell when a battle happened?** The `start_date` column holds dates, but a program may treat them as plain text. Ask the AI how to check, and what is different about a date that Python truly understands. Why would that matter for sorting battles or counting them by year? Then ask how to load the file so that `start_date` is read as a date.

**3. What does the table say about one battle?** Find the battle named **Cold Harbor** (in the `battle_name` column) and print everything the table records about it. Then read the [American Battlefield Trust page on Cold Harbor](https://www.battlefields.org/learn/civil-war/battles/cold-harbor). What do the two sources agree on? What does each include that the other leaves out? If you had only the table, what would you not know?

**4. What is missing or awkward?** Look at the `locations` column. Some battles list more than one place, and two have none. Find them. You will have to decide what to do about them in Part B, so note what you see.

When you finish, write a short description of the dataset in your own words: what one record is, how many there are, what fields it has, which years it covers, and what you **cannot** tell from it.

## Part B: Where were the battles?

To draw a battle on a map, the computer needs numbers: a longitude and a latitude. The table only has a description of the place. Your job is to work out how to bridge that gap.

**1. How can Python turn a place description into coordinates?** Ask the AI what the options are. Ask what each one needs (an internet connection? an account or key?), what limits it has (how many requests per second or per day?), and how it handles a place name that could mean more than one place.

**2. Try it on one battle first.** Use Cold Harbor. Look the real location up in an online map yourself, then compare it with the coordinates Python gives you. Are they close? If not, why not?

**3. Decide how to handle the awkward cases.** From Part A, you know that some battles list several places and two list none. Write down your decision for each before you code it. Which place will you use for a battle with several, and why? What will you do with a battle that has no location? Is there a choice that changes what the final map says?

**4. Do it for every battle, and save the result.** Ask the AI how to run your method over the whole table without crashing halfway, and how to **save the coordinates to a file** so you never have to repeat a slow step. Then report: how many battles you placed, how many you could not, and which ones you do not trust.

**Check:** Pick five battles whose locations you can confirm elsewhere. Do all five coordinates land where they should?

## Part C: Build a base map

A base map is the background that your battles will sit on. Here you assemble one yourself. The shapes of the states come from the map files that came with the assignment, and your job is to get Python to draw them the way you want.

**1. What are these files, and what can read them?** Ask the AI what a `.shp` file is, why it comes with a `.shx` and a `.dbf`, and which Python libraries can draw a map from them. Ask how the libraries differ and choose one. (Different libraries can do the same job, so do not worry if your choice differs from a classmate's.)

**2. Draw the region where the war took place.** The map files cover the whole United States, but the war was fought in one part of it. Ask the AI what it means to set the **extent** of a map, and use it to show roughly the area from the Mississippi Valley to the Atlantic coast and from the Gulf of Mexico north to Pennsylvania. Draw the outlines of the states, nothing else.

**3. Understand the projection.** The Earth is round, and a screen is flat. Ask the AI what a **projection** is, why there are many, and what could go wrong if your battle coordinates and your map use different coordinate systems. Then try changing the projection and see what happens to the shape of the region. Which would you choose for this area, and why?

**4. Make it reusable.** You will draw this map several times. Ask the AI how to wrap your steps in a function that returns the map, so that later you can add points to it without copying code.

**5. What other base maps are out there?** The files you were given are only one choice. Ask the AI what other sources of base maps exist, from other file formats to boundary data that mapping libraries download for you to interactive web maps. Which would suit a map of the 1860s? Then look at your map. What does it show that did not exist during the war (hint: look at the state borders), and what might be missing from it?

**Check:** Does it look like the eastern United States, with Florida, the Gulf coast and Chesapeake Bay where they should be? Is anything stretched, tilted or cut off? Change **one thing at a time** and watch what each setting does.

## Part D: Put the battles on the map

**1. Plot three battles first.** Place **Baton Rouge**, **Munfordville** and **Second Manassas** on your base map and label each one. Do they land in the right states (Louisiana, Kentucky and Virginia)? If a dot is in the wrong place, work out why before you go any further. A common cause is the map and the points using different coordinate systems, so ask the AI how to tell the map what system your coordinates are in.

**2. Plot every battle you placed.** Add all the battles from Part B. Look at the map. Which regions have many battles, and which have few? What is hidden by dots that overlap?

**3. Look at the casualty figures.** The table records casualties for each side. Find the columns. What exactly do they count (killed, wounded, missing, captured)? How many battles have no figure at all? (Around 65.) Which ones are they? Is there a pattern, such as early or late in the war, or small or large engagements?

**4. Decide what to do about the missing figures.** A dot needs a size, and a missing value has none. Ask the AI what your options are (leave those battles off the map, treat them as zero, or fill them in with an estimate) and what each one does to the picture. Choose one and explain why. Make sure a viewer can tell a battle with *no figure* from a battle with a *small* one, for example with a different marker. (If you want to go further, ask the AI what it means to fill gaps with a low percentile of the figures you do have, and what that assumes about the missing battles.)

**5. Show the losses on the map.** Now work out how to make each dot show **how many soldiers each side lost**, using size and color.

Ask the AI what choices you have: what could size stand for, and what could color stand for, when you have two numbers (Union and Confederate losses) for every battle? What does each choice make easy to see, and what does it make harder to see? Choose one, make the map, and add a legend so a reader knows how to read it.

**6. Read your map.** What does the map show that the table did not? Which battles stand out, and where? Are there clusters, and what might explain them? Does geography, such as rivers, mountains or the coast, help explain any pattern? What does your map hide: battles with several locations, the two with none, overlapping dots, the borders of the base map, and the choices you made in Part B?

## Part E: From points to shapes

So far every battle has been a dot. But sometimes the question is about an *area*: which states saw the most fighting? Here you attach data to a **shape** instead of a point.

**1. Which state was each battle in?** Look at the `locations` column again. Entries such as "Limestone County, AL" already name a state. Ask the AI how to pull the state out of that text, and what to do with battles that list several places (and the two that list none). Then count battles per state. Before you code, write down your rule: if a battle spans two states, does it count once for each, or once in total?

**2. Color the states.** Ask the AI what a map is called when *areas*, rather than points, are colored by a number, and how to make one from your base map files. You will need to connect your counts to the shapes, so look at what the map files record about each state and ask the AI how to match your table to them. (State abbreviations, full names and numeric codes are all in use, so be careful.) Include states with **zero** battles, because zero is not the same as missing. Choose a color scale and add a legend.

**3. Check it a second way.** You already have a longitude and latitude for every battle from Part B, and the map files contain the state boundaries. Ask the AI how you could find each battle's state from its *position on the map* instead of from the text. Do the two methods agree? For every battle where they do not, work out which one is right. The cause might be a geocoding error from Part B, a battle near a border, or something about the borders themselves.

**Check:** Do the state counts add up to the number of battles, following your rule for battles in more than one state? Do Baton Rouge, Munfordville and Second Manassas land in Louisiana, Kentucky and Virginia?

**4. Try casualties.** Color the states by total casualties instead of the number of battles, using the choice you made for missing figures in Part D. Does the same state stand out? Why might counts and casualties tell different stories?

**5. Compare shapes with dots.** Put your state map beside your dot map. What does each show well, and what does each hide? Think about large and small states, a few huge battles versus many small ones, and what a state border means for a battle fought along a river or near a boundary. Modern borders place every battle in a *present-day* state. How does that affect your counts?

**If you have time:**

- **Chart the war month by month.** Use the `start_date` column to make a series of maps, one for each month, showing where the fighting was and how costly it was. Ask the AI how to group battles by month, how to arrange many maps in a grid, and what to do about months with no battles. To compare months fairly, every map should use the same base map and the *same dot-size scale*. Ask the AI why, and how. Decide how you will show so many months, and say why. Check one month by counting its battles by hand.
- **Try another way of handling the missing figures** and see which of your conclusions survive the change.

## What to submit

**In your notebook, for each part:** your question, the steps the AI proposed (edited by you), the code and its output, and two or three sentences of your own about what it shows. Add a short **prompt log** near the top listing the prompts that mattered, and mark any where the AI was wrong, incomplete or misleading.

**Reflection (a markdown cell at the end, about 200 words):**

1. Where did asking the AI for options change what you decided to do?
2. Describe one time the AI's output looked fine but you had reason to doubt it. How did you check?
3. Your map makes choices (where each battle is placed, what the dots show). Pick one and explain how a different choice would change what a viewer concludes.

**Before you export:** restart the kernel and run all cells from the top so the notebook works in order. If your geocoding step is slow, load the saved coordinates file instead of repeating it. Avoid printing whole tables, which make the HTML huge. Then export the HTML (JupyterLab: *File, Save and Export Notebook As, HTML*; classic Notebook: *File, Download as, HTML*) and open it in a browser to check that your maps appear.

- [ ] `.ipynb` notebook
- [ ] `.html` copy
