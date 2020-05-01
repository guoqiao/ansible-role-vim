Ansible Role: vim
=========

This role will:

- clone latest vim code from github, compile and install
- install vimrc file and plugins

Requirements
------------

The target hosts need to have `apt` to install deb packages.

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

DIY On Your Local Ubuntu
-----------------------

```
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
sudo apt install git
mkdir vim_DIY
cd vim_DIY
git clone https://github.com/DevopsishFriends/DevopsishVim.git
cat >> DIY.yml <<EOF
- name: vim role
  hosts: 127.0.0.1
  connection: local
  roles:
    - role: DevopsishVim
EOF
ansible-playbook -e ansible_python_interpreter=$(which python3)  --ask-become-pass -i localhost, DIY.yml
```

ToDo
----

* Do not let Ansible clone the VIM source if the latest version is already cloned

License
-------

MIT

Authors Information
------------------

* https://github.com/guoqiao
* https://github.com/pesarkhobeee

