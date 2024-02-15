## 1. Extract nouns from the user stories or specification

```
As a coach
So I can get to know all students
I want to see a list of students' names.

As a coach
So I can get to know all students
I want to see a list of students' cohorts.

```

```
Nouns:

student, name, cohort
```

## 2. Infer the Table Name and Columns

Put the different nouns in this table. Replace the example with your own nouns.

| Record                | Properties          |
| --------------------- | ------------------- |
| student               | name, cohort        |

Name of the table (always plural): `students`

Column names: `student_name`, `cohort`

## 3. Decide the column types

[Here's a full documentation of PostgreSQL data types](https://www.postgresql.org/docs/current/datatype.html).

Most of the time, you'll need either `text`, `int`, `bigint`, `numeric`, or `boolean`. If you're in doubt, do some research or ask your peers.

Remember to **always** have the primary key `id` as a first column. Its type will always be `SERIAL`.

```
id: SERIAL
student_name: text
cohort: text
```

## 4. Write the SQL

```sql
-- file: student_directory_1.sql

-- Replace the table name, columm names and types.

CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  student_name text,
  cohort text
);
```

## 5. Create the table

```bash
psql -h 127.0.0.1 student_directory_1 < students_table.sql
```