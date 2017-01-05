#Authored by Phillip Bailey
.PHONY: all up  ssh d g update

ANSIBLE_GALAXY_ROLES_PATH = ../ansible/roles/galaxy

all:
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

up: ## Vagrant up.
	vagrant up
	vagrant provision

ssh:
	vagrant ssh

stop: ## Stops the vagrant machine
	vagrant halt

d: ## Vagrant destroy.
	vagrant destroy -f
	rm -rf .vagrant/

g: ## Ansible-galaxy pull and installs roles from galaxy.ansible.com
	ansible-galaxy install -r requirements.yml -p $(ANSIBLE_GALAXY_ROLES_PATH)

update: ## Updates the box that is in use in the current Vagrant environment.
		vagrant box update
