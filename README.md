# Express.js Products API

## Setup

1. Clone your repository
2. Run `npm install`
3. Copy `.env.example` to `.env` and set your API key
4. Run `node server.js`
   - Default port: 3000

## Environment Variables

See `.env.example` file.

## Endpoints

### Authentication

All endpoints require header: `x-api-key: <your_api_key>`

### Hello World

- `GET /`  
  **Response:** `"Hello World"`

### Products

- `GET /api/products`  
  List products, supports `category`, `page`, `limit`, `search` query params.

- `GET /api/products/:id`  
  Get product by ID.

- `POST /api/products`  
  Create product.  
  **Body:**  
  ```json
  {
    "name": "Example",
    "description": "Product desc",
    "price": 100,
    "category": "Books",
    "inStock": true
  }
  ```

- `PUT /api/products/:id`  
  Update product.

- `DELETE /api/products/:id`  
  Delete product.

- `GET /api/products/search?name=foo`  
  Search products by name.

- `GET /api/products/stats`  
  Get stats: count by category.

### Example Request

```bash
curl -H "x-api-key: your_api_key" http://localhost:3000/api/products
```

## Error Handling

Errors return JSON with `error` field and appropriate status code.
