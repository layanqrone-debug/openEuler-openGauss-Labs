1 Enter to openGauss database 
```bash
/opt/software/bin/gsql -d postgres
```
> `openGauss=#   `

2 Creat a new training user.sql
```bash
CREATE USER lab_user PASSWORD 'LabUser@123';
```
> `CREATE ROLE `

3 User verification.gsql-meta-command
```bash
\du
```
> `
Role name 
omm   `
> `lab_user `

4 Display users registered in database.sql
```bash
SELECT usename FROM pg_user;
```
> `
usename
omm
lab_user
  `

5 Information about (lab_user)privileges
```bash
SELECT rolname, rolsuper, rolcreaterole, rolcreatedb
FROM pg_roles
WHERE rolname = 'lab_user';
```
> `
rolname   | rolsuper | rolcreaterole | rolcreatedb
----------+----------+---------------+------------
lab_user  | f        | f             | f 
`

6 Activating permissions_alter_user.sql
```bash
ALTER USER lab_user SUPERUSER CREATEDB CREATEROLE;
```
> `
ERROR: unrecognized role option "superuser"
`

> [!NOTE]
> **the reason is we used syntax specific to PostgreSQL instead of syntax specific to openGauss.**
```bash
ALTER ROLE
```
> `
Sysadmin, Create role, Create DB
`

7 Verify privileges
```bash
\du lab_user
```
> `
Sysadmin, Create role, Create DB
`

8 Log in to lab_user
```bash
\q
/opt/software/bin/gsql -d postgres -U lab_user -W 'LabUser@123'
```
> `
openGauss=>
`

9 CREATEROLE test
```bash
CREATE ROLE practice_role;
```
> `
ERROR: The password could not be NULL
 `
> [!NOTE]
> ** means that openGauss requires a password when creating a role **

```bash
CREATE ROLE practice_role PASSWORD 'practice@123';
```
> `
CREATE ROLE
 `

10 just checking what we created
```bash
\du practice_role
```
> `
practice_role | Cannot login | {}
 `

> [!NOTE]
> **why cannot login even though we set a password ? Two different things:
PASSWORD → The password to be used if the Role is permitted to log in.
LOGIN → Allows the Role to be used as an account to connect to the database.**

 11 CREATEDB test 
```bash
CREATE DATABASE practice_db;
```
> `
CREATE DATABASE
 `

12 display a list of databases (we should find practice_db)
```bash
\l
```
> `
practice_db | lab_user
 `

> [!NOTE]
> **this mean the  practice_db database created by lab_user now exists**

13 Using the ALTER ROLE to modify role properties to perimtted login 
```bash
ALTER ROLE practice_role LOGIN;
```
> `
ALTER ROLE 
 `

14 exite lab_user then log in using practice_role
```bash
\q
```
 > `
[omm@opengauss ~]$
 `
```bash
/opt/software/bin/gsql -d postgres -U practice_role -W 'practice@123'
```
 > `
openGauss=>
`

