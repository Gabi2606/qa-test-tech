# Part 2: API Test - Postman Collection

## Overview

This project includes a Postman collection that contains automated tests for a RESTful API. The API is used to manage posts, comments, and profile information. The collection tests various HTTP methods such as GET, POST, PUT, and DELETE.

### Endpoints Covered
- GET /posts: Fetch a list of all posts.
- GET /posts/{id}: Fetch a single post by its ID.
- POST /posts: Create a new post.
- PUT /posts/{id}: Update an existing post by its ID.
- DELETE /posts/{id}: Delete a post by its ID.
- GET /comments: Fetch a list of all comments.
- GET /comments/{id}: Fetch a single comment by its ID.
- POST /comments: Create a new comment.
- PUT /comments/{id}: Update an existing comment by its ID.
- DELETE /comments/{id}: Delete a comment by its ID.
- GET /profile: Fetch the profile information.

## Prerequisites

Before running the tests, make sure you have the following installed:

- **Node.js** (v14 or higher)
- **npm** (v6 or higher)
- **Postman** (to run the Postman collection)

## Installation Instructions

1. **Clone the repository**:
```
git clone https://github.com/Gabi2606/qa-test-tech.git
cd QA-TECH-TEST-MAIN
```

2. **Install the dependencies:**
```
npm install
```

3. **Start the JSON server:**
```
npm start
```
The server will run at http://localhost:3000.

## Running Tests in Postman

To run the tests in this Postman collection, follow these steps:

1. Import the file collection.json and environment.json

    With it will create an environment variable named base_url with the value http://localhost:3000 and two variables: postId and commentsId

    This will be used in the endpoints.

2. Run the Tests:

    Once the environment is set, click the Run button in the top-right corner of Postman (in the Overview tab of the collection).

    This will run all the tests in the collection and show you the results.


## Considerations

- I created a Cleanup folder at the end of the collection, which includes the DELETE requests for posts and comments. This folder ensures that the API state is reset after running tests, keeping the environment clean for subsequent runs.

- I store the postId and commentId in the environment variables for use in future requests. These IDs are needed to perform operations such as GET, PUT, and DELETE on specific posts or comments (e.g., GET /posts/{id}, PUT /comments/{id}). By saving these IDs, I ensure that the tests are consistent and can refer to the correct resources during their execution.

- In a real-world scenario, a comment should not exist without an associated post. With proper database management (such as foreign key constraints and cascading deletes), it would not be possible to create a comment for a non-existent post, and deleting a post would automatically remove its related comments. However, even though JSON Server does not enforce these rules, I enforced the comment creation to use an existent postId and organized the tests so that comments are deleted before their associated posts, simulating how it would work in a real environment. 


## Endpoint improvements considerations:

Should there be an endpoint like /profile/{id} or /profile/me?
-  An endpoint like /profile/{id} would allow retrieving the profile of any user by their ID.
-  An endpoint like /profile/me could return the profile of the authenticated user (using an authentication system).


