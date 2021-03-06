# docker-kerberos

This project is an example MIT Kerberos v5 containerisation.

It is intended for demonstration / learning on a local host and is not production ready. In particular weak passwords are used.

It has the following components:

* compose file: https://github.com/mans0954/docker-kerberos/blob/master/docker-compose.yml
* Kerberos administration server: https://hub.docker.com/r/mans0954/kerberos-kadmin/
* Kerberos version 5 Authentication Service and Key Distribution Center https://hub.docker.com/r/mans0954/kerberos-kdc/

# Run
```
docker-compose up
```

# Administer
```
alias kadmin.example.org="docker exec -ti kadmin kadmin.local"
kadmin.example.org -q "add_principal mans0954@EXAMPLE.ORG"
kadmin.example.org -q "add_principal mans0954/admin@EXAMPLE.ORG"
```
N.B. kadm5.acl is configured so that all principals ending /admin have admin rights

