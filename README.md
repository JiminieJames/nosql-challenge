nosql-challenge
Part 1: Database and Jupyter Notebook Set Up

Import Data:

Import the data provided in the json file from your Terminal.

Name the database uk_food and the collection establishments.
Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
Library Imports:

Within your notebook, import the libraries you need: PyMongo and Pretty Print (pprint).
Mongo Client:

Create an instance of the Mongo Client.
Database Confirmation:

List the databases you have in MongoDB. Confirm that uk_food is listed.
List the collection(s) in the database to ensure that establishments is there.
Find and display one document in the establishments collection using find_one and display with pprint.
Assign the establishments collection to a variable to prepare the collection for use.
Part 2: Update the Database
Use NoSQL_setup_starter.ipynb for this section of the challenge.

Add New Restaurant:

Find the BusinessTypeID for "Restaurant/Cafe/Canteen" and return only the BusinessTypeID and BusinessType fields.
Update the new restaurant with the BusinessTypeID you found.
Remove Dover Establishments:

Check how many documents contain the Dover Local Authority.
Remove any establishments within the Dover Local Authority from the database.
Check the number of documents to ensure they were deleted.
Data Type Conversion:

Use update_many to convert latitude and longitude to decimal numbers.
Use update_many to convert RatingValue to integer numbers.
Part 3: Exploratory Analysis
Use NoSQL_analysis_starter.ipynb for this section of the challenge.

Hygiene Score 20:

Find establishments with a hygiene score equal to 20.
Use count_documents to display the number of documents.
Display the first document in the results using pprint.
Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.
London RatingValue >= 4:

Find establishments in London with a RatingValue greater than or equal to 4.
Use $regex to locate the London establishments.
Use count_documents to display the number of documents.
Display the first document in the results using pprint.
Convert the result to a Pandas DataFrame, print the number of rows, and display the first 10 rows.
Top 5 Establishments Near Penang Flavours:

Find establishments within 0.01 degree of the "Penang Flavours" restaurant.
Limit the results to establishments with a RatingValue of 5.
Sort results by lowest hygiene score.
Limit the results to 5.
Print all five results using pprint.
Convert the result to a Pandas DataFrame and display.
Hygiene Score 0 in Each Local Authority:

Build an aggregation pipeline to include a match query, group, and sort.
Match documents with a hygiene score of 0.
Group on LocalAuthorityName and count the number of documents.
Sort the count of documents in descending order.
Send the aggregation pipeline to the aggregate method.
Cast the results as a list and save to a variable.
Print the first ten results using pprint.
Convert the result to a Pandas DataFrame and display the first 10 rows.
Requirements
Part 1: Database and Jupyter Notebook Set Up (15 points)
Include the mongoimport command text you used to import establishments.json in a markdown cell (3 points)
The mongoimport command text correctly drops any existing establishments collection before importing establishments.json (2 points)
The database is named uk_food and the collection is named establishments (2 points)
Correctly imports PyMongo and Pretty Print (2 points)
An instance of the Mongo Client is created (1 point)
Lists the databases you have in Mongo, which includes uk_food (1 point)
Lists the collection(s) in the uk_food database, which includes establishments (1 point)
Uses find_one() and pprint to display one document in the establishments collection (2 points)
The establishments collection is assigned to a variable (1 point)
Part 2: Update the Database (20 points)
The supplied data for the "Penang Flavours" restaurant is correctly inserted into the establishments collection (3 points)
A query is performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returns only the BusinessTypeID and BusinessType fields (3 points)
The "Penang Flavours" document is updated with the correct value for BusinessTypeID (3 points)
A query is correctly performed to delete all the documents in the collection where "Dover Local Authority" is the value for LocalAuthorityName (3 points)
A count_documents() check is performed before and after the removal of the Dover documents to ensure the documents were removed (4 points)
An update_many() query is performed to convert the latitude and longitude fields from strings to decimal numbers and RatingValue to integers (4 points)
Part 3: Exploratory Analysis (55 points)
Question 1: Which establishments have a hygiene score equal to 20? (8 points)

A query is correctly performed to find the establishments with a hygiene score of 20 (2 points)
count_documents() is used to list the correct number of documents (answer: 41) (2 points)
The first result is printed using pprint (2 points)
The results are converted to a Pandas DataFrame and display the first 10 rows (2 points)
Question 2: Which establishments in London have a RatingValue greater than or equal to 4? (12 points)

A query is correctly performed to find the establishments in London with a RatingValue greater than or equal to 4 (4 points)
The query uses the $regex operator to locate the London establishments (2 points)
count_documents() is used to list the correct number of documents (answer: 33) (2 points)
The first result is printed using pprint (2 points)
The results are converted to a Pandas DataFrame and display the first 10 rows (2 points)
Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? (15 points)

A query is correctly performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant (4 points)
The query also limits the results to establishments with a RatingValue of 5 (2 points)
The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score (2 points)
The query uses the limit() method in PyMongo to limit the results to 5 (2 points)
All five results are printed using pprint (3 points)
The results are converted to a Pandas DataFrame and display (2 points)
Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. (20 points)

An aggregation pipeline is built to include a match query, group, and sort (3 points)
The match query matches documents with a hygiene score of 0 (2 points)
The group step of the pipeline is grouped on LocalAuthorityName and counts the number of documents (4 points)
The sort step of the pipeline sorts the count of the documents in descending order (2 points)
The aggregation pipeline is correctly sent to the aggregate() method (2 points)
The results from the aggregation query are cast as a list and then saved to a variable (2 points)
The first ten results are printed using pprint (3 points)
The results are converted to a Pandas DataFrame and display the first 10 rows (2 points)