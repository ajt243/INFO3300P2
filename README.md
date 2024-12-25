Introduction
This report examines the distribution of fast food chain preferences and their correlation with obesity rates across the United States. It includes an analysis of obesity rates by sex and racial demographics, providing insights into dietary preferences and health effects across different populations at the state level. By exploring current fast food popularity and obesity statistics, we can better understand the relationship between fast food choices and obesity rates by state.

Data Description
This analysis uses multiple data sources to examine the relationship between fast food chain preferences and obesity rates across the United States. A TopoJSON file (us.json) provides geographic shapes for U.S. states, enabling state-level mapping of obesity and fast food data.

The first dataset, fast_food.csv, sourced from WorldPopulationReview.com, provides information on the most popular fast food chains in each state, ranked by search frequency. The other datasets, obesity_race.csv and obesity_sex.csv, include state-level obesity rates broken down by racial and sex demographics and are sourced from KFF.org.

Variables
The merged dataset consists of the following variables:

State: State name
First: The most popular fast food chain by search popularity
Second: The second most popular fast food chain by search popularity
Third: The third most popular fast food chain by search popularity
Obesity Rates by Race: “White,” “Black,” “Hispanic,” “Asian/Native Hawaiian or Pacific Islander,” “American Indian or Alaska Native,” and “Other”
Obesity Rates by Sex: “Male” and “Female”

Data Preprocessing and Criteria
To process the data, all datasets were loaded concurrently and stored in corresponding arrays. For fast_food.csv, the MostPopularFastFoodMostSearchedFor field was split by lines to isolate the top three chains in each state, removing ranking numbers and saving the values as first, second, and third. Unnecessary columns, such as MostPopularFastFoodBestIconicChain and MostPopularFastFoodFavoriteBreakfast, were removed to streamline the data. In the obesity_race.csv and obesity_sex.csv file, a general All column was removed to focus on specific racial breakdowns.

Each dataset was then converted into a map object, keyed by state, to facilitate merging by state name. The datasets were combined using the state key to create a comprehensive entry for each state, including fast food preferences, obesity rates by race, and obesity rates by sex. The TopoJSON file was processed to extract state shapes using topojson.feature() with the geoAlbersUsa projection, aligning the map’s dimensions for accurate state-level visualization.

Not all variables from the original datasets were used; instead, we focused on those most relevant to fast food preferences and obesity rates to enhance usability. Selection criteria prioritized variables essential for understanding the relationship between fast food choices and obesity trends by demographic group across states.

Visualization Design Rationale 
This interactive choropleth map visualizes fast food preferences and obesity rates across U.S. states. Each state is colored according to obesity rates, allowing users to explore potential correlations between fast food popularity and health trends. The design prioritizes clarity, interactivity, and an intuitive user experience.
Color Mapping for Obesity Rates: The choropleth map uses a blue gradient where darker shades represent higher obesity rates. This color scheme helps viewers quickly identify states with varying obesity levels, while the monochromatic palette ensures accessibility for colorblind users and keeps the map visually cohesive.


State-Specific Tooltips: Hovering over each state reveals a tooltip displaying the top fast food chain by search popularity, providing an instant snapshot of dominant food preferences. This interaction adds depth to the map without cluttering the main view, enabling easy comparison between states.


Legend and Labels:
Obesity Rate Legend: Positioned below the map, this legend provides clear reference points for the range of obesity rates, using high-contrast text and a straightforward layout to facilitate easy interpretation.
Fast Food Preferences Ranking: Each state’s top three fast food chains are shown in the side panel using gold, silver, and bronze icons to indicate their rank. This visual ranking system allows users to intuitively grasp food popularity without textual overload.


Mapping of Data to Visual Elements:
Position: Each state is mapped to its geographic position using the geoAlbersUsa projection, preserving familiar U.S. state shapes and ensuring spatial accuracy.
Color Intensity: Obesity rates are conveyed through color intensity, providing an immediate visual cue for areas with higher or lower rates.


