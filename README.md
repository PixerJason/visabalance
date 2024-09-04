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
