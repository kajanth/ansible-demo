# Ansible Demo

Easy and quick setup to develop and test Ansible roles.

## Requirements

Ansible: ```pip install ansible```

Vagrant: https://www.vagrantup.com/downloads.html

Vagrant plugins: ```vagrant plugin  install vagrant-hosts```

### Installation

``` git@github.com:p0bailey/ansible-demo.git ```


## Usage

### Centos:


cd ansible-demo/centos7

vim ../ansible/roles/base/tasks/centos.yml

Add the following code into it:

```
- name: Install basic packages
  yum: pkg={{ item }} state=present
  with_items:
    - vim
    - curl
    - git
    - unzip
    - wget
```
save and run ``` make p ```


### Ubuntu:

cd ansible-demo/ubuntu16.04/

vim ../ansible/roles/base/tasks/ubuntu.yml

Add the following code into it:

```
- name: Install base packages
  action: apt pkg={{item}} state=installed
  with_items:
    - vim
    - curl
    - git
    - unzip
    - wget
```
save and run ``` make p ```

### Adding a custom made role.

Module init.

```
cd ../ansible/roles/

ansible-galaxy init --offline <customrolename>
```
Add new module into the playobook i.e CentOS playoobook.


```
---
- name: CentoOS 7.3 Ansible playbook
  hosts: all
  become: yes

  roles:
     #- { role: ../ansible/roles/galaxy/<rolename> } #example of Ansible-Galaxy
     - { role: ../ansible/roles/base }
     - { role: ../ansible/roles/<customrolename> }

```     

Test it with ``` make p ```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D


## Author

Phillip Bailey - phillip@bailey.st

## License
