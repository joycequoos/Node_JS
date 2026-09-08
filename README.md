# Node.js API — DevHouse

[← Back](https://github.com/joycequoos/Development)

REST API developed in Node.js, using Express for the HTTP server and MongoDB (via Mongoose) as the database. The project exposes authentication (session) routes and property registration routes, including cover image upload.

## About the Project

This API serves as the back end for a property-listing application (**DevHouse**), allowing:

- **Session authentication** — a route for user login/authentication.
- **Property registration** — a route to create a new property, with the upload of a thumbnail image.

## Technologies Used

| Technology | Role in the Project |
|---|---|
| **Node.js** | JavaScript runtime environment on the server. |
| **Express** | Framework for creating the HTTP server and the API routes. |
| **Mongoose** | Library for data modeling and connecting to MongoDB. |
| **Multer** | Middleware for file uploads (property images). |

## File Structure

| File | Description |
|---|---|
| [server.js](https://github.com/joycequoos/Node_JS/blob/main/server.js) | The application's entry point — starts the server on port `3333`. |
| [app.js](https://github.com/joycequoos/Node_JS/blob/main/app.js) | Main application configuration: MongoDB connection, middlewares, and route loading. |
| [routes.js](https://github.com/joycequoos/Node_JS/blob/main/routes.js) | Definition of the API routes and their respective controllers. |

## API Routes

| Method | Route | Description |
|---|---|---|
| `POST` | `/sessions` | Authenticates a user (login). |
| `POST` | `/houses` | Registers a new property, receiving the thumbnail image via upload (`multipart/form-data`). |

## How to Run

```bash
# install the dependencies
npm install

# start the server
node server.js
```

The server will be available at `http://localhost:3333`.

## Security Note

The `app.js` file currently contains the MongoDB connection string (username and password) directly in the code. For production projects, it's recommended to move these credentials to environment variables (for example, using a `.env` file with the `dotenv` library), avoiding exposing sensitive data in the repository.
