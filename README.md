# API Documentation

## Overview

This API provides endpoints to fetch orders and payments data. It requires a valid API key for authorization.

### Base URL

The base URL for accessing the API is https://XXXXXXXXXXXXXXX.

## Endpoints

### Fetch Orders

- **Endpoint:** `/v1/orders`
- **Method:** POST
- **Description:** Fetches orders data based on specified date range.
- **Request Body:**
  - startDate: Start date of the range (DD/MM/YYYY)
  - endDate: End date of the range (DD/MM/YYYY)
  - account: acount number here ex. (41110002)
- **Response:**

  - Status 200: Returns an array of orders with details like order ID, date, pricing breakdown, and total amounts.
  - Status 400: Returns an error if the request is missing required parameters or if the start date is greater than the end date.
  - Status 403: Returns an error if the API key is invalid.
  - Status 500: Returns an error if there is a server-side issue.

  ## Example Response for Orders Endpoint

```json
[
  {
    "id": "000001",
    "date": "2023-03-30T03:03:37.178Z",
    "prime_net": 405000,
    "frais": 40500,
    "total_htva": 445500,
    "tva": 0,
    "total_tvac": 445500
  }
]
```

This is an example response that you can expect when querying the orders endpoint. It includes details such as order ID, date, pricing components, and total amounts.

### Fetch Payments

- **Endpoint:** `/v1/payments`
- **Method:** POST
- **Description:** Fetches payments data based on specified date range.
- **Request Body:**
  - startDate: Start date of the range (DD/MM/YYYY)
  - endDate: End date of the range (DD/MM/YYYY)
- **Response:**
  - Status 200: Returns an array of payments with details like payment status, date, and amount.
  - Status 400: Returns an error if the request is missing required parameters or if the start date is greater than the end date.
  - Status 403: Returns an error if the API key is invalid.
  - Status 500: Returns an error if there is a server-side issue.

## Authentication

To access the API endpoints, include the API key in the request headers as follows:

```
x-api-key: xxxxxxxxxxxxxxxxxxxxxxxs
```

Please ensure to handle errors appropriately based on the response status codes.
