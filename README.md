# Roboshop Deployment using Ansible

This repository demonstrates the automation of deploying the **Roboshop microservices application** using Ansible.

The project showcases how Infrastructure as Code (IaC) can be used to provision, configure, and deploy a complete multi-service application efficiently across multiple servers.

---

## Project Overview

Roboshop is a **microservices-based e-commerce application** consisting of multiple services such as:

- Web (Frontend)
- Catalogue
- User
- Cart
- Shipping
- Payment
- Dispatch

Each service is configured and deployed using **Ansible roles and playbooks**, enabling automated and repeatable infrastructure setup.

---

## Architecture

- Each microservice runs on a separate server or instance
- Databases like MongoDB, MySQL, and Redis support backend services
- Ansible automates:

  - Package installation
  - Service configuration
  - Application deployment

---

## Tech Stack

- Ansible
- Linux
- YAML (Playbooks & Roles)
- SSH (Agentless communication)
- Git & GitHub

---

## Key Features

- Fully automated deployment using Ansible
- Modular structure using roles
- Scalable and reusable automation scripts
- Real-world microservices deployment

---

## Setup & Execution
### Install Ansible

```
sudo apt update
sudo apt install ansible -y
```

---

### Configure Inventory

Edit inventory file:
```
[web]
<web-server-ip>

[catalogue]
<catalogue-server-ip>

[db]
<mongodb-ip>
```


### Verify Connectivity

```
ansible all -m ping
```

---
### Run Playbook

```
ansible-playbook -i inventory/hosts playbooks/main.yml
```

---

## Example Role Task

```
- name: Install Nginx
  apt:
    name: nginx
    state: present

- name: Start Nginx
  service:
    name: nginx
    state: started
    enabled: yes
```

---

## Learning Outcomes

Through this project, I gained hands-on experience in:

- Automating infrastructure using Ansible
- Writing reusable roles and playbooks
- Managing multi-tier applications
- Understanding real-world deployment workflows

---

## 🔮 Future Enhancements

- Integrate with CI/CD pipelines (GitHub Actions / Jenkins)
- Deploy on AWS EC2 instances
- Add monitoring (Prometheus & Grafana)
- Convert setup to Kubernetes-based deployment

---

## Note

This project is created for learning and demonstrating real-world DevOps practices using Ansible and microservices architecture.

