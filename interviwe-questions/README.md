📘 Ansible Interview Questions & Answers (Beginner → Advanced)

This repository contains the most important Ansible interview questions and answers for DevOps, SRE, and Cloud Engineer roles.

📌 Topics Covered

Ansible Basics

Playbooks & Roles

Modules, Tasks, Handlers

Templates & Jinja2

Inventory (Static & Dynamic)

Ansible Vault

Advanced Production Concepts

Ansible Tower / AWX


🔰 Beginner Level Q&A
1. What is Ansible?

Ansible is an open-source automation, configuration management, and orchestration tool. It is agentless and uses SSH/WinRM.

2. Why is Ansible agentless?

No need to install software on remote servers; uses SSH.

3. What is Inventory?

A file containing hosts and groups to automate. Default: /etc/ansible/hosts.

4. What is a Playbook?

A YAML file containing plays and tasks.

5. What is a Task?

A single automation step executed by a module.

🔹 Intermediate Q&A
9. What is a Role?

A structured directory for organizing tasks, handlers, templates, vars, and files.

11. What is a Handler?

A task triggered by notification (e.g., restart service).

12. What is Idempotency?

Running a playbook multiple times results in the same state.

17. How to secure passwords?

Using Ansible Vault.

🔥 Advanced Q&A
21. What is Ansible Tower/AWX?

A UI providing RBAC, scheduling, and centralized logging.

22. What is Dynamic Inventory?

Inventory generated from cloud providers like AWS, Azure, GCP, Kubernetes.

25. What are Block/Rescue/Always?

Error handling similar to try/catch/finally.

33. What is Serial?

Used for rolling updates.

🏁 Summary

This repository helps with:
✔ DevOps interviews
✔ Refreshing Ansible concepts
✔ Understanding production-level Ansible usage



