
## API SPECIFICATION:

1) Get Books I have read/currently reading:

   /books_read/ (GET)
   Request: {UserID: "Integer"}

   Response:
   [
    {
      Book ID: "Integer"
      Book Name: "string"
      Author: "string"
      Day/Month/Year started: "Integer"
      Day/Month/Year finished: "Integer" (if not finished, will return NULL and if NULL, output will be "Still Reading")
    }
   ]

2) Create Account:

   /review_book/ (POST)
   Request:
   {
       Name: "string"
       email: "string"
       password: "string"
   }

   Response:
   {
      userID: "Integer"
   }

3) Log Books I started reading:

   /books_started/ (POST)
   [
    {
      Book ID: "Integer"
      Day/Month/Year started: "Integer"
    }
   ]

   Response:
    {
        Okay: "string"
    }

3) Log Books I finished reading:

   /books_finished/ (POST)
   [
    {
      Book ID: "Integer"
      Day/Month/Year finished: "Integer"
    }
   ]

   Response:
    {
        Okay: "string"
    }

4) Review Book:

   /books_review/ (POST)
   [
    {
      userID: "integer"
      Book ID: "Integer"
      Review: "Integer" (1-5)
      isFinished: "Boolean" (useful for book recommondation data)
    }
   ]

   Response:
    {
        Okay: "string"
    }

   
5) Get Reviewed Books:

   /books_reviewed/ (GET)
   {
      userID: "Integer"
   }

   [
    {
      reviewID: "Integer"
      Book ID: "Integer"
      Book Name: "string"
      Author: "String"
      Review: "Integer" (1-5)
    }
   ]


6) Find books by genre:

   /find_genre/ (GET)
   {
      genre: "string"
   }

   [
    {
      Book ID: "Integer"
      Book Name: "string"
      Author: "String"
    }
   ]


7) Find books by author:

   /find_author/ (GET)
   {
      author: "string"
   }

   [
    {
      Book ID: "Integer"
      Book Name: "string"
      genre: "String"
    }
   ]
    

5) Recommend books:

   /books_recommend/ (GET)
   {
      userID: "integer" (implementing a basic AI to take a mix of the user's read books and reviews to recommend books of similar authors and genres)
   }

   [
    {
      Book ID: "Integer"
      Book Name: "string"
      Author: "string"
      Genre: "string
    }
   ]
