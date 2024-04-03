# Bike_share_analysis
## Data Understanding

This project utilizes a case study centered around a fictitious bike-share company, Cyclistic. The data employed for this analysis originates from the Google Data Analytics Course capstone project. While not reflecting a real-world company, the datasets provided (encompassing the years [2019](https://docs.google.com/spreadsheets/d/1uCTsHlZLm4L7-ueaSLwDg0ut3BP_V4mKDo2IMpaXrk4/template/preview?resourcekey=0-dQAUjAu2UUCsLEQQt20PDA#gid=1797029090), [2020](https://docs.google.com/spreadsheets/d/179QVLO_yu5BJEKFVZShsKag74ZaUYIF6FevLYzs3hRc/template/preview#gid=640449855)). The data has been made available by Motivate International Inc. under this [License](https://divvybikes.com/data-license-agreement) were meticulously crafted to closely resemble real-world bike-share operations.

## Business Task

During a recent stakeholder meeting, the Director of Marketing, Lily Monroe, and other key decision-makers discussed the company's growth strategy and how data analytics could contribute. Cyclistic, a bike-share company, caters to two customer segments: casual riders and annual members. Stakeholders hypothesize that converting casual riders to annual memberships will significantly increase profitability. As a result, Ms. Monroe has tasked me with this project, focusing on a central question: How does the usage pattern of annual members differ from casual riders when it comes to Cyclistic bikes?

## Data Preparing 

The datasets, originally in Google Sheets format, were downloaded as CSV files for further analysis. To gain an initial understanding of the data structure, I employed exploratory functions like colnames(), str(), and head() within RStudio (Posit). This revealed discrepancies in column names between the 2019 and 2020 datasets, although the overall data structure remained similar. To facilitate data manipulation, the 2019 data underwent column renaming to match the 2020 format. Additionally, irrelevant columns were strategically removed using targeted code to ensure they wouldn't impact the final results.

![1](https://github.com/alkheosa000/Bike_share_analysis/assets/162853772/a8d6a439-2969-4c0f-b1a1-92ba6bd6f4cb)

## Data Processing and cleaning
I started in this stage by inspecting the new table that has been created by using the following code.

![2](https://github.com/alkheosa000/Bike_share_analysis/assets/162853772/62995e1b-64a6-419e-b509-0188c529fd0b)

### Data inconsistencies were addressed through the following cleaning steps:

- **Member/Casual Rider Label Consolidation:** The "member_casual" column now uses consistent labels. "Subscriber" has been replaced with "member" and "Customer" with "casual," resulting in a two-category system (member/casual).
- **Date Granularity Enhancement:**  Additional date information has been incorporated. New columns for day, month, and year now enable data aggregation by these timeframes.
- **Ride Length Calculation:** A new "ride_length" field has been calculated and added to the entire dataset, ensuring consistency across all rides, including those in 2020Q1 that lacked the "tripduration" column.
- **Negative Trip Duration Removal:** Entries with negative trip durations, likely representing rides removed by Divvy for quality control, have been removed from the dataset to ensure data accuracy.

![3](https://github.com/alkheosa000/Bike_share_analysis/assets/162853772/e65cf2e7-d8dd-4c13-83c6-016285a69b33)


## Analysis
Following data cleaning, I conducted a descriptive analysis to gain insights into ride characteristics. This analysis explored:
- **Overall Ride Length Distribution:** Total ride lengths were examined to understand the general distribution of ride durations.
-	**Extreme Ride Durations:** The longest and shortest rides within the dataset were identified.
-	**Member vs. Casual Rider Comparison:** A comparative analysis was performed to reveal potential differences in ride patterns between members and casual riders.
-	**Weekly Ridership Trends:** Ridership data was analyzed by both rider type (member/casual) and week to uncover potential patterns or variations in ridership across the week.

![4](https://github.com/alkheosa000/Bike_share_analysis/assets/162853772/cbfb8d76-27fc-4f3a-ac43-e78c4fbd7bd6)


## Data Visualization in Tableau

Leveraging the insights gained from the descriptive analysis, I transitioned to the visualization stage. The prepared dataset, "all_trips_v2," was exported to Tableau to transform the numerical findings into an easily comprehensible narrative.

A two-worksheet dashboard was constructed to visually compare members and casual riders. The first worksheet presents total rides categorized by member type, while the second focuses on average ride length for each category.

[link to dashboard here](https://public.tableau.com/app/profile/osama.alkhedr/viz/Bike_Share_Analysis_17121714920540/Bike_share_Analysis)

![5](https://github.com/alkheosa000/Bike_share_analysis/assets/162853772/3e9522bd-33aa-4a40-90ed-d61a16abaa14)

## Results

The analysis of ride data revealed distinct usage patterns between members and casual riders.
-	**Ride Frequency:** Members demonstrate significantly higher ride frequency compared to casual riders. On average, members take approximately 50,000 rides per day, substantially exceeding the daily average of 3,500 rides for casual riders.
-	**Weekend Usage:** Interestingly, member ridership exhibits a decrease on weekends, suggesting that members primarily utilize the bikes for weekday commutes.
-	**Ride Length:** While members ride more frequently, casual riders seem to travel longer distances per trip. The average ride length for casual riders is around 5,000 meters, considerably higher than the members' average of 900 meters per ride.

## Recommendations 
### Focus on Weekday Commutes:

-	**Targeted Workplace Marketing Campaigns:** Partner with local businesses in areas with high concentrations of target audience (office workers). Offer presentations or lunch-and-learn sessions highlighting the benefits of cycling to work, including cost savings, health advantages, and environmental impact. Provide on-site registration options with special workplace discounts for annual memberships.
-	**Weekday Marketing Blitz:** Increase marketing efforts during weekdays, especially during peak commute times. Utilize platforms like local radio, bus stop advertisements, or digital signage near office buildings to showcase the convenience and time-saving benefits of cycling to work with your bike-share program.

### Membership Incentives:

-	**Limited-Time Annual Membership Discounts:** Offer limited-time discounts on annual memberships, specifically targeting casual riders who might be hesitant about the upfront cost. This could be a flat discount or a tiered discount based on the length of the membership purchased (e.g., deeper discount for a 2-year commitment).
-	**Employee Referral Programs:** Implement an employee referral program to incentivize existing members. Offer rewards (e.g., free ride credits, discounts on merchandise) to members who successfully refer colleagues to sign up for annual memberships.

