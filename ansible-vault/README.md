| Command                 | Usage                              |
| ----------------------- | ---------------------------------- |
| `ansible-vault create`  | Create new encrypted file          |
| `ansible-vault edit`    | Edit encrypted file                |
| `ansible-vault view`    | View encrypted file                |
| `ansible-vault encrypt` | Encrypt existing file              |
| `ansible-vault decrypt` | Decrypt file                       |
| `--ask-vault-pass`      | Run playbook with vault password   |
| `--vault-password-file` | Automate vault password file usage |




Step 1 — Create Vault file for AWS credentials

ansible-vault create aws_credentials.yml



Step 2 — Create the EC2 Provisioning Role

ansible-galaxy init roles/ec2_provision



Step 3 — Add main task file

roles/ec2_provision/tasks/main.yml



Step 4 — Create main playbook to call role

playbooks/launch_ec2.yml



Step 5 — Run the playbook
ansible-playbook -i inventory.ini playbooks/launch_ec2.yml --ask-vault-pass




