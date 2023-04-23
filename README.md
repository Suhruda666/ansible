# ansible

#Ansible manual command : Using this, we can execute one command at a time

ansible all -i inventory -e ansible_user=centos -e ansible_password=xyz123 -m shell -a uptime

-i inventory file
-e extra or environment variables
ansible_user speacial variable name for the user account to use
ansible_password speacial variable name for the user-account-password to use
-m module

###Ansible command that we are using to call the playbook

ansible_playbook -i inv-dev -e ansible_user=centos -e ansible_password=DevOps321 -e COMPONENT=mongodb robot.yml