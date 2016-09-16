andrewrothstein.consul-cluster
==============================

Role for configuring a Consul cluster. Relies principally on the existence of two host groups.

consul: all hosts that participate in the cluster whether server or client.
consul-agent-server: all hosts that participate in the RAFT as servers.

Requirements
------------

See [meta/main.yml]

Role Variables
--------------

See [defaults/main.yml]

Dependencies
------------

See [meta/main.yml]

Example Playbook
----------------

inventory.ini
[consul]
host[1:10].test

[consul-agent-server]
host[1:7].test

group_vars/consul-agent-server.yml
consul_agent_bootstrap_expect : 7

playbook.yml
    - hosts: consul
      roles:
         - andrewrothstein.consul-cluster

License
-------

MIT

Author Information
------------------

Andrew Rothstein andrew.rothstein@gmail.com
