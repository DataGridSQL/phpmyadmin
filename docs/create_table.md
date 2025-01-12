# How to Create a Simple Table in MySQL

## Step 1: Create a Simple Table

To create a table named `users` in the database, run this command:

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

This table includes the following columns:
- `id`: A unique identifier for each user.
- `name`: The name of the user.
- `email`: The user's email address, which must be unique.
- `created_at`: The timestamp when the record was created, with a default value of the current time.

Your table is now ready to store data!