# API Documentation

## Base URL

```
http://localhost:5000/api
```

## Authentication Endpoints

### Register

```http
POST /auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "phone": "+971501234567"
}
```

**Response:**

```json
{
  "message": "User registered successfully",
  "token": "eyJhbGc...",
  "user": {
    "id": "507f1f77bcf86cd799439011",
    "name": "John Doe",
    "email": "john@example.com"
  }
}
```

### Login

```http
POST /auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

## Product Endpoints

### Get All Products

```http
GET /products?category=Electronics
```

### Get Product by ID

```http
GET /products/{productId}
```

### Search Products

```http
GET /products/search/{query}
```

## Price Comparison

### Compare Prices

```http
GET /prices/compare/{productId}
```

**Response:**

```json
{
  "product": {
    "id": "507f1f77bcf86cd799439011",
    "name": "Samsung Galaxy S21",
    "image": "https://...",
    "category": "Electronics"
  },
  "prices": [
    {
      "store": "Noon",
      "price": 2299,
      "currency": "AED",
      "url": "https://noon.com/..."
    },
    {
      "store": "Talabat",
      "price": 2450,
      "currency": "AED",
      "url": "https://talabat.com/..."
    }
  ],
  "cheapestOption": {
    "store": "Noon",
    "price": 2299
  },
  "savings": 151
}
```

## Cart Endpoints

### Get Cart

```http
GET /cart/{userId}
```

### Add to Cart

```http
POST /cart/{userId}/add
Content-Type: application/json

{
  "productId": "507f1f77bcf86cd799439011",
  "store": "Noon",
  "price": 2299,
  "quantity": 1
}
```

## User Endpoints

### Get User Profile

```http
GET /users/{userId}
```

### Update User Profile

```http
PUT /users/{userId}
Content-Type: application/json

{
  "name": "Jane Doe",
  "phone": "+971501234567",
  "preferences": {
    "notificationsEnabled": true,
    "favoriteStores": ["Noon", "Talabat"]
  }
}
```
