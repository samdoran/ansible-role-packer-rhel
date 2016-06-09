Packer RHEL
=========
[![Galaxy](https://img.shields.io/badge/galaxy-samdoran.packer--rhel-blue.svg?style=flat)](https://galaxy.ansible.com/samdoran/packer-rhel)

Configure a RHEL machine to be used as a Vagrant box. Configuration based on [Vagrant box documentation](https://www.vagrantup.com/docs/boxes/base.html).

This role will register with Red Hat, perform configuration and updates, then deregister.

Requirements
------------

Current Red Hat subscription.
Red Hat username and password.

Role Variables
--------------

| Name              | Default Value       | Description          |
|-------------------|---------------------|----------------------|
| `packer_users` | [see `defaults/main.yml` | User accounts to create and passwords to set. |
| `rhn_username` | `{{ lookup('env', 'RHN_USERNAME') }}` | Red Hat Portal username. Looks for an environment variable by default. |
| `rhn_password` | `{{ lookup('env', 'RHN_PASSWORD') }}` | Red Hat Portal password. Looks for an environment variable by default. |
| `packer_services` | [see `defaults/main.yml`] | List of services and their state. |

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: rhel
      roles:
         - samdoran.packer-rhel

License
-------

MIT
