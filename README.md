# HNG Stage 1 DevOps Task

## Number Classification API

A RESTful API that takes a number and returns interesting mathematical properties about it, along with a fun fact. This project was built using Node.js and Express.

## Features

- Determines if a number is prime
- Determines if a number is perfect
- Identifies Armstrong numbers
- Calculates digit sum
- Provides number properties (odd/even, Armstrong)
- Fetches fun facts about numbers from the Numbers API

## Prerequisites

- Node.js
- npm (Node Package Manager)

## Local Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Awesome6192/HNG-Stage-1-DevOps-Interns-Task.git
   cd HNG-Stage-1-DevOps-Interns-Task
   ```

2. Initialize the project:
   ```bash
   npm init -y 
   ```

3. Install dependencies:
   ```bash
   npm install express cors axios
   ```

4. Run the application:
   - For development:
     ```bash
     nodemon server.js
     ```
   - For production:
     ```bash
     npm start
     ```

The API will be available at `http://localhost:5000`.

## API Documentation

### Endpoint

```
GET /api/classify-number?number=<integer>
```

### Request Parameters

| Parameter | Type    | Required | Description                    |
|-----------|---------|----------|--------------------------------|
| number    | integer | Yes      | The number to be classified    |

### Success Response (200 OK)

```json
{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 11,
    "fun_fact": "371 is a narcissistic number." //gotten from the numbers API
}
```

### Error Response (400 Bad Request)

```json
{
    "number": "invalid_input",
    "error": true
}
```

### Properties Field Combinations

The `properties` array can contain the following combinations:
1. `["armstrong", "odd"]` - number is both Armstrong and odd
2. `["armstrong", "even"]` - number is Armstrong and even
3. `["odd"]` - number is only odd
4. `["even"]` - number is only even

## Development

To run the server in development mode with hot reloading:
Run the application:
   - For development:
     ```bash
     nodemon server.js
     ```
   - For production:
     ```bash
     npm start
     ```

## Deployment

This API is deployed on [Render](https://render.com) and can be accessed at: [https://hng-stage-1--devOps-interns-task-chibuzor.onrender.com](https://hng-stage-1--devOps-interns-task-chibuzor.onrender.com)

## Built With

- Node.js - JavaScript runtime
- Express - Web framework
- Axios - HTTP client
- CORS - Cross-Origin Resource Sharing middleware