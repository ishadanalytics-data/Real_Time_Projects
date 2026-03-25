# Belgium Airbnb Data Analysis

## Project Overview
This project aims to perform a comprehensive data analysis on the `belgium.csv` dataset, which contains Airbnb listing information for Belgium. The purpose is to understand the dataset's structure, identify trends, explore relationships between various features, and extract actionable insights for potential hosts, guests, or market analysts.

## Data Description
The dataset `belgium.csv` provides detailed information about Airbnb listings in Belgium. It includes a wide array of features such as:
*   **Listing Details**: ID, listing URL, name, summary, description, property type, room type, number of accommodations, bathrooms, bedrooms, beds, price, weekly/monthly prices, security deposit, cleaning fee, minimum/maximum nights.
*   **Host Information**: Host ID, host name, host since, host location, host response time/rate, host listings count.
*   **Review Scores**: Review scores for accuracy, cleanliness, check-in, communication, location, value, and overall rating, along with the number of reviews and reviews per month.
*   **Location Data**: Street, neighbourhood, city, state, zip code, market, country, latitude, longitude, geolocation.
*   **Other Features**: Amenities, cancellation policy, calendar updated status, availability for various periods, and features provided by the host.

## Key Findings
### Data Preparation and Cleaning
*   Initial inspection revealed several columns with a very high percentage of missing values (e.g., 'Host Acceptance Rate', 'Has Availability', 'Jurisdiction Names', 'License', 'Square Feet'). These columns were dropped to improve data quality.
*   Price-related columns ('Price', 'Weekly Price', 'Monthly Price', 'Security Deposit', 'Cleaning Fee', 'Extra People') were cleaned by removing currency symbols and commas, and then converted to numeric types for accurate calculations.
*   Missing values in critical numerical columns such as 'Host Response Rate', 'Review Scores' (all categories), 'Reviews per Month', 'Bathrooms', 'Bedrooms', 'Beds', 'Price', 'Host Listings Count', and 'Host Total Listings Count' were imputed using their respective median values to maintain data integrity for analysis.
*   Datetime columns like 'Last Scraped' and 'Host Since' were converted to appropriate datetime objects for temporal analysis.

### Exploratory Data Analysis (EDA)
*   **Price Distribution**: The 'Price' distribution was skewed to the right, indicating that most listings are affordably priced, with a few high-priced outliers. Box plots confirmed the presence of these outliers.
*   **Review Scores Rating**: 'Review Scores Rating' showed a distribution heavily skewed towards higher scores, suggesting a generally high satisfaction level among guests.
*   **Room Type vs. Price**: "Entire home/apt" listings generally have the highest average prices, followed by "Private room", and then "Shared room", indicating distinct pricing tiers based on accommodation type.
*   **Property Type vs. Price**: 'Apartment' is the most common property type, but 'House' and other unique property types also contribute significantly to the listing count. Average prices vary considerably across different property types.
*   **Geographical Distribution**: The `City` analysis revealed a concentration of listings and varying average prices across different cities, with some cities exhibiting higher average prices.

### Aggregation Insights
*   **Room Type Aggregation**: "Entire home/apt" commands the highest average price and represents the largest segment of listings. "Private room" has the highest average review score, suggesting guests find good value and experience.
*   **Multi-level Grouping (Property Type & City)**: Granular analysis showed significant variation in total listings and average prices for different property types within specific cities, highlighting localized market dynamics.
*   **Top Hosts**: A few hosts manage a substantial number of listings, indicating professional host operations or property management companies playing a significant role in the Belgian Airbnb market.

## Next Steps
*   **Advanced Feature Engineering**: Create new features from existing ones, such as 'host experience duration' from 'Host Since' or 'price per person' based on 'Accommodates'.
*   **Geospatial Analysis**: Utilize latitude and longitude to visualize listing density, average prices, and review scores on a map to identify high-value areas or potential gaps in the market.
*   **Predictive Modeling**: Build a regression model to predict listing prices based on various features, which could help new hosts price their listings competitively or identify undervalued properties.
*   **Sentiment Analysis**: If review text data were available, perform sentiment analysis to understand qualitative aspects of guest feedback.
*   **Time-Series Analysis**: Analyze trends over time using the 'Last Scraped' and 'Host Since' dates to observe changes in listing availability, pricing, or host activity.

