# 081_Star_Wars_Andor_NetVis  
In the past few days, I completed an exciting hobby project where I built the character network of the Star Wars Andor series using Python and Gephi. (covering the episodes from seasons 1 and 2 so far)
📊 The goal of the project was to showcase how raw text data can be transformed into structured network data and then visualized.

The workflow steps were as follows:

1️⃣ Preparing the subtitle texts
In the first step, I combined the episode scripts of the series into a single text file. This created the raw data foundation for further processing.

2️⃣ Extracting the character list (web scraping)
I obtained the full cast of the series from IMDb using the BeautifulSoup and requests libraries. This structured list, which I eventually narrowed down to 60 characters, was essential for accurate character identification.

3️⃣ Normalizing character names
Based on the character list generated from web scraping, I created name variations, nicknames, and alternative spellings to reliably link the names appearing in the text to the correct characters.

4️⃣ Building the network
By analyzing the subtitle text, I generated edges and nodes: when two characters appear in the same scene or part, a connection is created between them. The frequency of these edges already hints at the strength of the relationship.
I wrote Python code that scans the movie script for strings from the character list → from this, it creates 1. a 'nodes' CSV file with the characters’ names and total mention count, which gives the node weight, and 2. an 'edges' CSV file with the character interactions. I applied a sliding window technique here: if two character names appear within 5 sentences, it counts as an interaction between them — of course, this isn’t perfect but delivers ~95% accurate results.
The 'edges' file has three columns: source character, target character, and weight, which is determined by the number of interactions.

5️⃣ Network visualization in Gephi
I imported the processed data into Gephi, where the visualization took place.
