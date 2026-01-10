# Create a Table
In this project, you will create your own friends table and add and delete data from it!

### 1. Create a table named friends 
The table friends shall have three columns: id (integer), name (text), birthday (date)
```sql
CREATE TABLE friends (
    id INTEGER,
    name TEXT,
    birthday DATE
);
```

### 2. Add Ororo Munroe to friends.
Her birthday is May 30th, 1940.
```sql
INSERT INTO friends (id, name, birthday)
VALUES (1, 'Ororo Munroe', '1940-05-30');
```

### 3. Let’s make sure that Ororo has been added to the database:
```sql
SELECT * 
FROM friends;
```

We see that the friends table has been created:

![](images/create_a_table_1.png)

We see that Ororo Munroe has been added:

![](images/create_a_table_2.png)

### 4. Add two people to the table.
Adding Jean-Ralphio Saperstein born December 12th, 1985 and Leslie Knope born January 18th, 1975 to the table.

```sql
INSERT INTO friends (id, name, birthday)
VALUES (2, 'Jean-Ralphio Saperstein','1985-12-12');

INSERT INTO friends (id, name, birthday)
VALUES (3, 'Leslie Barbara Knope','1975-01-18');
```
or more efficiently
```sql
INSERT INTO friends (id, name, birthday)
VALUES (2, 'Jean-Ralphio Saperstein','1985-12-12'), (3, 'Leslie Barbara Knope','1975-01-18');
```

### 5. Ororo Munroe just realized that she can control the weather and decided to change her name. Her new name is “Storm”.
Let's update her record in friends.
```sql
UPDATE friends
SET name = 'Storm'
WHERE id = 1;
```

### 6. Add a new column named email.
Set the email datatype to text
```sql
ALTER TABLE friends
ADD COLUMN email TEXT;
```

### 7. Update the email address for everyone in your table.
Storm's email is storm@codecademy.com, Jean-Ralphio's email is swagonyourmom.biz@gmail.com and Lelie's is leslie.knope@pawneecity.gov
```sql
UPDATE friends
SET email = 'storm@codecademy.com'
WHERE id = 1;

UPDATE friends
SET email = 'swagonyourmom.biz@gmail.com'
WHERE id = 2;

UPDATE friends
SET email = 'leslie.knope@pawneecity.gov'
WHERE id = 3;
```
Let see what our table looks like now
```sql
SELECT *
FROM friends;
```
![](images/create_a_table_3.png)

### 8. Wait, Storm is fictional… 
Remove her from friends.
```sql
DELETE FROM friends
WHERE id = 1;
```

### 9. Let’s take a look at the result one last time:
```sql
SELECT *
FROM friends;
```
![](images/create_a_table_4.png)
