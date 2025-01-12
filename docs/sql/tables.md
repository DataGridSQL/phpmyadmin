# SQL Tables

## Tables with alias
```sql
SELECT 
    email AS "User email", -- everything after as alias will be the alias for the column name
    passwd AS "User password" 
FROM login;
```

## Adding new colums to tables 
```sql
ALTER TABLE login
ADD phone VARCHAR(25) -- add a new column to the table
```

## Get a specifc data from table when employee got fired
```sql
SELECT *
FROM employees
WHERE fire_date BETWEEN '2020-01-01' AND '2020-12-31' -- from 2020 jan 1 to 2020 dec 32
ORDER BY fire_data ASC; -- from old to new
```

## Creating a new table and using a foreign key to link the tables
### Create the Parent Table:
```sql
CREATE TABLE parent_table (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL
);
```
### Create the Child Table with a Foreign Key:
```sql
CREATE TABLE child_table (
    id INT PRIMARY KEY,
    parent_id INT,
    description VARCHAR(255),
    FOREIGN KEY (parent_id) REFERENCES parent_table(id)
);
```
### Insert Data into the Parent Table:
```sql
INSERT INTO parent_table (id, name)
VALUES
    (1, 'Parent One'),
    (2, 'Parent Two');
```
### Insert Data into the Child Table:
```sql
INSERT INTO child_table (id, parent_id, description)
VALUES
    (1, 1, 'Child of Parent One'),
    (2, 2, 'Child of Parent Two');
```

### Query Data from Both Tables:
```sql
SELECT c.id AS child_id, c.description, p.id AS parent_id, p.name AS parent_name
FROM child_table c
JOIN parent_table p ON c.parent_id = p.id;
```
### set new data
```sql
UPDATE parent_table
SET parent_id = 3
where id = 1
```




