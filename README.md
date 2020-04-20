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

DIY On Your Local Ubuntu
-----------------------

```
sudo apt update
sudo apt install software-properties-common
sudo apt-add-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
sudo apt install git
sudo apt install openssh-server
mkdir vim_DIY
cd vim_DIY
git clone https://github.com/pesarkhobeee/ansible-role-vim.git vim
cat >> DIY.yml <<EOF
- name: vim role
  hosts: all
  roles:
    - role: vim
EOF
ansible-playbook -e ansible_python_interpreter=$(which python3) --ask-pass --ask-become-pass -i localhost, DIY.yml
```

License
-------

MIT

Author Information
------------------

guoqiao, a Python Developer living in New Zealand.
