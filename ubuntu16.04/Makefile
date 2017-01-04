#Authored by Phillip Bailey
.PHONY: all u p ssh d g

ANSIBLE_GALAXY_ROLES_PATH = ../ansible/roles/galaxy

all:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'


u: ## Vagrant up.
	vagrant up
	vagrant provision

p: ## Vagrant provision
	vagrant provision
ssh:
	vagrant ssh

d: ## Vagrant destroy.
	vagrant destroy -f

g: ## Ansible-galaxy pull and installs roles from galaxy.ansible.com
	ansible-galaxy install -r requirements.yml -p $(ANSIBLE_GALAXY_ROLES_PATH)
