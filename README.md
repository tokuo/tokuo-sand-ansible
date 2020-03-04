# SETUP
## managed server side
setup ssh public key authentication

## controle server side
check if it is possible to access managed server
`$ ansible -i inventories/dev/hosts db -m ping`
`$ ansible -i inventories/dev/hosts db -a 'uname -a'`


# USE
`$ ansible-playbook -i inventories/dev/hosts site.yml`


# File, Directory Detail
## .ansible.cfg
Avoiding security risks with ansible.cfg in the current directory  
https://github.com/ansible/ansible/blob/devel/examples/ansible.cfg

## site.yml, playbooks
site.yml is msater playbook  
site.yml import from playbooks

## inventories
this hierarchy represents a "inventory"

## roles
this hierarchy represents a "role"  
https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html


# Reference
https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html
