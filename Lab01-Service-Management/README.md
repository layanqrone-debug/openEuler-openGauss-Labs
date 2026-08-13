objective: learn how to manage the openGauss service state
commands and results
1 switch to the omm user
```bash
su - omm
```
2 check the initial database status
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
5 server shutdown test
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node stop
```
result: `server stopped`
6 check the status
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node status
```
result: `no server running`
7 start the server again 
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node start
```
result: `server started`
```bash
/opt/software/bin/gs_ctl -D /opt/software/data/single_node status
```
result: `server is running`
