# PostgreSQL Table Operations Documentation

## 1. Create Table

### Syntax:
```sql
CREATE TABLE table_name (
    column1 datatype1 constraints,
    column2 datatype2 constraints,
    ...
);
```

### Example:
```sql
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    hire_date DATE,
    salary NUMERIC(10, 2)
);
```

## Row Operations

### 2. Insert into Row

#### Syntax:
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

#### Example:
```sql
INSERT INTO employees (name, email, hire_date, salary)
VALUES ('Jane Smith', 'jane.smith@example.com', '2023-01-15', 50000);
```

### 3. Update Rows

#### Syntax:
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

#### Example:
```sql
UPDATE employees
SET salary = 55000, email = 'john.doe@example.com'
WHERE id = 1;
```

### 4. Delete Rows

#### Syntax:
```sql
DELETE FROM table_name
WHERE condition;
```

#### Example:
```sql
DELETE FROM employees
WHERE id = 2;
```

## Column Operations

### 5. Add Column

#### Syntax:
```sql
ALTER TABLE table_name
ADD COLUMN column_name datatype constraints;
```

#### Example:
```sql
ALTER TABLE employees
ADD COLUMN department VARCHAR(50);
```

### 6. Delete Columns

#### Syntax:
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

#### Example:
```sql
ALTER TABLE employees
DROP COLUMN department;
```

### 7. Rename Columns

#### Syntax:
```sql
ALTER TABLE table_name
RENAME COLUMN old_column_name TO new_column_name;
```

#### Example:
```sql
ALTER TABLE employees
RENAME COLUMN email TO work_email;
```

### 8. Update Column Type

#### Syntax:
```sql
ALTER TABLE table_name
ALTER COLUMN column_name TYPE new_datatype;
```

#### Example:
```sql
ALTER TABLE employees
ALTER COLUMN salary TYPE NUMERIC(12, 2);
```

Note: When changing column types, make sure the existing data is compatible with the new type. You may need to use USING clause for type conversion in some cases.
