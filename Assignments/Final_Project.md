# Final Research Project

The major culminating assignment for this course is a research project in which you find or create a dataset that allows you to investigate some sort of historical topic (broadly defined). You will use Python to process and analyze the data in order to present an argument, interpretation, or narrative based on that analysis. You will complete your project as a Jupyter Notebook that combines your code, your visualizations, and your analysis. You are free to choose any topic or dataset that you want, with approval, but it must be historical in nature.

## Finer Points

1. The project must be history focused. You could return to John Arnold for a discussion of what history is.

    1. Two potential tests to assess if your project is historical, if it is presenting a **historical** argument or just a statistical finding:

        1. The "So What?" Test – is your output an argument or a finding? "Forced enslaved migration in the US peaked in the 1830s" is a finding. Explaining why that occurred and/or why it matters is an argument. History explains what is happening around the numbers.

        2. The "Disagreement" Test – Could a reasonable person/historian offer a counterargument to your narrative based on your data and/or different data?

2. You are free to use AI as a coding assistant, or not. You choose! You can also choose to learn to write the code on your own, free from the assistance and use of AI. There are lots of tutorials out there (see [The Programming Historian](http://programminghistorian.org) for examples) I would ask that you declare your intention in your proposal AND in your final project (you can change your mind).

3. Do not use AI to **generate** ideas about your data. The goal is for you to make arguments of your own based on the manipulation and presentation of data. Don't feed your data to an AI and ask it to find patterns, don't give over your thinking to a machine.

## Research Steps and Due Dates

| Steps            | Due Dates                                                 |
|------------------|-----------------------------------------------------------|
| Initial Thoughts | Monday Nov 9, 5pm                                         |
| Proposal         | Monday Nov 16, 5pm                                        |
| Full Draft       | Wednesday, Dec 9, 5pm                                     |
| Presentation     | Tuesday Dec 8 or Thursday Dec 10 (in-class, random order) |
| Peer Review      | Friday Dec 12, 5pm                                        |
| Final Draft      | Wednesday Dec 16, 5pm                                     |

## Initial Thoughts on Research Proposal

Here are the questions we need to answer in identifying a meaningful data-driven historical research project:

1. Is there a particular historical question you would like to answer with data? If yes, then we can start to search for a dataset that might allow you to do so.

2. Is there a particular dataset that you would like to base your project on? Is that dataset available or do you need to create it?

3. Is there a particular Digital History approach that you would like to explore?

4. Do you intend to use AI Assisted coding, or to learn to write the code yourself? (You can change your mind)

### Choosing Your Approach

For your final project, choose at least **one** of the five approaches below. In each case you can use AI-assisted coding in Python, or learn to write the code yourself. Either way you are responsible for checking that the code and its results are correct and for explaining your choices.

#### 1. Visualization and Statistical Analysis

Use a historical dataset to identify, describe, and test patterns over time or across groups. You might chart change over time, compare categories, or use basic statistics (correlation, regression, significance tests) to ask whether an apparent pattern is meaningful.

Visualization does not have to mean bar charts, line graphs, and scatterplots. Think of the compelling work we've discussed (Naylor and Klein) that moves away from conventional visualizations to surface and perhaps restore the human presence hidden in the data. You're welcome, but **aren't required**, to experiment with form: What would it mean to show each person, family, or household rather than an aggregate? What does a conventional chart hide, and what might a different design reveal?

Your project should combine clear visualizations with an argument about what they show and what they cannot show.

#### 2. Digital Mapping and Spatial Analysis

Use geographic information to ask a historical question. You might plot events, people, or institutions on a map, show change across space and time, or analyze spatial relationships such as clustering, distance, or access. Your map should do analytical work, not just illustrate, and you should discuss how historical place names, boundaries, and missing data shape what the map can claim. Huge examples we've discussed this semester are [Mapping Inequality](https://dsl.richmond.edu/panorama/redlining/) and [The Forced Migration of Enslaved Peoples in the United States, 1810-1860](https://dsl.richmond.edu/panorama/forcedmigration/).

#### 3. Text Analysis and Distant Reading

Analyze a large body of text (newspapers, speeches, letters, books) using computational methods such as word frequency, topic modeling, named entity recognition, sentiment analysis, or comparison across time periods or authors. Your goal is to find patterns no single reader could see, then return to individual passages to test and interpret them. The Immerwahr article "Burning Down the House" is an example (there are other listed on the [Advanced DH Projects](https://proctorf.github.io/HIST280DataAndHistory/Readings/CodingWork/AdvancedDHExamples.html) page).

#### 4. Network Analysis

Model a set of historical relationships as a network: people who corresponded, organizations that shared members, places linked by trade or travel. Calculate and visualize measures such as centrality, betweenness, and clustering, and use them to ask who or what was influential, connected, or isolated. You should also address what the network leaves out and how your choices about what counts as a "connection" affect the results. My paper or [Tudor Networks](http://tudornetworks.net) are examples.

#### 5. Dataset Creation and Curation

Build a small, computer-readable dataset from historical sources. You may (a) extract structured information (names, dates, places, amounts) from a set of primary sources you select, using OCR or AI-assisted methods, or (b) substantially enhance an existing dataset by adding new information, such as geocoding, disambiguating people, or coding new variables. You must verify your data against the original sources and document what you included and excluded, how you resolved ambiguities, and where the AI made errors as part of your Data Biography. Your dataset should be accompanied by a brief analysis demonstrating what it makes possible. You might look at [Freedom On the Move](http://freedomonthemove.org) – a repository of encoded newspaper ads for enslaved fugitives.

## Research Proposal

Submit a research proposal via Canvas that addresses the following questions:

- Name
- Tentative title for your project
- What are the historical questions you hope to answer? What is your topic?
- Description of Dataset: What kind of information does it contain? Are you going to be creating it or is it already in a machine-readable format? How are you going to access it?
- Ideas for Analysis: What research questions do you want to answer and how do you hope to use this data to do so?
- What digital approach(es) do you hope to employ?
- Do you plan to rely on AI Assisted coding?

## Research Project Draft

Your full research project will take the form of a Jupyter Notebook containing written analysis, code, and your visualizations, all rendered on a page or set of pages housed on your portfolio website. You should include (in no particular order):

- Title, Author, and Date
- Generative AI Disclaimer – be explicit about how you used AI to complete your project
- Introduction – Identify the questions you are seeking to answer and establish the context that your reader will need to understand the data. This section must include references to existing scholarship or research on the topic.
- Data Biography (look back to Klein and D'Ignazio if you have questions) – discuss how the data was collected and processed, by whom, and for what purposes? Explore any shortcomings you can identify with the data (for example, many people criticize slavevoyages.org because it "buries" the individual histories of the victims of the Slave Trade by presenting aggregatable data). Can you identify any questions that the dataset cannot address?
- Main Analysis – present a clearly communicated historical argument, interpretation, or narrative supported by compelling evidence and examples and appropriate visualizations of your dataset. You should indicate how you verified your code and its outputs (don't trust it to be correct).
    - **Make sure** that each visualization you create/present meets the standards established by Nathan Yau in *Data Points: Visualization that Mean Something.*
    - **Provide** examples of your prompts to an AI to produce your code, if you used AI.
- Conclusion
- Link to the project's Github Repository
- Bibliography: A list of the existing scholarship on your topic and a citation of your data source.
    - NOTE: At a bare minimum, please identify five interpretive secondary sources (academic journal articles, book chapters, long-form journalism, web-based analytical analyses of data and/or a historical question). Your work should be in conversation with these scholars, journalists, and thinkers.

## Presentation of Research Project Draft

During the last week of classes you will give a **5-7 minute presentation** to our class that walks through your dataset and your major analytical findings. Treat this as both an opportunity to share what you've accomplished and a chance to receive feedback on your project. DO NOT try to cover everything. Rather give a high-level introduction (think about the best of the Project Review Presentations from earlier in the semester).

The presentation order will be RANDOM. I will use a random number generator to create an order, that I will share with you in-class on Tuesday.

I will provide short, substantive feedback on the state of the project to assist in your continuing work on completing it.

## Peer Review of Research Project Draft

You will be randomly assigned one of your classmates' projects to review in more depth. As part of that review, you will read their project analysis and provide qualitative feedback to assist in completing the project.

More to follow on the specifics of the peer review.

## Research Project (Final)

This will be the complete project described above. I will be assessing the final version of your project not only on its overall quality, but also on the quality of your revisions and how you considered feedback from your peers and your professor (me). In the spirit of learning, I want to see you learning here.

A Strong Project will include:

- Well commented, explained, and functional blocks of code
- Examples of your AI prompts
- Multiple Visualizations
- Other visuals, if appropriate (cite correctly here)
- A minimum of 1500 words of text [not including your code and commentary in your code blocks]
- A minimum of five (5) argument-based interpretations (scholarly, journalistic, or interpretive websites) that allow you to construct a conversation to engage with your research (think about how Rosenthal and Naylor use similar data very differently to make different arguments about enslavement)
