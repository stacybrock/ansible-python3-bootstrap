# ansible-python3-bootstrap

Bootstrap a python3 environment on CentOS

This playbook will build a Python 3 environment for an unprivileged user using [pyenv](https://github.com/pyenv/pyenv). If the user does not exist, the playbook will create it.

## Configuration

1. Create a file in `inventory/` containing the host(s) to configure. An example is provided in `inventory/example-dist`
1. Create a file in `group_vars/` with the configuration for the environment. An example is provided in `group_vars/example-dist`

```
common:
  create_user: changeme
  user_home: /home/changeme
  python_version: 3.7.1
```

## Running the Playbook

```
$ ansible-playbook -i inventory/dev install.yml
```
