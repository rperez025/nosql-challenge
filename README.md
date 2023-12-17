# nosql-challenge
Module 12 - NoSQL databases

**BACKGROUND**

With this challenge, I've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

**DELIVERABLE AND ASSOCIATED REQUIREMENTS**

**Database and Jupyter Notebook Set Up**

Used NoSQL_setup_starter.ipynb for this section of the challenge.

1. Import the data provided in the establishments.json file from your Terminal. Name the database uk_food and the collection establishments. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
2. Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).
3. Create an instance of the Mongo Client.
4. Confirm that you created the database and loaded the data properly:
   * List the databases you have in MongoDB. Confirm that uk_food is listed.
   * List the collection(s) in the database to ensure that establishments is there.
   * Find and display one document in the establishments collection using find_one and display with pprint.
5. Assign the establishments collection to a variable to prepare the collection for use.

**2. Scraped and Analyzed Mars Weather Data**

a. Used automated browsing to visit the [Mars Temperature Data Site](https://static.bc-edx.com/data/web/mars_facts/temperature.html).

b. Created a Beautiful Soup object and used it to scrape the data in the HTML table. 

c. Assembled the scraped data into a Pandas DataFrame. Ensured the columns should have the following column headings:
* id: the identification number of a single transmission from the Curiosity rover
* terrestrial_date: the date on Earth
* sol: the number of elapsed sols (Martian days) since Curiosity landed on Mars
* ls: the solar longitude
* month: the Martian month
* min_temp: the minimum temperature, in Celsius, of a single Martian day (sol)
* pressure: The atmospheric pressure at Curiosity's location

d. Examined the data types that are currently associated with each column and casted (or converted) the data to the appropriate datetime, int, or float data types.

e. Analyzed the dataset by using Pandas functions to answer the following questions:
* How many months exist on Mars?
* How many Martian (and not Earth) days worth of data exist in the scraped dataset?
* What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
  - Find the average minimum daily temperature for all of the months.
  - Plot the results as a bar chart.
* Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
  - Find the average daily atmospheric pressure of all the months.
  - Plot the results as a bar chart.
* About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
  - Consider how many days elapse on Earth in the time that Mars circles the Sun once.
  - Visually estimate the result by plotting the daily minimum temperature.

f. Exported the DataFrame to a CSV file.

**RESOURCES AND REFERENCES**

During the challenge, I referenced the following to aid in my understanding and completion of the assignment:

1. Reviewed and reperformed a majority of the class activities in my GitLab Working Folder.
  
2. Research reference:
- [Change the data type of a column or a Pandas Series](https://www.geeksforgeeks.org/change-the-data-type-of-a-column-or-a-pandas-series/)

3. Code reference:
* In [8] convert_dict={'id':int,'sol':int,'ls':int,'month':int,'min_temp':float,'pressure':float}temp_df=temp_df.astype(convert_dict)temp_df["terrestrial_date"]=pd.to_datetime(temp_df["terrestrial_date"])print(temp_df.dtypes) -- Used in [part_2_mars_weather.ipynb](https://github.com/rperez025/data-collection---challenge/blob/main/part_2_mars_weather.ipynb) in In [10]
