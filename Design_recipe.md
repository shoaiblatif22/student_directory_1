Single Table Design Recipe Template
Copy this recipe template to design and create a database table from a specification.

## 1. Extract nouns from the user stories or specification

# EXAMPLE USER STORY:
# (analyse only the relevant part - here the final line).

As a coach
So I can get to know all students
I want to see a list of students' names.

As a coach
So I can get to know all students
I want to see a list of students' cohorts.
Nouns:

student_name, student_cohort

## 2. Infer the Table Name and Columns

Put the different nouns in this table. Replace the example with your own nouns.

Students	Properties
student_name, student_cohort
Name of the table (always plural): students

Column names: student_name, student_cohort

## 3. Decide the column types.

Here's a full documentation of PostgreSQL data types.

Most of the time, you'll need either text, int, bigint, numeric, or boolean. If you're in doubt, do some research or ask your peers.

Remember to always have the primary key id as a first column. Its type will always be SERIAL.

# EXAMPLE:

id: SERIAL
student_name: text
student_cohort: text

## 4. Write the SQL.

-- EXAMPLE
-- file: albums_table.sql

-- Replace the table name, columm names and types.

CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  student_name text,
  student_year text
);
## 5. Create the table.

psql -h 127.0.0.1 students < students_table.sql
