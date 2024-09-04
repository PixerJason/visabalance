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
