ansible-role-sublimetext
========================
[![Build Status](https://travis-ci.org/vaulttec/ansible-role-sublimetext.svg?branch=master)](https://travis-ci.org/vaulttec/ansible-role-sublimetext)

Ansible role to install [Sublime Text 3](https://www.sublimetext.com/3) from tarball and configure a desktop shortcut.


Requirements
------------

None


Role Variables
--------------

Available variables are listed below, along with default values:

```yaml
# Sublime Text build number
sublimetext_build: 3114

# Sublime Text tarball is extracted here
sublimetext_dest: /opt/

# A sym-link with this name is created in '/usr/bin/' pointing to the exec 'sublime_text'
sublimetext_link_name: sublime
```


Dependencies
------------

None


Example Playbook
----------------

Install Sublime Text build 3114 into `/opt/` and create a sym-link named `sublime`:

```yaml
- hosts: desktop
  roles:
     - vaulttec.sublimetext
```

Install Sublime Text build 313 into `/usr/local/` and create a sym-link named `subl`:

```yaml
- hosts: desktop
  roles:
     - { role: vaulttec.sublimetext, sublimetext_build: 3103, sublimetext_dest: /usr/local/, sublimetext_link_name: subl }
```


Testing
-------

```bash
cd tests && vagrant up
```


License
-------

MIT