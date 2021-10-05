# ansible-role-bash

This role configures the current user's home directory for bash. ~/.bashrc
sources ~/.bashrc.local, which in turn sources all of the files in ~/bashrc.d
and ~/commonrc.d. ~/commonrc.d contains scripts that are compatible with your
other shells (zsh, fish, etc.).

The role also installs powerline and the powerline git plugin and
configures the bash shell to use it.

## gnome terminal colors
Terminal colors are not managed by this role, but here are some link
suggestions.

This is a good site for Gnome Terminal color schemes
https://mayccoll.github.io/Gogh/
I like Afterglow

This one has them for Mac :
https://iterm2colorschemes.com/
## Managed files
This roll will overwrite your changes to the managed files, but will also back
them up when it does so
## Requirements


Install python3 and ansible on Ubuntu
```shell
sudo apt install -y curl
bash -c 'curl "https://raw.githubusercontent.com/natemarks/pipeline-scripts/v0.0.23/scripts/setup_ansible.sh" | sudo bash -s'
```

The role takes a local user account as the target, so if you created the spiderman local account like this, 'spiderman'
would be the desktop_user variable
```shell
# 
sudo useradd "spiderman" -s /bin/bash -m -d "/home/spiderman"
sudo usermod -aG sudo "spiderman"
sudo passwd spiderman
```

## Installation

It can be installed using the ansible-galaxy command:
```shell
# Install from command line:
ansible-galaxy install git+https://github.com/natemarks/ansible-role-bash.git,v0.0.21
ansible-galaxy install git+https://github.com/natemarks/ansible-role-bash.git,simplify


# install from ansible_requirements.yml:
- name: ansible-role-bash
  src: https://github.com/natemarks/ansible-role-bash
  version: v0.0.21
```


Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Run the example playbook with the -K option to prompt for the sudo password

```shell
ansible-playbook example_playbook.yml -K
```
NOTE: you'll be prompted for the sudo password, then the local account to configure. In the example below, I configure it for the 'parallels' account
![](images/ar-bash-001.png)
After the playbook finishes, completely close the terminal and re-open. I cloned this project to show the git status:
![](images/ar-bash-002.png)
License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
