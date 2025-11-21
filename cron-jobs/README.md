| Task              | Module | Example                    |
| ----------------- | ------ | -------------------------- |
| Add cron          | cron   | `state: present` (default) |
| Remove cron       | cron   | `state: absent`            |
| For specific user | cron   | `user: ubuntu`             |
| Every X minutes   | cron   | `minute: "*/5"`            |
