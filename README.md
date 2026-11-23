# Task 1 – Basic CRUD API with Express.js and MongoDB

A REST API for managing products. It uses Express.js, MongoDB, Mongoose, and express-validator.

## Features

- Create a product (POST)
- Get all products (GET)
- Get one product by ID (GET)
- Update a product (PUT)
- Delete a product (DELETE)
- Validate request data
- Centralized error handling and appropriate HTTP status codes

## Requirements

- Node.js and npm
- MongoDB running locally, or a MongoDB Atlas connection string

## Setup

1. Open this folder in a terminal.
2. Install dependencies:

   ```bash
   npm install express mongoose dotenv express-validator
   npm install --save-dev nodemon
   ```

3. Check `.env` and set `MONGODB_URI` to your MongoDB connection string. The supplied value uses a local MongoDB server.
4. Start the API:

   ```bash
   npm start
   ```

The server starts at `http://localhost:3000` after MongoDB connects.

## API endpoints

| Method | URL | Description |
|---|---|---|
| GET | `/` | API health message |
| POST | `/products` | Create a product |
| GET | `/products` | List all products |
| GET | `/products/:id` | Get one product |
| PUT | `/products/:id` | Update a product |
| DELETE | `/products/:id` | Delete a product |

### Example request body

Send this JSON to `POST /products` with `Content-Type: application/json`:

```json
{
  "name": "Laptop",
  "price": 999.99,
  "inStock": true
}
```

For `PUT /products/:id`, send one or more fields to update. For example, `{ "price": 899.99 }` updates only the price.

## Testing with Postman or Thunder Client

1. `POST http://localhost:3000/products` with the example JSON above.
2. `GET http://localhost:3000/products` to see all products.
3. Copy the `_id` returned by the create request.
4. `GET http://localhost:3000/products/PRODUCT_ID` to retrieve one product.
5. `PUT http://localhost:3000/products/PRODUCT_ID` with an updated JSON body.
6. `DELETE http://localhost:3000/products/PRODUCT_ID` to delete it.

Replace `PRODUCT_ID` with the actual `_id` returned by MongoDB.

## Notes

- `.env` contains local configuration and is excluded from Git.
- Never commit database passwords or private connection strings.
- MongoDB must be available before starting the server.
