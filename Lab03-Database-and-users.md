1 Enter to openGauss database 
```bash
/opt/software/bin/gsql -d postgres
```
> `openGauss=#   `

2 Creat a new training user (SQL)
```bash
CREATE USER lab_user PASSWORD 'LabUser@123';
```
> `CREATE ROLE `

3 User verification (gsql meta-command)
```bash
\du
```
> `
Role name 
omm   `
> `lab_user `

4 Display users registered in database (SQL)
```bash
SELECT usename FROM pg_user;
```
> `
usename
omm
lab_user
  `
