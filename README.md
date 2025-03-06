# Categorizing COP attendees with Gemini and visualizing using ai2html: [Story](https://annikamcginnis.github.io/cop-attendees/)

## Goal
- To understand attendance at the UN climate summit by occupation, affiliation and world region

## Main Findings
- The share of attendees from developing countries has increased steadily over the decades. From their lowest participation of just 27 percent of total attendees at COP3 in 1997, when the Kyoto Protocol was passed that first committed countries to reduce greenhouse gas emissions, Global South participation has risen to 75 percent in the most recent years.
- In recent years, fossil fuel companies have made up a larger percentage of the overall attendees at COP. The share of total conference attendees associated with fossil fuel companies was 0.4 percent in 2015, which rose to 1.4 percent in 2024. The total number of fossil fuel representatives attending the summit rose by over five times in the decade, to a high of 895 in 2023 from just 84 in 2015.
- The growth of fossil fuel participation at COP was unmatched by any other profession except other companies. At the same time, the share of total attendees associated with governments, international NGOs, intergovernmental organizations and scientific institutions have declined.
- Between 2015 and 2024, Europe and Central Asia remained the top region sending fossil fuel representatives to COP. But over the last decade, East Asia and Pacific moved into second place, led by the rise of Chinese oil and gas companies. More fossil fuel companies from Sub-Saharan Africa and the Middle East and North Africa have also gained representation at COP in recent years.
- Young people, a historically neglected group at the negotiations, have also increased their presence at COP, but not faster than fossil fuel companies. From 1.6 percent of total attendees in 2015, representatives of youth-focused organizations made up 3 percent in 2024. But looking at the total share of attendees at each conference, the percentage of attendees from youth-oriented organizations doubled over the decade, while fossil fuel representation more than tripled.


## Data Collection
I acquired a dataset of COP attendees scraped from attendance rosters from COP1 - COP29, produced by Daria Blinova et al.: [Data]([https://github.com/bagozzib/UNFCCC-Attendance-Data])


## Data Analysis
I used the following languages, libraries, APIs and models in my data cleaning and analysis: 
- Python
- Pandas
- R
- ggplot
- bart-large-mnli
- OpenAI
- Gemini
- ai2html
- Adobe Illustrator
- html, css & d3
- RawGraphs
- Datawrapper

I used the Gemini LLM through the OpenAI library to categorize all attendees by their affiliations, including fossil fuel companies, youth-oriented organizations, and other categories. My code took into account the attendee's name, affiliation, job title and other identifying information to make the classification and save it to a new column. I also used Gemini to determine the most likely country of origin for about half of the dataset's rows that lacked country information. 

I conducted my data analysis in Python using the Pandas library. I also used R to produce a few EDA ggplots. 

I produced several visualizations in Datawrapper and Rawgraphs and cleaned them up in Adobe Illustrator. I produced desktop, tablet and mobile versions for each graphic. I used ai2html to make them responsive. In my html story code, I also included a flexbox with two side-by-side graphs that stack on top of each other when the page becomes smaller. 


## Reflection

In this project, I learned how to refine my categorization using LLMs to improve accuracy. First, I tried zero-shot classification to categorize COP attendees by their occupations (using the Job_Title column). To do this, I took a sample of the dataset to generate my initial categories that I then used in this classification with the bart-larg-mnli model. However, upon completion and review of the data, I realized much of the classifications were inaccurate because of relying on only the job title column to make the classification. This is when I pivoted to categorizing using Gemini, where I could write code that took into account several columns with identifying information and affiliations for the COP attendees to make a classification. When I reviewed samples of the output for this script, it was much more accurate. 

This project also introduced me to ai2html, Adobe Illustrator and responsive design. While I succeeded in using the flexbox, I want to understand how to refine my code so that the two side-by-side graphs become smaller in a more responsive way. I also initially attempted to make an ai2html scrollytelling page where annotations would appear one by one, but I only succeeded in making their paths appear in the scrollama steps (file uploaded in this repo). A future goal is to troubleshoot my scrollama code to make the first visualization scrolly.

 
