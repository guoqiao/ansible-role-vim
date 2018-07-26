Ansible Role: vim
=========

This role will:

- clone latest vim code from github, compile and install
- install vimrc file and plugins

Requirements
------------

The target hosts need to have `apt` or `homebrew` to install deb packages.

Role Variables
--------------

Refer to `defaults/main.yml`

Dependencies
------------

None

Example Playbook
----------------

    - name: test role
      hosts: vagrant
      roles:
        - role: vim
          config_src: ~/.vim/vimrc

Also refer to `tests/test.yml`

License
-------

MIT

Author Information
------------------

guoqiao, a Python Developer living in New Zealand.
