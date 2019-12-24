# Kaggle NFL Injuries Challenge
### Elijah Hall
### Started: 11/27/2019

## Description
In this challenge, you're tasked to investigate the relationship between the playing surface and the injury and performance of National Football League (NFL) athletes and to examine factors that may contribute to lower extremity injuries.

You'll also notice there isn't a leaderboard, and you are not required to develop a predictive model. This isn't a traditional supervised Kaggle machine learning competition. For more information on this challenge format, see this forum thread. This challenge is part of NFL 1st & Future, the NFL’s annual Super Bowl competition designed to spur innovation in player health, safety and performance.

## The Challenge
In the NFL, 12 stadiums have fields with synthetic turf. Recent investigations of lower limb injuries among football athletes have indicated significantly higher injury rates on synthetic turf compared with natural turf (Mack et al., 2018; Loughran et al., 2019). In conjunction with the epidemiologic investigations, biomechanical studies of football cleat-surface interactions have shown that synthetic turf surfaces do not release cleats as readily as natural turf and may contribute to the incidence of non-contact lower limb injuries (Kent et al., 2015). Given these differences in cleat-turf interactions, it has yet to be determined whether **player movement patterns and other measures of player performance differ across playing surfaces** and **how these may contribute to the incidence of lower limb injury**.

Now, the NFL is challenging Kagglers to help them **examine the effects that playing on synthetic turf versus natural turf can have on player movements and the factors that may contribute to lower extremity injuries**. NFL player tracking, also known as Next Gen Stats, is the capture of real time location data, speed and acceleration for every player, every play on every inch of the field. As part of this challenge, the NFL has provided full player tracking of on-field position for **250 players over two regular season schedules**. One hundred of the athletes in the study data set sustained one or more injuries during the study period that were identified as a **non-contact injury** of a type that may have turf interaction as a contributing factor to injury. The remaining 150 athletes serve as a representative sample of the larger NFL population that did not sustain a non-contact lower-limb injury during the study period. Details of the surface type and environmental parameters that may influence performance and outcome are also provided.

Your challenge is to **characterize any differences in player movement between the playing surfaces** and **identify specific scenarios (e.g., field surface, weather, position, play type, etc.) that interact with player movement to present an elevated risk of injury**. More details on the entry criteria are available in Evaluation Tab.

## About The NFL
The National Football League is America's most popular sports league, comprised of 32 franchises that compete each year to win the Super Bowl, the world's biggest annual sporting event. Founded in 1920, the NFL developed the model for the successful modern sports league, including national and international distribution, extensive revenue sharing, competitive excellence, and strong franchises across the country.

The NFL is committed to advancing progress in the diagnosis, prevention and treatment of sports-related injuries. The NFL's ongoing health and safety efforts include support for independent medical research and engineering advancements and a commitment to work to better protect players and make the game safer, including enhancements to medical protocols and improvements to how our game is taught and played.

As more is learned, the league evaluates and changes rules to evolve the game and try to improve protections for players. Since 2002 alone, the NFL has made 50 rules changes intended to eliminate potentially dangerous tactics and reduce the risk of injuries.

For more information about the NFL's health and safety efforts, please visit www.PlaySmartPlaySafe.com

## Evaluation

Your challenge is to characterize any differences in player movement between the playing surfaces and to identify specific variables (e.g., field surface, weather, position, play type, etc.) that may influence player movement and the risk of injury. A valid submission will include:
* Summary Slides: A summary of your findings delivered as either a PDF or PPT file.
* Notebook Analysis: At least one notebook containing the analysis to support your proposal. All notebooks submitted must be made public on or before the submission deadline to be eligible. If submitting as a team, all team members must be listed as collaborators on all notebooks submitted.

Submissions will be judged by the NFL based on how well they address:

**Representation of player movement, including, but not limited to, the development of novel metrics that characterize player movement on the field:**

* Speed
* Directional changes
* Acceleration/Deceleration
* Distance

**Identification of specific variables that present an elevated risk of injury:**

* Are there specific movement patterns that correlate with the acute onset of injury (in general or by specific injury location)?
* Are there summary metrics of player movement which influence risk of injury?
* How do playing surface, game scenario, player movement, and weather interact to influence the risk of injury?

**Evaluation of differences in player movement between playing surfaces:**

* For any metrics of player movement shown to influence risk of injury, do differences in these metrics exist across playing surfaces for the non-injured player population?
* Do any of the environmental or game scenario variables influence player movement in the non-injured player population?

### Submissions will be scored using the following rubric:

1) Creativity and Presentation (5 points)

* Did the authors develop a creative or novel approach to characterizing player movement patterns?
* Did the authors make effective use of data visualizations to communicate their findings?
* Are the important results easily understood by the average person?

2) Methodology (5 points)

