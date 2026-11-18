# Day 2: Client, Server & REST APIs

## Core Mechanisms
1. **GET Requests:** Used to read data from a server. Endpoints return JSON dictionaries.
2. **POST Requests:** Used to write/send data to a server. We package data into a JSON payload and send it in the request body.
3. **Status Codes:** 
   - `200 OK`: Request succeeded.
   - `201 Created`: Request succeeded and a new resource was created.
   - `404 Not Found`: The endpoint does not exist.
4. **Data Extraction:** APIs return nested JSON. We must use bracket notation (e.g., `data['address']['city']`) to isolate specific variables.