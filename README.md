Packer RHEL
=========

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
| `rhsm_username` | `{{ lookup('env', 'RHSM_USERNAME') }}` | Red Hat Portal username. Looks for an environment variable by default. |
| `rhsm_password` | `{{ lookup('env', 'RHSM_PASSWORD') }}` | Red Hat Portal password. Looks for an environment variable by default. |
| `rhsm_pool_ids` | `{{ lookup('env', 'RHSM_POOL_ID }}` | Red Hat pool IDs to attach |
| `packer_services` | [see `defaults/main.yml`] | List of services and their state. |

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: rhel
      roles:
         - samdoran.packer_rhel

License
-------

Apache 2.0