* Does the author document their methodology appropriately?
* Are the statistical and modeling methods used appropriate for the situation?
* Do the authors appropriately document the performance of their injury risk models?

3) Application (5 points)

* Are the characterizations of player movement patterns useful for comparison and injury risk assessment?
* Do the authors provide insights that would be useful for reducing the incidence of injury in the NFL?

## Timeline
* Start date: November 25th
* Final submission deadline: Jan. 2nd
* Winners announced: Jan 14th

***All dates are 11:59PM UTC***

Please note that all notebooks and submissions are evaluated after the deadline.

### Submission Instructions
You can make as many submissions as you like, but we will only consider your latest submission before the deadline of January 2nd.

If you are submitting as a team, you do NOT need to merge within the Kaggle platform (it's actually disabled), but all team members must be listed as collaborators on the submitted Notebook, and all team members must accept the competition rules before the submission deadline

A valid submission will include:

* Summary Slides: A summary of the proposed rule change presented in slide format and delivered as either a PDF or PPT file.
* Notebook Analysis: At least one notebook containing the analysis to support your proposal. All notebooks submitted must be made public on or before the submission deadline to be eligible. If submitting as a team, all team members must be listed as collaborators on all notebooks submitted.

## The Data

### Introduction
This page describes the datasets and variables provided to examine the effects that playing on synthetic turf versus natural turf can have on player movements and the factors that may contribute to lower extremity injuries. The data provided for analysis are 250 complete player in-game histories from two subsequent NFL regular seasons. Three different files in .csv format are provided, documenting injuries, player-plays, and player movement during plays. This manual describes the specifics of each variable contained within the datasets as well as guidelines on the best approach to processing the information.

### Data Files
There are three files provided in the dataset, as described below:
* **Injury Record**: The injury record file in .csv format contains information on 105 lower-limb injuries that occurred during regular season games over the two seasons. Injuries can be linked to specific records in a player history using the PlayerKey, GameID, and PlayKey fields.
* **Play List**: – The play list file contains the details for the 267,005 player-plays that make up the dataset. Each play is indexed by PlayerKey, GameID, and PlayKey fields. Details about the game and play include the player’s assigned roster position, stadium type, field type, weather, play type, position for the play, and position group.
* **Player Track Data**: player level data that describes the location, orientation, speed, and direction of each player during a play recorded at 10 Hz (i.e. 10 observations recorded per second).
<img src="Documents/nfl-playing-surface-analytics/documentation images/table1.png" width="1000">

### Field and Key Definitions
The following provides a description of each field contained within the datasets and their corresponding formats and descriptions. **Key Variables** are designated in bold.

### Injury Data File
<img src="Documents/nfl-playing-surface-analytics/documentation images/table2.png" width="1000">

Note that there is not a PlayKey available for every injury. This indicates that the game in which the injury occurred is known, but the specific play in which the injury occurred was not noted at the time of injury.
* 102 Games
* PlayKey 27% null
* injury 46% knee and 40% ankle
* feild type 54% synthetic and 46% natural
* Days Missed More than (DM_M) used as OHE variable, i.e. DM_M1, DM_M7 etc...
    * Can be converted to ordinal i.e. 
        * DM_M1 = 1
        * DM_M7 = 2
        * DM_M28 = 5
        * DM_M42 = 7
        
### Play List
The play file contains information about each player-play in the dataset, to include the player’s assigned roster position, stadium type, field type, weather, play type, position for the play, and position group
<img src="Documents/nfl-playing-surface-analytics/documentation images/table3.png" width="1000">

*Important Note: The GameID field is a unique identifier of player games but does not strictly reflect the order in which the games were played. The PlayerDay is an integer sequence that provides an accurate timeline for player game participation. In order to generate an accurate timeline of an individual player’s game participation, the PlayerDay variable should be used. The interval between days in the PlayerDay field for an individual player accurately reflects the interval in days between that player’s participation in games. Every player has a PlayerDay = 1 (note that this date is not the same for all players). Some players may have negative values for PlayerDay, which simply indicates participation in a game that occurred before their individually assigned PlayerDay = 1.

### Player Track Data
The player track file in .csv format includes player position, direction, and orientation data for each player during the entire course of the play collected using the Next Gen Stats (NGS) system. This data is indexed by PlayKey (which includes information about the player and game), with the time variable providing a temporal index within an individual play.

When processing the player track data, it is recommended to calculate velocity using the x, y position data and use those calculated velocities for any analysis (although we have provided the speed variable reported by the NGS system). The origin for the x and y coordinates is defined as the corner of the home endzone and home sideline (see Figure 1). The angles defined by orientation and direction are referenced from the y-axis of the coordinate system.
<img src="Documents/nfl-playing-surface-analytics/documentation images/table4.png" width="1000">
<img src="Documents/nfl-playing-surface-analytics/documentation images/coordinate_diagram.png" width="1000">

* Time is in hundreth of seconds
* Event timeline is 98% null and labeled when the new event occures, i.e. huddle, lineset, snap, pass...etc

## My Hypothesis'
Areas of interest:

1) "player movement patterns and other measures of player performance differ across playing surfaces and how these may contribute to the incidence of lower limb injury."

