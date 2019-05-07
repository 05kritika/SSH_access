# SSH_access
Automate the process of granting / revoking SSH access to a group of servers instances to a new developer

PREREQUISITES :-
-------------

Python (for installing ansible), 
Anisble (for running playbooks) 

COMMANDS USED :-
--------------

1. To add new user and grant SSH access    --> ansible-playbook -i inventory/ -e "action=grant" playbooks/ssh.yml
2. To grant SSH access to an existing user --> ansible-playbook -i inventory/ -e "action=grant" playbooks/ssh.yml --skip-tags=add
3. To revoke SSH access from a user        --> ansible-playbook -i inventory/ -e "action=revoke" playbooks/ssh.yml --skip-tags=remove
4. To remove user and revoke SSH access    --> ansible-playbook -i inventory/ -e "action=revoke" playbooks/ssh.yml

NOTE :-
-------

1. Under [instances] group in inventory/hosts files I had added IPs or DNS of target instances.
2. I had created a directory under "sshkeys" of same name as user name and put its SSH pub key (id_rsa.pub) under it.
3. I have used ec2-user in my "ssh.yml" file, As I have tested this on AWS instances as target instances. 
