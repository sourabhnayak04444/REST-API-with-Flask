# REST-API-with-Flask
REST (Representational State Transfer): This is the architectural style the API follows. It's not a strict protocol but a set of guidelines for building web services. The key idea is that you have "resources" (in this case, users) that can be manipulated using standard HTTP methods.

CRUD Operations: The API provides the four fundamental functions of persistent storage, known as CRUD:

Create: POST /users (Adds a new user)

Read: GET /users (Gets all users) and GET /users/<id> (Gets one user)

Update: PUT /users/<id> (Modifies an existing user)

Delete: DELETE /users/<id> (Removes a user)

Resources and Endpoints:

A Resource is the "thing" you are managing. Here, the resource is a user.

An Endpoint is the URL where the resource lives. Your code defines two main endpoints:

/users: Represents the collection of all users.

/users/<int:user_id>: Represents a specific user, identified by their ID.

HTTP Methods (Verbs): The code correctly maps HTTP verbs to specific actions, which is a core tenet of REST theory:

GET: Used for safe, idempotent retrieval of data.

POST: Used to create a new resource.

PUT: Used to update an existing resource (or create it, though here it's just for updates).

DELETE: Used to remove a resource.

Statelessness (In-Memory Storage): The API uses a simple Python dictionary (users) as its database. This demonstrates the logic of data persistence without the complexity of a real database. Theoretically, this makes the server itself stateless (it doesn't store client session info between requests). All the "state" is in the users dictionary. In a real-world application, this dictionary would be replaced by a database like PostgreSQL, MySQL, or MongoDB.

Data Exchange Format (JSON): The API uses jsonify to send responses and request.json to receive data. JSON (JavaScript Object Notation) is the de-facto standard data format for modern APIs because it's lightweight and human-readable.

Server and Tunneling:

Flask acts as the web server, listening for HTTP requests on a local port (5000).

Pyngrok is a utility that creates a secure tunnel from a public URL to your local server. This is purely for testing, allowing you (or any tool like Postman) to send requests from the public internet to the Flask app running only on your machine.

