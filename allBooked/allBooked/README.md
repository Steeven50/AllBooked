# allBooked

**Web App for Book Enthusiasts**

## Description

**allBooked** is a web app that allows users to register an account, search for books, and share their thoughts by leaving reviews. Users can view their reviews on their profile page, offering a personalized space to showcase their literary experiences to others.

## Technologies Used

- **Frontend:** Built with React
- **Backend:** Powered by Express
- **Database:** Managed with PostgreSQL (psql)

## Google Books API

The Google Books API was used for sourcing book data, and all data relating to books are fetched with their corresponding Google Books API ID.  In frontend/src/api/googleBooksApi.js, you'll find the js class with a few methods for making calls to the API. Here's a quick demonstration on how they should work. 

### Book Search

For Searching for books based on a query, use the searchBooks method and pass in the query as a parameter.  This should return an array of items.

```javascript
const searchQuery = "Dune";
try {
  const searchResults = await GoogleBooksApi.searchBooks(searchQuery);
  console.log("Search Results:", searchResults);
} catch (error) {
  console.error("Error searching books:", error);
}
```

To get deatils about a specific book, use the getBook method, passing in the ID as a parameter.

```javascript
const bookId = "VALID_BOOK_ID";
try {
  const bookDetails = await GoogleBooksApi.getBook(bookId);
  console.log("Book Details:", bookDetails);
} catch (error) {
  console.error(`Error fetching book ${bookId}:`, error);
}
```
This class was made to handle requests to the Google Books API in a way that was convenient and keeps any other API aware content out of the rest of the frontend.

## Getting Started

### Prerequisites

Make sure you have a PostgreSQL database named **allbooked** with the appropriate schema. You can use the provided schema from [allbookedschema.sql](https://github.com/boodamans/allBooked).

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/boodamans/allBooked.git
    ```

2. Set up the backend:

    ```bash
    # Navigate to the backend directory
    cd allBooked/backend

    # Install dependencies
    npm install

    # Start the express backend
    npm start
    ```

3. Set up the frontend:

    ```bash
    # Navigate to the frontend directory
    cd allBooked/frontend

    # Install dependencies
    npm install

    # Start the React frontend
    npm start
    ```

## Note

This project was completed under time constraints, and some features remain unimplemented. Unused express routes, methods within models, and React components may be present in the project files.

## Contributing

Contributions are welcome! Feel free to report issues, suggest enhancements, or submit pull requests.

## Contact

For any questions or feedback, please contact Sam Narciso at samnarciso3300@gmail.com.
