Mongo in Azure

- Find Ubuntu VM with docker and mongo container installed (by Docker)
- Create a VM
- Open ports: Network Interfaces-> Network Security Group
- Connect from shell: mongo  <IP>/
- docker run --name mongo_with_auth_2 -d -p 27017:27017 mongo --auth
- docker exec -it mongo_with_auth_2 mongo admin
- db.createUser({ user: "admin", pwd: "admin", roles: [ { role: "userAdminAnyDatabase", db: "admin" } ] });
- db.auth("admin","admin")
- use myDB
- db.createUser({ user: "user", pwd: "user", roles: [{ role: "dbOwner", db: "myDB" } ] });
- mongo  -u user -p user --host <IP> --authenticationDatabase "myDB"




