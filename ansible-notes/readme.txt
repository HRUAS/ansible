----------------- Ansible Commands ---------------------
ansible-playbook --inventory first-ansible/inventory/vm-setup-playbook/hosts first-ansible/roles/vm-setup-playbook.yml


[vm-hosts]
server1 ansible_host=web2 ansible_connection=ssh ansible_user=root ansible_ssh_pass=Passw0rd
server2 ansible_host=web1 ansible_connection=ssh ansible_user=root ansible_ssh_pass=Passw0rd
server3 ansible_host=web1 ansible_ssh_private_key_file=/home/thor/.ssh/id_rsa ansible_user=root

----------------- Generating ssh keys ------------------
1) Run Command: ssh-keygen
2) Run command: ssh-copy-id user@server
3) Now login without password

---------------- Ansible Varibales ---------------------
