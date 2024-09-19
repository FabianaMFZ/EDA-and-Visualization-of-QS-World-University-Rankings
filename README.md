# Academic Performance vs. Social, Economical and Educational Indicators

This README accompanies a data analysis project utilizing Python and Tableau to explore the relationship between universities, economic development, and social indicators. The analysis includes various datasets and visualizations to support the findings presented. This analysis aims to provide a comprehensive understanding of the factors contributing to the development of top universities and their impact on economic and social development. For the purposes of this project the rankings were filtered to display only universities at the top 500 positions.

## Instructions
1.	Python Analysis: The Python scripts used for data cleaning, analysis, and visualization are included in the jupyter notebook. Execute these scripts to reproduce the analysis.
2.	Tableau Dashboards: The Tableau dashboards provide interactive visualizations of the data. Open the .twb files in Tableau to explore the visualizations.

### Requirements
- Python 3
- Tableau Desktop or Tableau Public 
- Libraries: pandas, numpy, matplotlib, seaborn, statsmodel

### How to Run
1.	Install the required Python libraries: pip install pandas numpy matplotlib seaborn statsmodels.api
2.	Execute the Python scripts in the scripts directory.
3.	Open the [Tableau dashboard](https://public.tableau.com/views/AcademicPerformance_17171028986820/WherearetheTop500UniversitiesintheWorld?:language=pt-BR&publish=yes&:sid=&:display_count=n&:origin=viz_share_link) files to explore the visualizations.
4.	For an End-to-End analysis, read my [post on Medium platform](https://medium.com/@fabianamfz/end-to-end-data-analysis-and-visualization-project-ba16fedfc0ab)

![Captura de ecrã 2024-07-15 112129](https://github.com/user-attachments/assets/2ca4a4ef-5582-40f9-a3cf-a32f58b3bcb2)

## QS World University Rankings 2024
The QS World University Rankings is a comprehensive ranking of 1,500 institutions across 104 locations, emphasizing employability and sustainability. The top universities in the world include both public and private institutions, with notable examples in the United States, United Kingdom, Europe, and Asia. In Latin America, top universities are predominantly public institutions.

Their ranking includes the following scoring metrics:
1. AR - Academic Reputation
2. ER - Employer Reputation
3. SUS – Sustainability
4. GER - Employment outcomes
5. FSR - Faculty Student Ratio 
6. CPF - Citations per Faculty 
7. IFR - International Faculty Ratio
8. ISR - International Students Ratio 
9. IRN - International Research Network 

All universities then receive an Overall Score - which is a weighted average of the other grades - and are finally ranked according to this final score.

### Economic Development and Universities
The relationship between universities and a country's wealth is multifaceted:

1.	Economic Development:
Wealthier countries can invest more in higher education, leading to better-funded universities.
Well-funded universities offer high-quality education, attract top faculty, and conduct cutting-edge research, driving economic growth.

2.	Human Capital:
Universities enhance human capital by providing education and training, boosting workforce skills and productivity.
A highly educated workforce is key to economic growth and innovation.

3.	Research and Innovation:
Universities are centers for research and innovation, leading to technological advancements and new industries.
Strong university systems contribute to patents, startups, and industry partnerships, promoting economic prosperity.

4.	Global Competitiveness:
Prestigious universities attract international students and faculty, fostering a diverse and competitive academic environment.
Leading universities enhance a country's global reputation and influence.

5.	Social and Cultural Impact:
Universities promote social and cultural development, encouraging values like critical thinking, equality, and civic engagement.
A well-educated population contributes to a more stable and cohesive society, supporting economic growth.

### Case Study: Brazil
Brazil's case demonstrates how emerging economies can develop high-ranking universities despite challenges. Factors contributing to the success of universities like the University of São Paulo (USP) and the State University of Campinas (Unicamp) include targeted investments, strong government policies, international collaborations, and a cultural emphasis on research and development.

## Key Insights
- The higher the university's overall score, the higher their rank.
- The vast majority of universities that appeared in the 2023_rank, also appeared in the 2024_rank.
- U.S, U.K, Germany, China, Australia have remained as the countries with the higher count of institutions on the top 500 from 2023 to 2024.
- There are only 62 countries in the list for 2024_rank.
- 75% of the countries have a count of universities between 1.25 and 8. Counts above 18 (Q3 + IQR*1.5) can be considered outliers, that is, U.S, U.K, Germany, China and Australia have a count of institutions far above average.
- Overall Scores range mostly between 32.05 and 57.7. Universities with overall scores above 96.17 (Q3 + IQR*1.5) can be considered outliers, meaning that they are exceptionally good.
'United States', 'United Kingdom', 'Switzerland', 'Singapore' are the only countries in the top 10 universities.

### Correlations
- To perform a correlation analysis, all indicators were aggregated:
  For universities scores, the max of each country's university overall scores were used (max makes more sense than the mean because some countries have a large range of scores, this way we mantain the ranking).
  For economic, social and educational indicators, the mean of each country over the years was used.
- AR - Academic Reputation, is the score more closely correlated to the countries' maximum overall score. After that, SUS – Sustainability, GER - Employment outcomes,  ER - Employer Reputation, IRN - International Research Network, ISR - International Students Ratio, CPF - Citations per Faculty; the other indicators that are more highly correlated to the maximum overall_scores of a country are the researchers_in_r&d_(per_million_people) and the percentage of GDP spent in research and development, followed by the HDI,  the  number of articles published in Scientific and technical journals and the learning-adjusted_years_of_school;  IFR (International Faculty Ratio) and FSR (Faculty Student Ratio) and gdp_per_capitacome only after these. Meaning that, the higher the above indicators, the higher the maximum overall_score of a country. Also, the lower the inequality_in_education the higher the maximum score. percentage of population in poverty, expenditure estimates in education, population, literacy_estimates and the gini_coefficient (economic inequality) are very low correlated to the overall_scores.

- Top countries and bottom countries (from both count of institutions and overall scores) were selected. Brazil (my homecountry) and Portugal (where I live) were also included in the filter.
- Correlations matrix was performed again and we could see new correlations:
After the ranking scores AR - Academic Reputation, ER - Employer Reputation, GER - Employment outcomes, SUS – Sustainability, and CPF - Citations per Faculty
the indicators that are more highly correlated to the maximum overall_scores of a country are the percentage of GDP spent in research and development, followed by IRN - International Research Network, ISR - International Students Ratio, and the researchers_in_r&d_(per_million_people), then we have the  number of articles published in Scientific and technical journals and the HDI; FSR (Faculty Student Ratio), IFR (International Faculty Ratio) and learning-adjusted_years_of_school come only after these; GDP per capita and population seem to be somewhat correlated to the scores as well. Meaning that, the higher the above indicators, the higher the maximum overall_score of a country. Also, the lower the inequality_in_education the higher the maximum score. Percentage of population in poverty, expenditure estimates in education, literacy_estimates and the gini_coefficient (economic inequality) are very low correlated to the overall_scores.

### Data Sources
- QS World University Rankings: [2024](https://www.topuniversities.com/world-university-rankings/2024)
- Population: [Population Estimates](https://ourworldindata.org/grapher/population-with-un-projections?country=BRA~PRT~AGO~MOZ~CPV~GNB~STP~TLS )
- GDP per capita: [GDP per Capita](https://ourworldindata.org/grapher/gdp-per-capita-maddison)
    This data is adjusted for inflation and for differences in the cost of living between countries.    
- Poverty: [Share of Population in Extreme Poverty](https://ourworldindata.org/grapher/share-of-population-in-extreme-poverty?tab=chart&country=BRA~PRT )
    Percentage of population living in households with an income or consumption per person below $2.15 a day.
- Human Development Index (HDI): [HDI Data](https://ourworldindata.org/grapher/human-development-index)
    The Human Development Index (HDI) is a summary measure of key dimensions of human development: a long and healthy life, a good education, and a decent standard of living. Higher values indicate higher human development.
- Literacy: [Literacy rates] (https://ourworldindata.org/grapher/cross-country-literacy-rates)
    The share of adults aged 15 and older who can both read and write.
- Economic Inequality:[Gini Index](https://ourworldindata.org/grapher/economic-inequality-gini-index?time=2023&country=~BRA)
    The Gini coefficient measures inequality on a scale from 0 to 1. Higher values indicate higher inequality.
- Education Inequality: [Inequality in Education](https://ourworldindata.org/grapher/inequality-in-education)
    Inequality is measured here in terms of the number of years adults older than 25 participated in formal education.
- Learning-Adjusted Years of Schooling: [Learning-Adjusted Years of Schooling](https://ourworldindata.org/grapher/learning-adjusted-years-of-school-lays)
    Learning-adjusted years of schooling merge the quantity and quality of education into one metric, accounting for the fact that similar durations of schooling can yield different learning outcomes. Learning Adjusted Years of School are calculated by multiplying the estimates of Expected Years of School by the ratio of most recent Harmonized Test Score to 625, where 625 corresponds to advancement attainment on the TIMSS (Trends in International Mathematics and Science Study) test.
- Government Expenditure on Education: [Government Expenditure](https://ourworldindata.org/grapher/total-government-expenditure-on-education-gdp)
    Total general government expenditure on education (all levels of government and all levels of education), given as a share of GDP.
- Research and Development (R&D) Spending: [Research Spending](https://ourworldindata.org/grapher/research-spending-gdp)
    Includes basic research, applied research, and experimental development by governments as a share of GDP.
- Scientific Publications: [Scientific and Technical Journal Articles](https://ourworldindata.org/grapher/scientific-and-technical-journal-articles)
    Includes physics, biology, chemistry, mathematics, clinical medicine, biomedical research, engineering and technology,and earth and space sciences.
- Number of R&D researchers per million people: [R&D researchers](https://ourworldindata.org/grapher/researchers-in-rd-per-million-people)
    Professionals engaged in conceiving or creating new knowledge, products, processes, methods, or systems.
