Rabbitmq [![Build Status](https://travis-ci.org/SimpliField/ansible-rabbitmq.svg?branch=master)](https://travis-ci.org/SimpliField/ansible-rabbitmq) [![Ansible Role](https://img.shields.io/ansible/role/10049.svg?maxAge=2592000)](https://galaxy.ansible.com/SimpliField/rabbitmq/)
=========

Setup rabbitmq

Requirements
------------

Need ansible 2+

Role Variables
--------------

```yaml
rabbitmq_vhosts:
- name:    vhost1
  node:    node_name # Optional, defaults to "rabbit"
  tracing: yes # Optional, defaults to "no"

rabbitmq_users:
- vhost: vhost1
  user: user1
  password: password1
  node: node_name # Optional, defaults to "rabbit"
  configure_priv: "^resource.*" # Optional, defaults to ".*"
  read_priv: "^$" # Disallow reading.
  write_priv: "^$" # Disallow writing.
- vhost: vhost1
  user: user2
  password: password2
  force: no
  tags: # Optional, user tags
  - administrator
rabbitmq_erlang_cookie: mycustomcookie
rabbitmq_erlang_cookie_path: "/var/lib/rabbitmq/.erlang.cookie"
```

Dependencies
------------

This role use :
- [SimpliField.packages](https://github.com/SimpliField/ansible-packages).

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - { role: SimpliField.rabbitmq }
```

License
-------

BSD
