# nosql-challenge
Module 12 - NoSQL databases

**BACKGROUND**

With this challenge, I've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

**DELIVERABLE AND ASSOCIATED REQUIREMENTS**

**Database and Jupyter Notebook Set Up**

Used [NoSQL_setup_starter.ipynb](https://github.com/rperez025/nosql-challenge/blob/main/NoSQL_setup_starter.ipynb) for this section of the challenge.

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

  2. Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
  3. Updated the new restaurant with the BusinessTypeID you found.
  4. The magazine is not interested in any establishments in Dover, so checked how many documents contain the Dover Local Authority. Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
  5. Some of the number values are stored as strings, when they should be stored as numbers.
     * Used update_many to convert latitude and longitude to decimal numbers.
     * Used update_many to convert RatingValue to integer numbers.

**Exploratory Analysis**

Eat Safe, Love has specific questions they want me to answer, which will helped them find the locations they wish to visit and avoid.

I used [NoSQL_analysis_starter.ipynb](https://github.com/rperez025/nosql-challenge/blob/main/NoSQL_analysis_starter.ipynb) for this section of the challenge.

Then, I used the following questions to explore the database, and find the answers, so I could provide them to the magazine editors.

Unless otherwise stated, for each question:

    * Used count_documents to display the number of documents contained in the result.
    * Displayed the first document in the results using pprint.
    * Converted the result to a Pandas DataFrame, printed the number of rows in the DataFrame, and displayed the first 10 rows.

  1. Which establishments have a hygiene score equal to 20?
  2. Which establishments in London have a RatingValue greater than or equal to 4?
     Hint: The London Local Authority has a longer name than "London" so you will need to use $regex as part of your search.
  3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
     Hint: You will need to compare the geocode to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.
  4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.

**RESOURCES AND REFERENCES**

During the challenge, I referenced the following to aid in my understanding and completion of the assignment:

1. Reviewed and reperformed a majority of the class activities in my GitLab Working Folder.

2. Reviewed the following instructor videos from Dr. A:
   * [NoSQL Day 02 - Activity 06 - Air Fields (Demo)](https://youtu.be/9c9F6cP74wg)
   * [NoSQL Day 02 - Activity 08 - Find Pets (Demo)](https://youtu.be/bKnCmHFGN5s)
   * [NoSQL Day 02 - Activity 10 - Sort and Limit Pets (Demo)](https://youtu.be/e5ymqICA2BA)
   * [NoSQL Day 03 - Activity 08 - Mini-Project Part 3 (Demo)](https://youtu.be/SdxpC7nT1hM)
  
3. Research reference:
   [What's the canonical way to check for type in Python?](https://stackoverflow.com/questions/152580/whats-the-canonical-way-to-check-for-type-in-python/57099789#57099789)

   Used the following in In [21] in NoSQL_setup_starter file:
   You can check for type of a variable using __name__ of a type.
   Ex:
   >>> a = [1,2,3,4]
   >>> b = 1>>> type(a).__name__
   'list'
   >>> type(a).__name__ == 'list'
   True>>> type(b).__name__ == 'list'
   False>>> type(b).__name__
   'int'

4. I also used the following code as reference for performing my assignment. Specifically, I would review the code and gain an understanding of its organization and use. I would then take that understanding and incorporate my knowledge and practice from the class activities and instructor videos to write my script included [NoSQL_setup_starter.ipynb](https://github.com/rperez025/nosql-challenge/blob/main/NoSQL_setup_starter.ipynb) and [NoSQL_analysis_starter.ipynb](https://github.com/rperez025/nosql-challenge/blob/main/NoSQL_analysis_starter.ipynb).
   * [yeyanwang/nosql-challenge](https://github.com/yeyanwang/nosql-challenge/blob/main/NoSQL_setup.ipynb)

