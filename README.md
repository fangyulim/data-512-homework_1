# data-512-homework_1
# DATA512_HW1
DATA 512 Homework 1: Professionalism & Reproducibility

## Goal
    - The goal of this assignment is to construct, analyze, and publish a dataset of monthly article traffic for a set of pages from English Wikipedia from July 1, 2015 through September 30, 2024. 
    - The list of articles is determined in the rare-disease_cleaned.AUG.2024.csv file.

## License:
    - **Wikimedia**: 
[Wikimedia API Reference](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html)
        - Creative Commons Attribution-ShareAlike 3.0 (CC-BY-SA 3.0) 
        - GNU Free Documentation License (GFDL)
            - My dataset was created using the Wikimedia API, which is governed by their Terms of Use. By utilizing this data, you agree to comply with the attribution requirements specified by the CC-BY-SA license. Any adaptations or modifications of the dataset must be shared under a similar license. Care should be taken to respect user privacy and adhere to applicable data protection regulations. All interactions with the API should comply with its usage guidelines.

    - **rare-disease_cleaned.AUG.2024.csv** 
[rare-disease_cleaned.AUG.2024.csv](rare-disease_cleaned.AUG.2024.csv) 
        - Creative Commons (CC-BY license)
    
    - **wp_article_views_example.ipynb** 
[wp_article_views_example.ipynb](wp_article_views_example.ipynb)
    This code example was developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the [Creative Commons](https://creativecommons.org) [CC-BY license](https://creativecommons.org/licenses/by/4.0/). Revision 1.3 - August 16, 2024

## Project Structure
project-main/ <br>
| <br>
|-- HW1_Professionalism_Reproducibility_FangYuLim.ipynb <br>
|-- [rare-disease_cleaned.AUG.2024.csv](rare-disease_cleaned.AUG.2024.csv) <br>
|-- [wp_article_views_example.ipynb](wp_article_views_example.ipynb) <br>
| <br>
|-- output/ <br>
|   |-- [rare-disease_monthly_desktop_start201507-end202409.json](rare-disease_monthly_desktop_start201507-end202409.json) <br>
|   |-- [rare-disease_monthly_mobile_start201507-end202409.json](rare-disease_monthly_mobile_start201507-end202409.json) <br>
|   |-- [rare-disease_monthly_cumulative_start201507-end202409.json](rare-disease_monthly_cumulative_start201507-end202409.json) <br>
|   |-- [max_avg_min_avg.png](max_avg_min_avg.png) <br>
|   |-- [top_10_peak_page_views.png](top_10_peak_page_views.png) <br>
|   |-- [fewest_months_of_data.png](fewest_months_of_data.png) <br>


## Final output files
    - The three JSON files follow the same data schema:
        - rare-disease_monthly_desktop_start201507-end202409.json  <br>
          This file contains the monthly desktop page traffic for the subset of articles from July 2015 - Sept 2024.
        
        - rare-disease_monthly_mobile_start201507-end202409.json <br>
          This file contains the monthly mobile page traffic for the subset of articles from July 2015 - Sept 2024. (mobile-web and mobile-app)
        
        - rare-disease_monthly_cumulative_start201507-end202409.json  <br>
          This file contains the cummulative mobile page traffic for the subset of articles from July 2015 - Sept 2024 for both mobile and desktop access. 

        **Schema** : 
        {"disease_name1": [{"project": "string", 
                            "granularity": "string",
                            "timestamp": "string",
                            "agent": "string",
                            "views": "int" },
                           {}],
         "disease_name2": [{"project": "string",
                            "granularity": "string",
                            "timestamp": "string",
                            "agent": "string",
                            "views": "int" },
                           {}] }

    - **3 png files for the graphs**
        - max_avg_min_avg.png
          This graph displays the time series of the four articles with the highest and lowest average page views (for desktop and mobile access).

        - top_10_peak_page_views.png
          This graph displays the time series of the top 10 articles with the highest page views (for desktop and mobile access).

        - fewest_months_of_data.png
          This graph displays the time series of the 10 articles with the fewest months of available data (for desktop and mobile access).

## Issues/ To reproduce 
    - Not all the diseases have the same span (eg: COVID website only started to exist in 2020)
    - There are 4 different parameters for the access when using the API. 
        all-access ┃ desktop ┃ mobile-app ┃ mobile-web
    - You will need a list of article titles. Please reference the rare-disease_cleaned.AUG.2024.csv
    - There might be a need to review the enocding for article titles
       article_title_encoded = urllib.parse.quote(request_template['article'].replace(' ', '_'), safe='')

## Installation Instructions
To run this project, you will need the following Python packages installed:
- json
- urllib.parse
- itertools
- copy
- time 
- pandas     (2.2.1)
- matplotlib (3.8.0)
- requests   (2.31.0)
- seaborn    (0.12.2)


Python version: 3.11.9
