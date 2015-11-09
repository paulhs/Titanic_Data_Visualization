# Titanic_Data_Visualization
This repository is for Udacity Data Visualization and D3.js final project.

Summary
=======
The goal of this data visualization is to lead viewers looking into the Titanic disaster from the perspective of social level, gender and age.   I want to achieve this goal via a stacked histogram showing the survivor and deceased count per age group in Titanic disaster.  User interaction is deployed so the viewer can look at the visualization from a different perspective or even change the underlying data.  Animation is applied to make the visualization more dynamic.

Design
======
My original idea was to design a data visualization to present the Titanic tragedy showing the fatality rate in terms of social level, gender and age to the viewer.  To highlight the fatality count, the first option is the histogram per age group.  I also want to display both survivor and fatality count in order to show the ratio.  To achieve this, a grouped bar chart rather than a simple histogram is chosen.  In terms of hierarchy, the first level is age group, next level is survived / deceased, the last level can be either Passenger Class or Gender.

One of the feedbacks (see feedback 1) is that the visualization needs to demonstrate the survived/ deceased count distribution from both Pclass (passenger class) and Gender perspective.  A stacked bar chart can meet the requirement.  The HTML input form with radio buttons is used to switch between Pclass and Gender.

Another feedback (see feedback 2) I got is to allow viewer to explore how the Random Forest parameter n_estimators affects the survived count, a dataset with multiple n_estimators combination needs to be generated.  A mechanism for the viewer to choose different n_estimators value is necessary in design as well.  Based on another feedback (see feedback 3) , a slider is applied in the design for such purpose.  The dataset contains data for n_estimators values from 10 to 150 in increments of 10.  In this visualization implementation, values between 20 - 140 in increments of 10 were chosen.

For the visual encodings, d3.scale.category10() is used to generate colours for each stack.  In the dataset, the Pclass has only 3 different values while Gender has only two.  So the 10 colours generated from category10 are more than sufficient to cover all different stacks in the stacked bar chart.  A different way of encoding (Opacity level) is used to differentiate the survived vs deceased bars.  Lower opacity value was used for deceased count.  Visually, viewer can easily differentiate the survived vs deceased bar and not confused by too many colours.

The legends are added to enable viewer to easily identify the purpose of each bar section.  To match the colour encoding of the bars, the legends design also uses the same colour scheme. For the axes, lighter colour is chosen so as not to mix with the bar colour and confuse viewer.

The layout of the web page uses top-down approach – Heading, User input, then the chart.  For user interaction with the visualization, a group of two radio buttons and a d3 slider are located after the page heading.  The colours used for these user interaction mechanisms are light colours so the viewers main focus will be on the chart area.

The 'tooltip' user interaction is deployed in the design based on feedback 4.   To highlight the tooltip information, the colours used for the tooltip contents are dark background with bright text colours.  With the tooltip, the viewer can see the actual count number highlighted when the mouse hovers over the bar section.  The intention of this interaction mechanism is to guide the viewer when using and exploring the figures.

Animation is a big part of this design.  I want to show the stacked histogram from both Pclass and Gender perspective.  The design first shows the chart from Pclass perspective, then change it into Gender perspective in transition.  At the same time, transition is also applied on the opacity for the deceased bars so it can bring viewers attention to the difference.  Once the first transition is finished, whenever viewer switches the radio button or changes the n_estimators value on the slider, the chart will be updated in transition.  Changing the n_estimators will trigger the change of underlying data source for the chart.  These animations make this design a dynamic data visualization.

Feedback
========

During the project, I received the following feedback:

1.	It is a good idea to allow viewers to see how survived count distributed per two important features in the dataset – Pclass and Gender.  Switching between these two views can enable viewers to understand how the social and gender factor play a role in survival during this disaster.

2.	It is important to allow user to explore how the value of Random Forest parameter n_estimators affects the survived count.  This can demonstrate how a parameter for the Random Forest classifier model plays a role in the result distribution.

3.	Using slider rather than text box for setting the “ n_estimators” value gives better user interaction experience.

4.	Using the tooltip interaction to show exact count number for a section of a bar when viewer hover the mouse over it enables viewers to get deeper into the story and makes the visualization more user-friendly.

5.	Provide a prompt for user interaction after the animation stops.  This will ensure users know how to interact with the visualization.

Resources
=========

1.	Stacked Histogram	http://bl.ocks.org/sbrudz/8ac4f4102f787d0fcea5
2.	d3-slider	http://github.com/turban/d3.slider
3.	Using d3-tip to add tooltips to a d3 bar chart	http://bl.ocks.org/Caged/6476579
4.	W3schools.com HTML Tutorial   http://www.w3schools.com/html/default.asp
5.	W3schools.com javascript Tutorial   http://www.w3schools.com/js/default.asp
6.	W3schools.com CSS Tutorial   http://www.w3schools.com/css/default.asp
7.	Stacked-Bar-Chart  http://bl.ocks.org/mbostock/3886208
8.	Stacked-to-Grouped Bars  http://bl.ocks.org/mbostock/3943967
9.	Jerome  Cukier web site  http://www.jeromecukier.net/blog/2011/08/11/d3-scales-and-color/
