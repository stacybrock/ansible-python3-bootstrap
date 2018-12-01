# ansible-python3-bootstrap

Bootstrap a Python 3 environment on CentOS or Debian

The `install` role will build a Python 3 environment for an unprivileged user using [pyenv](https://github.com/pyenv/pyenv). If the user does not exist, the playbook will create it.

This playbook has been tested with the following:
* Ansible 2.7.x
* Debian 8
* CentOS 7

## Configuration

1. Create a file in `inventory/` containing the host(s) to configure. An example is provided in `inventory/example-dist`
1. Create a file in `group_vars/` with the configuration for the environment. An example is provided in `group_vars/example-dist`

```
common:
  create_user: changeme
  user_home: /home/changeme
  python_version: 3.7.1
pyenv:
  version: v1.2.8
  virtualenvwrapper_plugin_version: v20140609
```

* `common.create_user` - name of user account to create
* `common.user_home` - homedir of user account to create
* `common.python_version` - version of Python to install; see [this list](https://github.com/pyenv/pyenv/tree/master/plugins/python-build/share/python-build) for possibilities
* `pyenv.version` - version of pyenv to install
* `pyenv.virtualenvwrapper_plugin_version` - version of [pyenv-virtualenvwrapper](https://github.com/pyenv/pyenv-virtualenvwrapper) to install

## Running the Playbook

```
$ ansible-playbook -i inventory/dev install.yml
```
