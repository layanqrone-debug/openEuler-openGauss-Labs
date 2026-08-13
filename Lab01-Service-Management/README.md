objective: learn how to manage the openGauss service state
commands and results
1 switch to the omm user:
```bash
su - omm
```
2 check the initial database status:
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node status
```
result: `no server running`
3 start the openGauss server
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node start
```
result: `server started`
4 verify the database status again 
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node status
```
result: `server is running`
