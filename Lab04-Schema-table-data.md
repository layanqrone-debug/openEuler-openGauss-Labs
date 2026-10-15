1 create schema 
```bash 
CREATE SCHEMA lab04;
```
>` CREATE SCHEMA `

2 verify
```bash
SELECT schema_name
FROM information_schema.schemata
WHERE schema_name = 'lab04';
```
>` 1 row`

3 create table 
```bash 
CREATE TABLE lab04.student (
    studend_id INT PRIMARY KEY,
    student_name VARCHAR(50),
    age INT,
    major VARCHAR(50)
);
```
>` CREATE TABLE`

4 verify
```bash
\d lab04.students
```
5 correction
```bash
ALTER TABLE lab04.student
RENAME COLUMN studend_id TO student_id;
```
>`ALTER TABLE`

6 insert values
```bash
INSERT INTO lab04.student
    (student_id, student_name, age, major)
VALUES
    (1, 'Layan', 21, 'MIS'),
    (2, 'Sara', 22, 'Computer Science'),
    (3, 'Maya', 20, 'Business');
```
>`INSERT 0 3`

7 
