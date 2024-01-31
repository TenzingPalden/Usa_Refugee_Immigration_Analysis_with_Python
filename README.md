# USA Refugee Immigration Analysis

This project focuses on analyzing refugee immigration data from 2000 to 2021. The dataset used for analysis is sourced from the file "cleaned_data/refugee_byYear_byCountry.csv". The analysis includes cleaning the data, visualizing refugee immigration trends over the years, and mapping refugee immigration by country using Plotly's Choropleth Map.

## Data Cleaning

The initial dataset contains multiple types of placeholder text for null values, including "D", " - ", "-", "X", and " X ". These placeholder texts are replaced with NaN values using NumPy's NaN constant. Rows with NaN values are then dropped to clean the data. Additionally, commas are removed from the "amount" column, and the column is formatted as numeric for further analysis.

## Refugee Immigration Analysis

### Refugee Arrivals Over Time
The analysis begins by calculating the total number of refugees accepted by the USA each year from 2000 to 2021. The results are visualized using a line plot to demonstrate refugee immigration trends over the years.
```Python
#plotting refugee immigration by year
import matplotlib.pyplot as plt
plt.figure(figsize=(20, 5))
plt.plot(yearcount, "k")
plt.title('REFUGEE ARRIVALS FROM 2000 to 2021')
plt.xlabel('Year')
plt.ylabel('Refugee amount')
plt.xticks(yearcount.index)

plt.show()
```
<img src="https://github.com/TenzingPalden/Usa_Refugee_python_analysis/assets/85039775/7bdd88c1-0007-4f34-af5c-65ac0bb63239" width="1200"/>


### Top 20 Countries with Most Refugees
Next, the dataset is grouped by country to calculate the total number of refugees accepted by each country from 2000 to 2021. The top 20 countries with the most refugees are identified and visualized using a bar chart.

```Python
#plotting top 20 countries with most refugees from 2000-2021
plt.figure(figsize=(25, 5))
plt.xlabel("Amount of Refugees accepted")
plt.ylabel("Country")
plt.title("Top 20 countries with most refugees from 2000-2021")
plt.bar(refugee_total_by_country.index[:10],refugee_total_by_country.values[:10])
plt.show()
```

<img src="https://github.com/TenzingPalden/Usa_Refugee_python_analysis/assets/85039775/2cedf856-cae9-4451-969b-8b10608a4f21" width="1200"/>

## Choropleth Map

This was the bread and butter of the project. Very difficult to attain as it required me to find ISO codes of each country. The analysis extends to mapping refugee immigration by country using a Choropleth Map. The map is created using Plotly Express, with each country represented by its ISO_A3 code. The map is animated by year, allowing for a dynamic visualization of refugee immigration trends across different countries over the years.

<img src="https://github.com/notcardanoless/USA_refugee_analysis/blob/main/gif_USA_refugee.gif" width="900"/>

## Requirements
- The dataset used in this analysis is sourced from "cleaned_data/refugee_byYear_byCountry.csv".
- Additional geospatial data is sourced from the "geocountries/archive/countries.geojson" file for mapping purposes.
- pandas
- numpy
- seaborn
- matplotlib
- plotly

## Conclusion
In conclusion, the analysis of refugee immigration data from 2000 to 2021 provides valuable insights into the trends and patterns of refugee arrivals across different countries. This project helped me practice through data cleaning, visualization, and mapping techniques, and with them I have identified key aspects of refugee immigration, including trends over time and the top countries accepting refugees.

## Future thoughts
- In-depth Analysis: Conducting further analysis to understand the factors influencing refugee immigration trends, such as geopolitical events, conflicts, and humanitarian crises.
- Predictive Modeling: Exploring the possibility of building predictive models to forecast refugee immigration trends based on historical data and external factors.
