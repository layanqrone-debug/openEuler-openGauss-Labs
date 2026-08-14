1 Enter to database 
```bash
/opt/software/bin/gsql -d postgres
```
> `openGauss=#`
```bash
SELECT current_database();
```
> `postgres`
2 command to list the existing database
```bash
\l
```
> `finance 
> postgres
> school
> template0
> template1
>(5 rows)
> all owned by the user omm`
3 Enter to school database
```bash
\c school
```
> `You are now connected to database "school" as user "omm".`
4 display the schemas in school database
```bash
\dn
```
> `blockchain
 cstore
 db4ai
 dbe_perf
 dbe_pldebugger
 dbe_pldeveloper
 dbe_sql_util
 pkg_service
 public
 snapshot
 sqladvisor`
5 see tables inside public
```bash
\dt public
```
> `class
  course
  school_department
  student
  teacher`
