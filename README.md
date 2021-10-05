ansible-role-pyenv
=========

Installs pyenv, placing the shell source script in ~/commonrc.d

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

Requires the bash config that sets up the commonrc.d  scripts to be sourced
when the shell starts:
```bash
ansible-galaxy install git+https://github.com/natemarks/ansible-role-bash.git,v0.0.21
# OR
ansible-galaxy install git+https://github.com/natemarks/ansible-role-bash.git,main
```

Example Playbook
----------------
```yaml
---
- name: Configure pyenv
  become: false
  hosts: localhost
  gather_facts: true
  connection: local
  roles:
    - ansible-role-pyenv

```

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
