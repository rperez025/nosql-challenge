# nosql-challenge
Module 12 - NoSQL databases

**BACKGROUND**

With this challenge, I've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

**DELIVERABLE AND ASSOCIATED REQUIREMENTS**

**Database and Jupyter Notebook Set Up**

Used NoSQL_setup_starter.ipynb for this section of the challenge.

  1. Imported the data provided in the establishments.json file from my Terminal. Named the database uk_food and the collection establishments. Copied the text I used to import your data from my Terminal to a markdown cell in my notebook.
  2. Within your notebook, imported the libraries I needed: PyMongo and Pretty Print (pprint).
  3. Created an instance of the Mongo Client.
  4. Confirmed that I created the database and loaded the data properly:
     * Listed the databases I have in MongoDB. Confirmed that uk_food was listed.
     * Listed the collection(s) in the database to ensure that establishments was there.
     * Found and displayed one document in the establishments collection using find_one and displayed with pprint.
  5. Assigned the establishments collection to a variable to prepare the collection for use.

**Update the Database**

  1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet. The magazine has asked me to include it in my analysis. Added the following information to the database:

{
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}

  2. Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.
  3. Update the new restaurant with the BusinessTypeID you found.
  4. The magazine is not interested in any establishments in Dover, so check how many documents contain the Dover Local Authority. Then, remove any establishments within the Dover Local Authority from the database, and check the number of documents to ensure they were deleted.
  5. Some of the number values are stored as strings, when they should be stored as numbers.
     * Use update_many to convert latitude and longitude to decimal numbers.
     * Use update_many to convert RatingValue to integer numbers.

**RESOURCES AND REFERENCES**

During the challenge, I referenced the following to aid in my understanding and completion of the assignment:

1. Reviewed and reperformed a majority of the class activities in my GitLab Working Folder.
  
2. Research reference:
- [Change the data type of a column or a Pandas Series](https://www.geeksforgeeks.org/change-the-data-type-of-a-column-or-a-pandas-series/)

3. Code reference:
* In [8] convert_dict={'id':int,'sol':int,'ls':int,'month':int,'min_temp':float,'pressure':float}temp_df=temp_df.astype(convert_dict)temp_df["terrestrial_date"]=pd.to_datetime(temp_df["terrestrial_date"])print(temp_df.dtypes) -- Used in [part_2_mars_weather.ipynb](https://github.com/rperez025/data-collection---challenge/blob/main/part_2_mars_weather.ipynb) in In [10]