2) "examine the effects that playing on synthetic turf versus natural turf can have on player movements and the factors that may contribute to lower extremity injuries"

3) "characterize any differences in player movement between the playing surfaces and identify specific scenarios (e.g., field surface, weather, position, play type, etc.) that interact with player movement to present an elevated risk of injury"


* **H01**: Player movement patterns are different on natural fields than synthetic.
* **H02**: Player movement patterns impact risk of injury.

## Investigation Questions
* What factors best explain injuries?
* What are the key differences in the movements between field types?


# Conclusion EDA:

* Synthetic Fields are both indoor and outdoors. All Natural are outdoors, some with retractable roofs.

* The potential for injury arises when a player plays in a game on either a Natural or Synthetic field. Each of these events are aggregated and we see **3311** observations of players playing in a game on Natural fields and **2401** observations of players playing on Synthetic Fields.
* Natrual Injury Base Rate = **1.45%**
* Synthetic Injury Base Rate = **2.33%**
* The majority of injuries happen outdoors when it is cloudy, likely causing more humidity which might have more of an impact to injuries on synthetic v natural turf.
* Indoor Injury Base Rate = **2.43%**
* Outdoor Injury Base Rate = **1.64%**
* The potential for injury arises when a player plays in a game on either Indoors or Outdoors. Each of these events are aggregated and we see **4061** observations of players playing in a game on Outdoors and **1296** observations of players playing indoor, with only **355**, about 7%, unkown observations.

* Injury severity of ankle is either <2 or >4 making it either a minor or sevier injury. An additional question might be, is there a tendency for more sevier injuries on synthetic v natural?

**Injury length of time inactive by type**:
Mode/Mean
* Ankel: 0/2.07
* Foot: 6/5.43
* Heel: 1/1
* Knee: 1/2.31
* Toes: 1/1.14

Weather is not a well defined categorical variable and needs converting. Set categories are:
* Sunny
* Cloudy
* Rain
* Clear
* Indoor
* Unkown

Stadium Types can be aggregated to three main types:
* Indoors
* Outdoors
* Unknown

## Conclusion of H01

<img src="Documents/nfl-playing-surface-analytics/documentation images/nfl_injury_paths.png" width="250">

There is no visible difference between types of movements. For this we look at two metrics 

* The distance between the first and last position over the total distance traveled for each play. This will give us an indication of more straight line movements vs zigzag runs. **my_met**
    * my_met: mean= 0.315 stdv= 0.163
    * my_met_nat: mean= 0.286 stdv= 0.142 size= 36.000
    * my_met_syn: mean= 0.340 stdv= 0.176 size= 40.000
    * Students T-Test Results:
        * Statistics=-1.445, p=0.153, **Same distributions (fail to reject H0)**
    * Boostrap replicates :
        * With a p-value = 0.9327, and an emperical difference of means of -0.0541, there is some evidence to suggest that we should reject the null hypothesis that movements on synthetic and natural, represented by the os_met is, come from the same distribution. However, at a 95% confidence interval = [-0.07122638  0.07162312], or alpha = .05, there is **not significant evidence to reject the null hypothesis**.

* An other indicaion might be direction changes. The average number of direction changes per play between field types. This will indicate more extreme movements vs mild, **diff_os**. Then counting the **diff_os** values that exceed a certain value we can determine the number of extreme turns or positional changes that were made. **os_met**
    * os_met: mean= 2.684 stdv= 3.853
    * os_met_nat: mean= 1.917 stdv= 2.586 size= 36.000
    * os_met_syn: mean= 3.375 stdv= 4.603 size= 40.000
    * Students T-Test Results:
        * Statistics=-1.655, p=0.102, **Same distributions (fail to reject H0)**
    * Permutation Replicates difference of means test:
        * With a p-value = 0.954 and an empirical difference of means of -1.4583, there is some evidence to suggest that we should reject the null hypothesis that movements on synthetic and natural, represented by the os_met is, come from the same distribution. However, at a 95% confidence interval = [-1.69729167  1.57777778], or alpha = .05, there is **not significant evidence to reject the null hypothesis**.

### Look at non injured players 

Check engineered features to try to answer if players movements are different between injured and non injured players. This is a random sample ignoring position. We might need a stratified sample of players from similar positions.

    * With a p-value = 0.0127, there is significant evidence to reject the null hypothesis that the feature os_met for both groups injured and non injured come from the same distribution.
    * With a p-value = 0.0031, there is significant evidence to reject the null hypothesis that the feature my_met for both groups injured and non injured come from the same distribution.
