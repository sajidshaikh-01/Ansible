# What is Ansible?

Ansible is an **open-source configuration management, automation, and orchestration tool** used to configure servers, deploy applications, and automate IT tasks.

It uses **YAML-based playbooks** and works in an **agentless** manner using **SSH (Linux)** or **WinRM (Windows)**.

---

# Why We Use Ansible (Real-World Reason)

In real environments, managing servers manually is:

* Error-prone ❌
* Time-consuming ❌
* Not scalable ❌

Ansible solves this by:

* Automating repetitive tasks
* Ensuring consistency across servers
* Reducing human errors
* Speeding up deployments

### Common Use Cases

* Install & configure software (Nginx, Docker, Java)
* Application deployments
* Patch management & OS hardening
* Configuration drift correction
* Zero-downtime deployments
* Post-infrastructure configuration (after Terraform)

---

# Ansible Architecture (Simple & Clear)

Ansible follows a **push-based** architecture.

## Core Components

### 1. Control Node

* Machine where Ansible is installed
* Runs playbooks
* Pushes configurations to target nodes

### 2. Managed Nodes

* Servers being managed (EC2, VMs, On-Prem, Containers)
* No agent required
* Uses SSH/WinRM

### 3. Inventory

* List of target hosts
* Can be static or dynamic (AWS, Azure, GCP)

Example:

```ini
[web]
server1
server2
```

### 4. Playbooks

* Written in YAML
* Describe **what state** the system should be in

Example:

```yaml
- hosts: web
  become: yes
  tasks:
    - name: Install nginx
      apt:
        name: nginx
        state: present
```

### 5. Modules

* Prebuilt units of work
* Examples: apt, yum, service, copy, file

### 6. Roles

* Structured way to organize playbooks
* Used in production

---

# How Ansible Works (Flow)

1. Engineer runs `ansible-playbook`
2. Control node reads inventory
3. Uses SSH to connect to managed nodes
4. Executes modules
5. Ensures desired state is achieved

---

# Difference Between Ansible and Terraform (Interview Important)

| Feature          | Ansible                  | Terraform                   |
| ---------------- | ------------------------ | --------------------------- |
| Purpose          | Configuration Management | Infrastructure Provisioning |
| Type             | Procedural + Declarative | Declarative                 |
| Agent            | Agentless                | Agentless                   |
| State Management | No state file            | Uses state file             |
| Best For         | OS & App configuration   | Cloud resource creation     |
| Language         | YAML                     | HCL                         |
| Execution        | Push-based               | Plan → Apply                |
| Drift Detection  | Limited                  | Strong                      |

---

# When to Use Ansible vs Terraform (Production Rule)

### Use Terraform When:

* Creating infrastructure (EC2, VPC, S3, RDS)
* Managing cloud resources
* Need dependency tracking & rollback

### Use Ansible When:

* Installing software
* Configuring servers
* Deploying applications
* Managing OS-level changes

### Real Production Workflow

```text
Terraform → Creates EC2, VPC, ALB
Ansible   → Configures EC2 (Nginx, Docker, App)
```

---

# Why Not Use Shell Scripts Instead of Ansible?

| Shell Script        | Ansible                 |
| ------------------- | ----------------------- |
| No idempotency      | Idempotent              |
| Hard to maintain    | Easy to maintain        |
| No inventory        | Inventory support       |
| Poor error handling | Built-in error handling |

-

