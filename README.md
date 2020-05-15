<img alt="GoStack" src="https://storage.googleapis.com/golden-wind/bootcamp-gostack/header-desafios.png" />

<h3 align="center">
  Challenge 04: Node.js - Financial Application
</h3>

## :rocket: About the Challenge

Node.js backend created using TypeScript for a financial application that lists transactions previously created either as income or expense.

### Application Routes

- **`POST /transactions`**: The route must get `title`, `value`, and `type` in the request body, where the `type` represents transaction's type that can be either `income` or `outcome (expense)`. When creating a new repository, it should be stored in an object with the following structure:

```json
{
  "id": "uuid",
  "title": "Salário",
  "value": 3000,
  "type": "income"
}
```

- **`GET /transactions`**: The route should list all created transactions along with the balance, which contains the sum of all income, outcome/expenses, and final balance (income - outcome);

```json
{
  "transactions": [
    {
      "id": "uuid",
      "title": "Pay",
      "value": 4000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Freelance work",
      "value": 2000,
      "type": "income"
    },
    {
      "id": "uuid",
      "title": "Credit card",
      "value": 4000,
      "type": "outcome"
    },
    {
      "id": "uuid",
      "title": "Gaming chair",
      "value": 1200,
      "type": "outcome"
    }
  ],
  "balance": {
    "income": 6000,
    "outcome": 5200,
    "total": 800
  }
}
```

### Tests Breakdown

- **`should be able to create a new transaction`**: For this test to pass, the aplication should allow the creation of a transaction and return the transaction created as json.

- **`should be able to list the transactions`**: For this test to pass, the application should return an object with all transactions that have been createad including the balance.

- **`should not be able to create outcome transaction without a valid balance`**: For this test to pass, the application should not allow an expense to be added if its value is greater than the sum of all income, returning a 404 HTTP response and an error message with the following format `{ error: string}`.

### Testing the Application

1. Run `yarn test` to run test suites

## Getting started

1. Clone this repo using `git clone https://github.com/yagosansz/gostack11-challenge01.git`
2. Move yourself to the appropriate directory: `cd gostack11-challenge01`<br />
3. Run `yarn` to install dependencies<br />

### Getting started with the backend server

1. Run `yarn dev:server` to start the server
2. Test the routes by either using [Insomnia](https://insomnia.rest/) or [Postman](https://www.getpostman.com/)

  ---

Made with :heart: by Yago!
