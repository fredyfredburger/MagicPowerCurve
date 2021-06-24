# MagicPowerCurve
MSDS692 Data Science Practicum
Author: "Frederick Pletz"


# Introduction
This project analyzes Magic the Gathering (MtG) card data to identify the power curve for MtG chreatures.  Additionally, the creature types and keyword abilities are visualized to compare with the MtG color wheel.

# Files Included
FinalCreatureData.csv - csv containing cleaned creature data for all "simple" creatures over the last three decades of MtG cards.
Fred Pletz - Final Presentation.ppt - final presentation slides used in YouTube presentation.
LICENSE
PracticumFinal.Rmd - R mark down code for project
PracticumFinal.docx - R mark down generated word document

# Background
MtG is a trading card game where players cast cards that represent spells, summoning creatures or causing affects such as buffing creatures or removing all creatures from play.  From a game design perspective, MtG presents an extremely unique challenge since there are so many card interactions possible from the over 20,000 unique magic cards created since the game was first produced in 1993.  This project attempts to assess the power curve of magic cards to identify if there is a way to roughly calculate the cost of any given card - and therefore judge it's relative strenght in the game.

# Methods Used
For this project, I started by downloading the data from mtgjson.com and doing exploratory analysis in Excel.  Based on project timeline, I filtered to "simple" creature cards to allow time to complete the analysis.  The filtering reduced the dataset to roughly 10% of the overall cards, using creature cards with fixed power and toughness and non-keyword mechanics.  Cards that are illegal for turnament play and other special cards were also filtered out.  After filtering the data set, the columns were narrowed to those relavent for the specific data sicence application of calculating mana cost.  I added the date in hopes I would have time to calculate power curve changes over time, but unfortunately did not have time to complete that portion of the project.  I also added a new data column representing the non-colorless mana cost of any given card.  Colored mana has to be paid by the specific color, which can result in not having the correct mana color for a spell.  That means colorless mana cost would theoretically be "cheaper" than mana of a specific color in the mana cost.

For additinal exploritory analysis, I used Rapid Miner to run multiple algorithms against the data.  This provided a quick view of the expected end results of the project, providing a shortcut to ensure the project would provide useful results.

![image](https://user-images.githubusercontent.com/35434572/123181282-0a9b6280-d45b-11eb-8840-f6f3a0a8052b.png)
![image](https://user-images.githubusercontent.com/35434572/123181305-14bd6100-d45b-11eb-8dcc-9ba144f6d42d.png)

Finally, I loaded the data into R and used a general linear model and random forrest model to create predictive algorithms for determining the cost of a simple creature spell.  The 



High: 8
Actual: 88
Low: 589


# Future Research


# Conclusion




# Sources
MTGJSON (n.d.) Magic The Gathering cards in portable formats. Retrieved from: http://www.mtgjson.com/. 
