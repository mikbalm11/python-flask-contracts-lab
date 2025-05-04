# Python Flask Contracts Lab

This lab is a simple Flask application that serves contract and customer data via HTTP endpoints. It includes unit tests to verify the API's behavior.

##  Project Structure

```
python-flask-contracts-lab/
├── server/
│   ├── app.py                # Flask application
│   ├── __init__.py
│   └── testing/
│       └── app_test.py       # Pytest-based test suite
├── Pipfile                   # Pipenv environment file (optional)
├── requirements.txt          # Dependency file (optional)
└── README.md                 # You're here
```

##  Features

* `GET /contract/<id>`: Retrieve contract information by ID.
* `GET /customer/<customer_name>`: Check if a customer exists.
* Includes a test suite using `pytest`.

##  Installation

1. **Clone the repo:**

   ```bash
   git clone <your-repo-url>
   cd python-flask-contracts-lab
   ```

2. **Set up your environment:**

   If using `pyenv` and `pipenv` (Flatiron default):

   ```bash
   pyenv install 3.8.13
   pyenv local 3.8.13
   pipenv install
   pipenv shell
   ```

   If using `venv` and `pip`:

   ```bash
   python3.8 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Fix dependencies (if needed):**

   ```bash
   pip install "Flask==2.0.3" "Werkzeug==2.0.3"
   ```

##  Running the Server

```bash
python server/app.py
```

This starts the Flask server at `http://localhost:5555`.

##  Running Tests

```bash
pytest -x
```

Tests include:

* Valid and invalid contract lookups
* Valid and invalid customer lookups
* Empty 204 responses for existing customers

##  Example API Usage

### `GET /contract/1`

**Response:**

```json
{
  "id": 1,
  "contract_information": "This contract is for John and building a shed"
}
```

### `GET /customer/bob`

**Response:**

* `204 No Content` if customer exists
* `404 Not Found` if not

##  Requirements

* Python 3.8 (recommended: `3.8.13`)
* Flask 2.x
* Werkzeug <2.1
* pytest

##  Notes

* Be sure to use the correct Python version (Flatiron recommends 3.8.x).
* Some newer versions of `Werkzeug` are incompatible with Flask <2.1.
