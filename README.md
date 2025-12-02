# MEAN To-Do App Backend

This is the **Node.js + Express + MongoDB backend** for a simple MEAN stack to-do application. It exposes a minimal REST API consumed by the Angular frontend.

## Tech Stack

- **Node.js / Express 5** - HTTP server and routing.
- **MongoDB + Mongoose 9** - Document database and ODM.
- **dotenv** - Environment variable management.
- **CORS** - Cross-origin resource sharing for the Angular frontend.

## API Endpoints

All endpoints are prefixed with `/api/todos`.

- `GET /api/todos`

  - Returns a JSON array of all todos sorted by `createdAt` (newest first).

- `POST /api/todos`

  - Creates a new todo.
  - **Request body (JSON):**

    ```json
    {
      "title": "Buy groceries"
    }
    ```

  - **Response (201 Created, JSON example):**

    ```json
    {
      "_id": "661f3c2d4abc123456789014",
      "title": "Buy groceries",
      "createdAt": "2025-01-03T08:00:00.000Z"
    }
    ```

## Installation

To run the backend locally:

1. Navigate to the backend folder:

   ```bash
   cd backend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Configure environment variables in `.env`:

   ```dotenv
   MONGODB_URI=your-mongodb-connection-string
   PORT=5000
   ```

   Example (MongoDB Atlas):

   ```dotenv
   MONGODB_URI=mongodb+srv://<user>:<password>@<cluster>/<database>?retryWrites=true&w=majority
   PORT=5000
   ```

4. Start the development server (with nodemon):

   ```bash
   npm run dev
   ```

   Or start with plain Node:

   ```bash
   npm start
   ```

5. The backend will be available at:

   ```text
   http://localhost:5000
   ```

   And the todos API at:

   ```text
   http://localhost:5000/api/todos
   ```

## Notes

- The todo model is defined in `models/Todo.js`.
- Routes are defined in `routes/todo.js` and mounted at `/api/todos` in `index.js`.
- CORS is enabled so the Angular frontend (typically running at `http://localhost:4200`) can access the API.

## Author

**Eng. Abdelaziz Mohamed**

- [LinkedIn](https://www.linkedin.com/in/abdelaziz)
- [GitHub](https://github.com/Abdelaziz-Mohammed)
