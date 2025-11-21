| Task              | Module         | Notes                                     |
| ----------------- | -------------- | ----------------------------------------- |
| Create user       | user           | `state: present`                          |
| Delete user       | user           | `state: absent`                           |
| Add/remove groups | user           | `groups:` / `append: yes`                 |
| Password          | user           | Must be **hashed**                        |
| Add SSH key       | authorized_key | Adds public key to `.ssh/authorized_keys` |
