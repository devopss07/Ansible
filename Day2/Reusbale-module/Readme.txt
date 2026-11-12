Ansible Galaxy:  It is used to create Roles.
Roles: Roles are reusable template for playbook, WE CAN USE ROLE WITHIN PLAYBOOK,
INSTED OF WRITING SMAE TASK AGAIN AND AGAIN 

              Ansible Galaxy and Roles
---------------------------------------------------------------------------------
1. What is Ansible Galaxy?
Ansible Galaxy is a tool provided by Ansible that allows us to create, install, and manage Ansible Roles.

We can use it to:
- Create a new role directory structure.
- Install reusable roles created by other users.
- Share our own roles with others.

2. What are Ansible Roles?
Roles are a way to organize Ansible Playbooks into reusable and structured components.

Instead of writing all tasks in a single playbook, we can organize them into separate roles.
For example, we can create:
- A Docker role to install Docker.
- An Nginx role to install Nginx.
- A MySQL role to install MySQL.
We can then reuse these roles in multiple playbooks without writing the same tasks again.

3. Creating a Docker Role Using Ansible Galaxy
Let's create a reusable role to install Docker using Ansible.

Command:
ansible-galaxy init roles/docker


Explanation:
- ansible-galaxy: Ansible's tool for managing roles.
- init: Initializes a new role directory structure.
- roles/: The parent directory where we want to create our role.
- docker: The name of our role.