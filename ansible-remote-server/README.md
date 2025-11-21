STEP 1 — SSH access to remote server
Your control machine must SSH into the remote EC2.
ssh -i mykey.pem ubuntu@3.110.22.45


STEP 2 — Create inventory file
Create a file named inventory:
[web]
3.110.22.45 ansible_ssh_user=ubuntu ansible_ssh_private_key_file=/home/ubuntu/mykey.pem
Explanation:
web → group name
3.110.22.45 → remote EC2 IP
ansible_ssh_user=ubuntu → default user
ansible_ssh_private_key_file → your .pem key


STEP 3 — Test Ansible connection to remote server
ansible -i inventory web -m ping


STEP 4 — Create a playbook for remote server
- name: Install Nginx on remote server
  hosts: web
  become: yes

  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present
        update_cache: yes

    - name: Start nginx
      service:
        name: nginx
        state: started


STEP 5 — Run the playbook
ansible-playbook -i inventory install_nginx.yml



OUTPUT EXAMPLE:

TASK [Install nginx] 
changed: [3.110.22.45]

TASK [Start nginx] 
ok: [3.110.22.45]

PLAY RECAP
3.110.22.45 : ok=2 changed=1 failed=0
