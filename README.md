# MagicPowerCurve
MSDS692 Data Science Practicum
Author: "Frederick Pletz"
YouTube Presentation: https://youtu.be/-YGfAKSknOQ

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

Finally, I loaded the data into R and used a general linear model and random forrest model to create predictive algorithms for determining the cost of a simple creature spell.  The resulting General linear model had a decent success rate of aproximately 60% when rounding the decimal costs to the nearest integer for comparison to the actual integer spell costs.  The model had 151 results with higher predicted costs, and 181 with lower predicted costs, and 517 predicted accurately.  Using the heatmap visualization, it becomes clear that the majority of predictions were not far off from the calculated cost - with a few surprising outliers.

![image](https://user-images.githubusercontent.com/35434572/123184062-e478c100-d460-11eb-9151-a04d4f26f79c.png)

The Random Forest model showed an even better result, with fewer outliers:
![image](https://user-images.githubusercontent.com/35434572/123184126-0b36f780-d461-11eb-8b60-b079f24bde52.png)

Assessing the word clouds, it became almost comically obvious that there was selection bias in the data set, as all but two mana colors had "flying" as the number one keyword ability.  I think that this was primarily due to the reduction in scope to "simple" creatures, and a broader text analysis would likely result in a more accurate picture of each color's focus on the color wheel.  However, there were still interesting things brought out from the word clouds:

White, focus on humans, soldiers, knights, angels, and cats with abilites focusing on life gain, coordination, and combat advantage
![image](https://user-images.githubusercontent.com/35434572/123184367-8b5d5d00-d461-11eb-93da-71d900583003.png)
![image](https://user-images.githubusercontent.com/35434572/123184372-8ef0e400-d461-11eb-82e0-ceede6868c1c.png)

Blue, focus on sea creatures and elementals with defensive abilities and countering as a key focus
![image](https://user-images.githubusercontent.com/35434572/123184442-b47ded80-d461-11eb-9577-5395120efc77.png)
![image](https://user-images.githubusercontent.com/35434572/123184450-b778de00-d461-11eb-8fe7-c60dd6400f6a.png)

Black, a focus on undead and evil creatures with abiliteis to drain life and cause fear
![image](https://user-images.githubusercontent.com/35434572/123184600-04f54b00-d462-11eb-88fe-b71b3f99525f.png)
![image](https://user-images.githubusercontent.com/35434572/123184606-07f03b80-d462-11eb-8a34-214eae73499a.png)

Red, a focus on war-like mytical creatures and abilities that focus on fast tempo
![image](https://user-images.githubusercontent.com/35434572/123184662-20605600-d462-11eb-94ad-7233d6b0179e.png)
![image](https://user-images.githubusercontent.com/35434572/123184667-23f3dd00-d462-11eb-885c-6cef5a3d3006.png)

Greern, a focus on wild creatures and elves with abilitiesd that focus on countering other colors and overwhelming through superior strenght
![image](https://user-images.githubusercontent.com/35434572/123184752-4e459a80-d462-11eb-9493-fec6bedbbebe.png)
![image](https://user-images.githubusercontent.com/35434572/123184758-51d92180-d462-11eb-8f23-1288cac28d27.png)

Uncolored being made up entirely of artifacts with a lot of inanament creatures with no specific ability focus
![image](https://user-images.githubusercontent.com/35434572/123184842-88af3780-d462-11eb-904a-1acea6b07d56.png)
![image](https://user-images.githubusercontent.com/35434572/123184846-8c42be80-d462-11eb-9c2e-c3790b4b9343.png)

# Future Research
This research provided an initial view in the power curves of MtG.  The research would benefit greatly by expanding to all MtG cards.  This becomes difficult with the sheer number of unique abilities that are hard to quantify, so barring expanding to ALL cards, it would at least be good to see research that included more common non-keyword abilities.

# Conclusion

It is possible to map MtG spells to an aproximate cost, though due to the nature of the game, no calculation will ever be an exact value.  This research provides insight into the rough power curve of cards to show over and under-valued spells.


# Sources
MTGJSON (n.d.) Magic The Gathering cards in portable formats. Retrieved from: http://www.mtgjson.com/. 
