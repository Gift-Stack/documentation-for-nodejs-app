# Revie hypothetical platform (Node.js)

> Backend API

This allows users to sign up or log in and post reviews about the apartments
they've previously lived in. These reviews may include videos and/or images
e(optional). They can give reviews about the landlord,the environment the
apartment is situated,and quality of the apartment.

These reviews can be uniquely marked by random visitors as helpful.

# Usage

> For deployed link

<!-- -   Sign up route: /api/user
-   Log in route: /api/auth
-   View posts route: /api/post
-   Auth user & get token route: /api/auth
-   Add post route: /api/post
-   Delete post route: /api/post
-   View posts route: /api/post -->

Run this code here, in a console or from any site

fetch(' https://immense-tor-81857.herokuapp.com/api/post ') .then(response =>
response.json()) .then(data => console.log(data))

NB: This is a protected route. So you are required to sign up or log in, if
you've signed uo before, before viewing your posts

# Routes

HTTP methods supported are

-   GET
-   POST
-   DELETE

> GET method

-   /api/auth

This is used in the authentication route (/api/auth) for getting logged in
user's detail by sending the token generated using header(key: x-auth-token,
value: 'token generated')

-   /api/post

The GET method is also used in the post route('/api/post) for getting all of the
user's reviews for different apartments. This route is also private, therefore,
a header with "x-auth-token" : "token generated" key/value pair is required
after the Content-Type header.

> POST method

-   /api/user

This is used in the user route (/api/user) for signing up a user. This route is
public, therefore, no token is required. The route takes in compulsory name,
email and password (which must be more than 6 letters)

-   /api/auth

This method is also used in the authentication route(/api/auth) for logging in a
user. That is, after authenticating the user ( inputing the user's email and
password ), the token is sent back as a response to validate that user is logged
in. This token is what is user to get the logged in user's reviews from the
database with get('https://immense-tor-81857.herokuapp.com/api/auth)

-   /api/post

Lastly, the POST method is used to add new post to user's database ( /api/post
). This route is private. This means can only ba accessed by logged in users.
Therefore, token is required. The token can be sent using the "x-auth-token" :
"token generated from login" key/value pair as header.

> DELETE

-   /api/post/:id

This method is used to delete a review already posted. This route is only
available in the post route (/api/post/:id). Definitely, this route is private
as only logged in user can access to delete a review. The token is required and
can be sent using the "x-auth-token" : "token generated from login" key/value
pair as header. NB: the :id in the route (/api/post/:id) should be gotten with
the (.params.id) parameter.
