andrewrothstein.consul_cluster
==============================
![Build Status](https://github.com/andrewrothstein/ansible-consul_cluster/actions/workflows/build.yml/badge.svg)

Role for configuring a [Consul](https://www.consul.io/) cluster. Relies principally on the existence of two host groups.

1. consul: all hosts that participate in the cluster whether server or client.
2. consul_servers: all hosts that participate in the RAFT as servers.

Requirements
------------

See [meta/main.yml](meta/main.yml)

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml)

Dependencies
------------

See [meta/main.yml](meta/main.yml)

Example Playbook
----------------

example inventory.ini
```ini
host[1:10].test

[consul]
host[1:10].test

[consul_servers]
host[1:7].test
```

playbook.yml
```yml
- hosts: consul
  roles:
    - andrewrothstein.consul_cluster
```

License
-------

MIT

Author Information
------------------

Andrew Rothstein <andrew.rothstein@gmail.com>
