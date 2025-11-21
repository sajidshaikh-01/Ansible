| Task               | Module | Example            |
| ------------------ | ------ | ------------------ |
| Create file        | file   | `state: touch`     |
| Create directory   | file   | `state: directory` |
| Delete file        | file   | `state: absent`    |
| Delete directory   | file   | `state: absent`    |
| Change permissions | file   | `mode: '0755'`     |
| Change owner/group | file   | `owner: ubuntu`    |
| Copy files         | copy   | earlier example    |
