# What You're Creating
This assignment has two deliverables
1. Scrape titles and preview text from Mars news articles
2. Scrape and analyze Mars weather data, which exists in a table

# Instructions

## Part 1: Scrape Titles and Preview Text from Mars News
Use `part_1_mars_news.ipynb` and follow the steps below. 

1. use automated browsing to visit the [Mars news site](https://static.bc-edx.com/data/web/mars_news/index.html). Inspect the page to identify which elements to scrape. 


>Hint: Use Chrome DevTools to identify which elements to scrape.

2. Create a BeautifulSoup obejct and use it to extract text elements from the website. 

3. Extract the titles and preview text of the news articles that you scraped. Store the scraping results in Python data structures as follows:
    - Store each title-and-preview pair in a Python dictionary and, give each dictionary two keys: `title` and `preview`. An example is the following 
        - `'title': "NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm, 
        'preview': "For the first time in its eight years orbiting Mars, NASA's MAVEN mission witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27."}`
    - Store all the dictionaries in a Python list
    - Print the list in your notebook

4. Optionally, store the scraped data in a file (to ease sharing the data with others). To do so, export the scraped data to a JSON file. 

## Part 2: Scrape and Analyze Mars Weather Data

Use `part_2_mars_weather.ipynb` and follow the steps below. 

1. Use automated browsing to visit the [Mars Temperature Data Site](https://static.bc-edx.com/data/web/mars_facts/temperature.html). Inspect the page to identify which elements to scrape. The url is `https://static.bc-edx.com/data/web/mars_facts/temperature.html`

>Hint: To identify which elements to scrape, you might want ot inspect the page using Chrome DevTools to discover whether th etable contains usable classes. 

2. Create a Beautiful Soup object and use it to scrape the data in the HTML table. Note that this can also be achieved by using Pandas `read_html` functoin. However, use Beautiful Soup here to continue sharpening your web scraping skills. 

3. Assemble the scraped data into a pandas dataframe. The columns should have the same headings as the table on the website. Below is an explanation of the column headings: 
    - `id`: the identification number of a single transmission from the Curiosity rover
    - `terrestrial_date`: the date on Earth
    - `sol`: the number of elapsed sols (Martian days) since Curiosity landed on Mars
    - `ls`: the solar longitude
    - `month`: the Martian month
    - `min_temp`: the minimum temperature, in Celsius, of a single Martian day (sol)
    - `pressure`: the atomospheric pressure at Curiosity's location

4. Examine the data types that are currently associated with each column. If necessary, cast (or convert) the data to the appropriate `datetime`, `int`, `float` data type. 

5. Analyze your dataset by using Pandas functions to answer the following questions: 
    - How many months exist on Mars?
    - How many Martian (and not earth) days worth of data exist in the scraped dataset?
    - What are the coldest and warmest months on Mars (at the location of Curiosity)? To answer this question:
        - Find the average minimum daily temperature for all of the months
        - Plot the results as a bar chart
    - Which months have the lowest and highest atmospheric pressure on Mars? To answer this question:
        - Find the average daily atmospheric pressure of all the months
        - Plot the results as a bar chart
    - About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
        - Consider how many days elapse on Earth in the time that Mars circles the sun once. 
        - Visually estimate the result by plotting the daily minmum temperature

6. Export the dataframe to a CSV file

# Requirements
## Part 1: Scrape Titles and Preview Text from Mars News (40 points)
- Automated browsing (with Splinter) was used to visit the Mars news site, and the HTML code was extracted (with Beautiful Soup). (10 points)

- The titles and preview text of the news articles were scraped and extracted. (20 points)

- The scraped information was stored in the specified Python data structure—specifically, a list of dictionaries. (10 points)

## Part 2: Scrape and Analyze Mars Weather Data (60 points)
- The HTML table was extracted into a Pandas DataFrame. Either Pandas or Splinter and Beautiful Soup were used to scrape the data. The columns have the correct headings and data types. (15 points)

- The data was analyzed to answer the following questions: (10 points)

    - How many months exist on Mars? (5 points)
    - How many Martian days' worth of data are there? (5 points)

- The data was analyzed to answer the following questions, and a data visualization was created to support each answer: (30 points)

    - Which month, on average, has the lowest temperature? The highest? (10 points)
    - Which month, on average, has the lowest atmospheric pressure? The highest? (10 points)
    - How many terrestrial days exist in a Martian year? A visual estimate within 25% was made. (10 points)
    
- The DataFrame was exported into a CSV file. (5 points)