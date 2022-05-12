# sql-syntax-challenge

In this challenge, we’re going to practice performing SQL queries. This should help better solidify some concepts that were covered during lecture.

## Assumptions

* You are using Postico
* You installed Postgres with homebrew
* Postgres is currently running on your computer

## Setup

Follow the instructions below before continuing with this challenge.

### Create your database, table, and data

We are creating a `bank` database with a single table (`accounts`) and 8 records. Please follow the instructions below to create a new database with this table and data.

1. Open Postico.
2. Connect to localhost.
3. Click on the `localhost` tab/bar in the upper-left corner.
4. Create a `bank` database.
5. Double-click the `bank` database to use it.
6. Double-click the 'SQL Query' icon to bring up the query window.
7. Paste the following query into the query box to create the `accounts` table and populate it with data. Remember to click the `Execute query` button.

```SQL
CREATE TABLE accounts (
    "id" serial PRIMARY KEY,
    "username" varchar(12) NOT NULL,
    "city" varchar(128),
    "transactions_completed" integer,
    "transactions_attempted" integer,
    "account_balance" numeric(12,2)
);

INSERT INTO accounts (username, city, transactions_completed, transactions_attempted, account_balance)
VALUES ('Shawn', 'Chicago', 5, 10, 355.80),
('Cherise', 'Minneapolis', 9, 9, 4000.00),
('Larry', 'Minneapolis', 3, 4, 77.01),
('Dorothy', 'New York', 6, 12, 0.99),
('Anthony', 'Chicago', 0, 0, 0.00),
('Travis', 'Miami', 10, 100, 500000.34),
('Davey', 'Chicago', 9, 99, 98.04),
('Ora', 'Phoenix', 88, 90, 3.33),
('Grace', 'Miami', 7, 9100, 34.78),
('Hope', 'Phoenix', 4, 10, 50.17);
```

## Base Mode

- Fork this repo
- You will store your responses to the exercise questions in the `database.sql` file. NOTE: This is merely a text file with a .sql extension.
- For each question in the `database.sql` file, write the SQL query that answers the question, below that comment.

### Example question and answer
```
-- 0. How do you get all users?
SELECT * FROM accounts;
```

## Stretch Goal Questions

1. Anthony moved to Santa Fe. Update his location in the table.
2. Grace closed her account. Remove her from the database.
3. Travis made a withdrawal of $20,000. What's their new balance? NOTE: Research `RETURNING`
4. The Bank needs to track last names. NOTE: Research `ALTER TABLE`
5. What is the total amount of money held by the bank? NOTE: Research `SUM`
6. What is the total amount of money held by the bank at each location? NOTE: Research `GROUP BY`
