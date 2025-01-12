# Database User Creation Guide

This README explains how to create a new user for a MySQL database and grant them access to a specific database.

### Steps to Create a User and Grant Database Access

1. **Log in to MySQL**
   
   First, log in to MySQL as an administrator or a user with the necessary privileges.

   ```bash
   mysql -u root -p
   ```

1. **Create a New User**
```sql
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
```

3. **Grant Access to the Database**
```sql
GRANT ALL PRIVILEGES ON database_name.* TO 'username'@'localhost';
```

4. **Flush Privileges**
```sql
FLUSH PRIVILEGES;
```

