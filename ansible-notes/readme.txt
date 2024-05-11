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
ansible-varibale-playbook.yml
ansible-playbook --inventory first-ansible/inventory/vm-setup-playbook/hosts first-ansible/roles/ansible-varibale-playbook.yml -v




Below task is incorrect : The error you are encountering is due to the incorrect syntax in the task where you are trying to use the register keyword along with the
debug and command actions in the same task. In Ansible, you cannot have conflicting action statements in the same task.

    - name: Use Register Keyword
      command: echo "{{ fruits_dict['apple'] }}"
      register: apple_price_register_var
      debug:
        msg: "Data stored in Register variable {{ apple_price_register_var.stdout }}"

----------- Correct --------
- name: Use Register Keyword
  command: echo "{{ fruits_dict['apple'] }}"
  register: apple_price_register_var

- name: Display Register Variable
  debug:
    msg: "Data stored in Register variable {{ apple_price_register_var.stdout }}"