Interactivity:
Hover Interaction: Hovering highlights the state and displays the top fast food chain in a tooltip, allowing users to explore food preferences quickly and intuitively.
Click Interaction for Detailed View: Clicking on a state opens a side panel with detailed obesity data broken down by gender and race. This drill-down feature keeps the main map clean while allowing users to access deeper insights.
Return to Main View: A back button in the side panel allows users to return to the main map view, maintaining a seamless and intuitive navigation flow.
The visualization is designed to be visually appealing and easy to interpret. Each interactive element serves to enhance user engagement, providing meaningful insights into regional fast food preferences and obesity trends without overwhelming the viewer.

Trade-offs and Additionally Design Decisions

Clarity vs. Detail in Data Presentation:
Trade-off: Displaying all data points could lead to visual overload, particularly with demographic breakdowns for obesity.
Decision: We chose to focus on key metrics—the top three fast food chains and demographic obesity rates by gender and race—ensuring clarity and usability without excessive detail.


Simplified Color Scheme:
Trade-off: A varied color scheme might have highlighted different data attributes but could distract viewers from the primary focus.
Decision: The blue gradient effectively represents obesity rates, maintaining a cohesive visual experience that avoids overwhelming users. This choice enhances readability and accessibility, particularly for users with color vision deficiencies.


Dynamic Tooltips vs. Static Labels:
Trade-off: Static labels on the map could increase visual clutter, especially in smaller states where text might overlap.
Decision: Tooltips appear on hover, reducing clutter while still providing information about fast food popularity. This dynamic approach keeps the map visually clean and allows users to access details on demand.


Gender and Race Obesity Data in Side Panel:
Trade-off: Showing detailed demographic data directly on the map could obscure primary information and complicate user interpretation.
Decision: We opted to display this data in a side panel upon clicking a state. This approach allows users to dive into specific demographics without distracting from the main obesity and fast food data.


Projection Choice:
Trade-off: Using a complex projection might have emphasized geographic nuances but would compromise the familiar layout.
Decision: The geoAlbersUsa projection keeps state shapes recognizable, balancing spatial accuracy with user familiarity for a U.S.-centered dataset.


Top Three Chains Focus:
Trade-off: Including all fast food chains could present a fuller picture but would complicate interpretation.
Decision: We limited the view to the top three chains in each state, emphasizing key preferences without overwhelming users. This focused approach highlights the most impactful data while maintaining simplicity.
By thoughtfully simplifying and prioritizing key elements, we have created an accessible and user-friendly presentation that effectively highlights regional fast food preferences and obesity trends. This approach enhances usability, guiding viewers to meaningful insights without overwhelming them with unnecessary detail.

Impact and Visual Story
This visualization provides a compelling narrative about the relationship between fast food popularity and obesity rates across different U.S. states. By presenting both dietary preferences and demographic health statistics, the map encourages viewers to explore how regional fast food choices may correlate with public health trends.
Insight into Regional Differences: The color-coded obesity rates allow users to quickly identify states with higher or lower rates, sparking questions about possible underlying factors, including cultural, socioeconomic, and dietary influences. Observing which fast food chains dominate in each state also provides a unique perspective on consumer behavior and regional preferences.


Health and Demographic Correlations: By enabling users to view obesity rates by race and gender upon clicking each state, the visualization offers a deeper understanding of how health outcomes vary across demographics. This breakdown invites reflection on potential health disparities, encouraging further inquiry into the social and environmental factors that influence public health.


Surprising Findings: Certain states exhibit unexpected patterns, such as popular fast food chains in areas with comparatively lower obesity rates, or demographic groups within a state showing significantly different obesity statistics. These patterns challenge assumptions and provoke questions about the complexity of health outcomes and lifestyle choices.


Intended Message: The visualization aims to emphasize the broader implications of fast food consumption on public health. By juxtaposing popular fast food chains with demographic obesity rates, it invites viewers to consider how dietary choices impact various communities. Ultimately, the goal is to foster a nuanced understanding of how cultural preferences and health intersect, inspiring discussions about public health, nutrition, and regional behaviors.
