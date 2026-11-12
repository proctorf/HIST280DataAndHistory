# Distant Reading with an AI Assistant: Supreme Court Opinions

Nov 12, 2026 · @Trey

## Overview

This assignment is about using an AI assistant to work out **what is possible** with a collection of texts. You will not be given steps or code. You will be given questions about a century of US Supreme Court opinions. For each one, you ask the AI how you could answer it, decide which approach to take, and check that the result makes sense.

**Data:** `supreme-court-opinions-by-author.jsonl.gz`, from Modules in Canvas. Work in a Jupyter notebook.

**What you do with it:** look at the data, see how the opinions are spread over time and how long they are, run a topic model, decide what the topics represent, and graph how a topic rises and falls across the century. This is **distant reading**: asking questions of thousands of texts at once by counting and modeling words, rather than reading them one by one.

**What you submit:** your notebook and an HTML copy of it.

## How to work

For every question below, do the same three things in your notebook.

1. **Ask the AI for a plan, not code.** Describe your file and your question, and ask: *what steps would I need, what tools (Python libraries) would I use for each step, and what choices will I have to make along the way?* Paste its answer into a markdown cell. Then edit it: cross out steps you do not need, and put a question mark by anything you do not understand and ask the AI to explain it.
2. **Run it one step at a time.** Ask for code for step 1, run it, look at the output, then move on. Do not ask for everything at once.
3. **Check and explain.** Does the result match something you can verify yourself? Write two or three sentences on what it shows and what it does *not* show.

**An example first prompt:**

```markdown
I have a compressed file called supreme-court-opinions-by-author.jsonl.gz that holds US Supreme
Court opinions. I'm working in a Jupyter notebook. I want to load it and find out how many opinions
there are per year. Don't write any code yet. What steps would I need, what Python libraries or
tools would I use for each step, and what choices will I have to make along the way?
```

You do not need to know the tools in advance. Asking which libraries the AI would use, and why, is how you find out what exists. Follow up with: *Are there other libraries that could do this? How do they differ?*

Asking "what choices will I have to make" gets the AI to show you the options (what counts as a "year", what to do with missing values) instead of silently picking for you.

**If the AI does something you do not recognize,** ask it what that line does and why it is needed. You are allowed to question its code.

## The questions

Work through these in order, since later ones build on earlier ones. Before each step runs, write one line saying what you expect to see.

### Part A: Know your data

Before you analyze any collection, find out what is in it. Ask the AI: *"Before I analyze this file, what should I find out about it, and how would I find it out, both before I load it and after?"* Then work through its checklist. Your file is a `.gz`, so start here:

- **Peek inside without loading it.** A `.gz` file is compressed, so a text editor shows nonsense, and the `.jsonl` inside holds one record per line. Ask the AI how you can read the first few lines of a compressed file without loading all of it. Ask for one method in the terminal and one in Python, and tell it your operating system. Write down what the first record looks like.
- **Load it, then look again.** Ask the AI how to load it and what to check afterward (its size, its fields, what type each one is, a few random records, anything missing).
- **Read a few opinions.** Print the beginning of three of them. What do you notice?

When you finish, write a short description of the dataset in your own words: what one record is, how many there are, what fields it has, which years it covers, and what you **cannot** tell from it.

### Part B: Ask questions of the data

**1. How are the opinions spread over time?** Make a chart of how many opinions there are per year (or per decade). Is the collection evenly spread? Why might that matter for anything you do later?

**2. How long are the opinions?** Make a histogram of opinion lengths. Does the typical length change over the century? Ask the AI what the different ways of measuring "length" are, and choose one.

**3. What topics run through the opinions?** Run a topic model and look at the top words for each topic. Ask the AI what a topic model needs from you, how to decide how many topics to ask for, and how to keep it from taking forever on a large collection.

**4. What does each topic represent?** Pick at least five topics and give each a short label. Check your label by reading the beginning of a few opinions that score high on that topic. Does the label hold up?

The textbook found one topic about **race and education** and another about **labor and unions**. Topic numbers depend on settings and a random seed, so yours will not match the book's. See whether your model has similar topics, and if not, why that might be.

**5. How does a topic's importance change over time?** Graph how much of the Court's writing is about one topic in each year or decade. Do it for two topics, such as race and education and labor and unions, or two others you find interesting. Ask the AI what the different ways are to define how "prevalent" a topic is in a given year, and compare two. Do they tell the same story? What happened in the world around any peaks?

**If you have time:** invent a seventh question of your own, or run the same questions on `old-bailey.csv.gz` (trial transcripts from London's central criminal court) and compare what you find.

## What to submit

**In your notebook, for each question:** your question, the steps the AI proposed (edited by you), the code and its output, and two or three sentences of your own about what it shows. Add a short **prompt log** near the top listing the prompts that mattered, and mark any where the AI was wrong, incomplete or misleading.

**Reflection (a markdown cell at the end, about 200 words):**

1. Where did asking the AI for options change what you decided to do?
2. Describe one time the AI's output looked fine but you had reason to doubt it. How did you check?
3. Pick one topic from your model. What would you need to read, beyond the model's output, before making a historical claim about it?

**Before you export:** restart the kernel and run all cells from the top so the notebook works in order. Avoid printing whole tables or long texts, which make the HTML huge. Then export the HTML (JupyterLab: *File, Save and Export Notebook As, HTML*; classic Notebook: *File, Download as, HTML*) and open it in a browser to check that your plots and text appear.

- [ ] `.ipynb` notebook
- [ ] `.html` copy
