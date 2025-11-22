| Goal                        | Solution                     |
| --------------------------- | ---------------------------- |
| Run entire playbook as root | `become: yes` under the play |
| Run only 1 task as root     | `become: yes` under the task |
| Run as specific user        | `become_user: root`          |
| Sudo with password          | `become_pass:` + Vault       |
