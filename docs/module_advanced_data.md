# Advanced Data module

## General SQL

### What are relational databases? Explain the theory behind them!

    A relational database is a type of database that stores and provides access to data points that are related to one another.
    Relational databases are based on the relational model, an intuitive, straightforward way of representing data in tables.
    In a relational database, each row in the table is a record with a unique ID called the key.
    The columns of the table hold attributes of the data, and each record usually has a value for each attribute, making it easy to establish the relationships among data points.

### Why SQL is important these days?

    It’s not something surprising as SQL is particularly effective at data manipulation. You can be able to see the exact data and the way
    it works then data testing and manipulating will be done faster. Evenmore, the data stored in a relational database is dynamic,
    which means it can be queried, modified, and manipulated easily with some basic SQL queries.

### All the new GUI tools enable me to click a button to write SQL. Why should I spend time learning to write SQL manually?

### If SQL is standardized, should you be able to program with SQL on any databases?

    If relational database the, yes.

### What makes SQL a nonprocedural language?

    SQL is not a procedural language but a declarative language. You write a single SQL declaration and hand it to the DBMS.
    The DBMS then executes internal code, which is hidden from us. The DBMS returns a set, which is a group of data that is somehow defined.

### What can you do with SQL?

    SQL can execute queries against a database
    SQL can retrieve data from a database
    SQL can insert records in a database
    SQL can update records in a database
    SQL can delete records from a database
    SQL can create new databases
    SQL can create new tables in a database
    SQL can create stored procedures in a database
    SQL can create views in a database
    SQL can set permissions on tables, procedures, and views

---

## DQL

### Do the following statements return the same or different output? Why?

    ```sql
    SELECT * FROM CHECKS;
    select * from checks;
    ```

### The following queries do not work when entered into the command line psql console. Why not?

    ```sql
    Select *
    Select * from checks
    Select amount name payee FROM checks;
    ```

    To use multiple SELECT statements in one query we need to use union and put the statements in parentheses.

### What shorthand could you use instead of `WHERE a >= 10 AND a <=30`?


    ```sql
    WHERE a BETWEEN 10 AND 30
    ```

### Which function capitalizes the first letter of a character string and makes the rest lowercase?

    INITCAP()

### Will this query work? Why?

    ```sql
    SELECT COUNT(LASTNAME) FROM CHARACTERS;
    ```

    Yes, the COUNT function counts the lines not the values.

### Assuming that they are separate columns, which function(s) would splice together FIRSTNAME and LASTNAME?

    CONCAT() or the operator || or CONCAT_WS()

### Why are so few functions defined in the ANSI standard and so many defined by the individual implementations?

### What is the function of the GROUP BY clause?

    The PostgreSQL GROUP BY clause is used to divide rows returned by SELECT statement into different groups.
    The specialty of GROUP BY clause is that one can use Functions like SUM() to calculate the sum of items or COUNT() to get the total number of items in the groups.

### When using the HAVING clause, do you always have to use a GROUP BY also?

    Yes. The HAVING clause allows us to pick out particular rows where the function's result meets some condition.
    The WHERE clause places conditions on the selected columns, whereas the HAVING clause places conditions on groups created by the GROUP BY clause.

### Can you use ORDER BY on a column that is not one of the columns in the SELECT statement?

    Yes, you can order by a field(s)even if it is not your in your select statement but exists in your table.

---

## Joins

### Explain the different kind of joins! (outer, inner, left, right, natural, etc.)

    INNER JOIN statement returns only those records or rows that have matching values and is used to retrieve data that appears in both tables.
    The LEFT OUTER JOIN gives the output of the matching rows between both tables. In case, no records match from the left table, it shows those records with null values.
    The RIGHT OUTER JOIN works by the same principle as the LEFT OUTER JOIN. The RIGHT OUTER JOIN selects data from the right table (Table B) and matches this data with the rows from the left table (Table A). The RIGHT JOIN returns a result set that includes all rows in the right table, whether or not they have matching rows from the left table. In case, a row in the right table does not have any matching rows in the left table, the column of the left table in the result set will have nulls.
    The SELF JOIN allows you to join a table to itself. This implies that each row of the table is combined with itself and with every other row of the table. The SELF JOIN can be viewed as a join of two copies of the same table. The table is not actually copied, but SQL performs the command as though it were. This is accomplished by using table name aliases to give each instance of the table a separate name. It is most useful for extracting hierarchical data or comparing rows within the same table.
    The CROSS JOIN command in SQL, also known as a cartesian join, returns all combinations of rows from each table. Envision that you need to find all combinations of size and color. In that case, a CROSS JOIN will be an asset. Note, that this join does not need any condition to join two tables. In fact, CROSS JOIN joins every row from the first table with every row from the second table and its result comprises all combinations of records in two tables.
    The SQL NATURAL JOIN is a type of JOIN and is structured in such a way that, columns with the same name of associated tables will appear once only.

### How many tables can you join on?

    As much as your computing power and time allows.

### Would it be fair to say that when tables are joined, they actually become one table?

    No but we can create a temporary table from the results.

### How many rows would a two-table join produce if one table had 50,000 rows and the other had 100,000?

    Between 50,000 and 100,000 but it depends on what type of join we use and the match between the rows in the table.

### What type of join appears in the following SELECT statement?

    ```sql
    select e.name, e.employee_id, ep.salary  
    from employee_tbl e, employee_pay_tbl ep  
    where e.employee_id = ep.employee_id;
    ```
    Inner join

### In joining tables are you limited to one-column joins, or can you join on more than one column?

    Yes.

---

## DML

### Does SQL have a statement for file import/export operations?

### Can you copy data from a table into itself using the INSERT command? You would like to make duplicate copies of all the existing records and change the value of one field.

### What would happen if you issued the following statement?

    ```sql
    DELETE * FROM COLLECTION;
    ```

### Can you remove columns with the ALTER TABLE statement?

    ALTER TABLE table_name DROP COLUMN column_name

### Is the DROP TABLE command functionally equivalent to the DELETE FROM <table_name> command?

### What is the difference between the functionality of the DELETE FROM <table_name> and the TRUNCATE TABLE command?

### When a table is created, who is the owner?

### If data in a character column has varying lengths, what is the best choice for the data type?
