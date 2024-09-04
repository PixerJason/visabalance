# Flask API for Balance and Statement Retrieval

## Introduction

This project provides a RESTful API built with Flask that allows users to interact with a credit card balance and statement retrieval system. The API supports two primary endpoints:

1. **Balance Check**: Retrieve the current balance of a specified credit card.
2. **Statement Retrieval**: Retrieve the transaction statement for a specified credit card over a given date range.

### Features

- **Authentication**: Secure API access using API keys.
- **Error Handling**: Provides clear error messages for unauthorized access and invalid requests.

### Prerequisites

- Python 3.x
- Flask
- Requests library

Ensure you have these dependencies installed. You can install the required packages using `pip`:

```bash
pip install Flask requests
```
```bash
sudo apt install python3
```

### API USAGE
# Simply using CuRl command For Balance Retreval

```bash
curl -X POST https://getbalance.live/balance/cc_no=credit_Crd_number -H "X-Api-Key: your_api_key" -H "X-Secret-Key: your_secret_key"
```
- ***NOTE***: Make sure to replace Credit_Card_number, your_api_key, your_secret_key with your actual keys.
# Success Response:
```json
{
  "active": true,
  "balance": {
    "401179600635460": "25,317.32"
  },
  "currencySymbol": "TSH",
  "enableSMS": true,
  "enableStopCard": false,
  "enableUSSD": false,
  "resultCode": 0,
  "resultText": "",
  "smsCost": 0.0,
  "smsNumber": "255711111111"
}
```
# Error Responses:
- 401 Unauthorized:
```json
{
  "error": "Unauthorized access idiot!"
}
```
- 400 Bad Request (Invalid cc_no):
```json
{
  "error": "Invalid cc_no. It must be a 16-digit integer."
}
```

### Using Python Requests

```python
import requests

# Replace with your actual values
url = 'https://getbalance.live/balance/cc_no=credit_card_number'
api_key = 'your_api_key'
secret_key = 'your_secret_key'

# Define headers
headers = {
    'X-Api-Key': api_key,
    'X-Secret-Key': secret_key
}

# Send POST request
try:
    response = requests.post(url, headers=headers)
    
    # Raise an exception if the request was unsuccessful
    response.raise_for_status()
    
    # Print the response from the server
    print("Response Status Code:", response.status_code)
    print("Response JSON:", response.json())
except requests.exceptions.RequestException as e:
    print("An error occurred:", e)
```

# Success Response:
```json
{
  "active": true,
  "balance": {
    "401179600635460": "25,317.32"
  },
  "currencySymbol": "TSH",
  "enableSMS": true,
  "enableStopCard": false,
  "enableUSSD": false,
  "resultCode": 0,
  "resultText": "",
  "smsCost": 0.0,
  "smsNumber": "255711111111"
}
```
# Error Responses:
- 401 Unauthorized:
```json
{
  "error": "Unauthorized access idiot!"
}
```
- 400 Bad Request (Invalid cc_no):
```json
{
  "error": "Invalid cc_no. It must be a 16-digit integer."
}
```

### Using Node-Js
- Required
```bash
sudo apt install npm
```
```bash
npm install axios
```
```js
const axios = require('axios');

// Replace with your actual values
const url = 'https://getbalance.live/balance/cc_no=credit_card_number';
const apiKey = 'your_api_key';
const secretKey = 'your_secret_key';

// Define headers
const headers = {
  'X-Api-Key': apiKey,
  'X-Secret-Key': secretKey
};

// Send POST request
axios.post(url, {}, { headers })
  .then(response => {
    console.log('Response Status Code:', response.status);
    console.log('Response Data:', response.data);
  })
  .catch(error => {
    console.error('An error occurred:', error.response ? error.response.data : error.message);
  });

```

# Success Response:
```json
{
  "active": true,
  "balance": {
    "401179600635460": "25,317.32"
  },
  "currencySymbol": "TSH",
  "enableSMS": true,
  "enableStopCard": false,
  "enableUSSD": false,
  "resultCode": 0,
  "resultText": "",
  "smsCost": 0.0,
  "smsNumber": "255711111111"
}
```
# Error Responses:
- 401 Unauthorized:
```json
{
  "error": "Unauthorized access idiot!"
}
```
- 400 Bad Request (Invalid cc_no):
```json
{
  "error": "Invalid cc_no. It must be a 16-digit integer."
}
```


### Using PHP
```php
<?php
// Define the API URL and headers
$url = 'https://getbalance.live/balance/cc_no=credit_card_number';
$apiKey = 'your_api_key';
$secretKey = 'your_secret_key';

// Initialize cURL
$ch = curl_init($url);

// Set cURL options
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Api-Key: ' . $apiKey,
    'X-Secret-Key: ' . $secretKey,
]);

// Execute the POST request
$response = curl_exec($ch);

// Check for errors
if ($response === false) {
    echo 'cURL Error: ' . curl_error($ch);
} else {
    // Display the response
    echo 'Response: ' . $response;
}

// Close the cURL session
curl_close($ch);
?>

```

# Success Response:
```json
{
  "active": true,
  "balance": {
    "401179600635460": "25,317.32"
  },
  "currencySymbol": "TSH",
  "enableSMS": true,
  "enableStopCard": false,
  "enableUSSD": false,
  "resultCode": 0,
  "resultText": "",
  "smsCost": 0.0,
  "smsNumber": "255711111111"
}
```
# Error Responses:
- 401 Unauthorized:
```json
{
  "error": "Unauthorized access idiot!"
}
```
- 400 Bad Request (Invalid cc_no):
```json
{
  "error": "Invalid cc_no. It must be a 16-digit integer."
}
```
