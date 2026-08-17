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

7
