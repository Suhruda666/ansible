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

#Files vs templates:

Files : just copy the files as it is
Templates: Copy the file along with the mentioned variables as a part of the copy

###Ansible roles directory structure:

roles-examples/ 
├── defaults 
│   └── main.yml 
├── files ├── handlers 
│   └── main.yml 
├── meta 
│   └── main.yml 
├── README.md ├── tasks 
│   └── main.yml 
├── templates ├── tests │   ├── inventory 
│   └── test.yml 
└── vars 
    └── main.yml 

##Limitation in this project:

Fronted UI fails  intermittently(which ensure u see no items or display of catalogue)


##Ansible-pull

Whenever the infra is dynamic or not in a position to maintain the static inventory or whenever u want some config-management to happen as a part of boot-strapping, prefer using ansible-pull. Ansible-pull expects ansible to be installed on the machine when you're are running

So, the easiest option is to install the ansible on the lab ami and keep it ready and prefer this AMI with ansible as a base image

eg: ansible-pull -U git_repo_url -e COMPONENT=      -e ENV=     playbook-name.yml