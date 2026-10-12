# Hybrid Ansible Playbook
This repository contains a simple Ansible playbook that runs on a hybrid local-cloud set-up, where the playbook would update system kernel software and firewalls.
## Introduction and rationale
Having been introduced to the world of AWS, I have chosen to conduct an experimental set-up where I can practically apply the knowledge I gathered pursuing the AWS Systems Architect Associate certification with greater levels of automation than required for the certification itself. I was always bugged by slow, inefficient usage of a GUI to conduct businesses of system administration on AWS, and I wondered if there was a more convenient way to automate repeatable tasks without having to click around and keeping the business logic in my head. This is where I was introduced to Ansible, which at least partly mitigates the hinderance of the dreaded GUI in system administration. Using this playbook, we can automate updating system software (and much more!) without having to type in Bash commands manually every single time. I also wanted to apply my comprehension of the hybrid architecture in systems, and therefore added the additional local node to enrich my proficiency in system administration.
## Architecture
The hybrid architecture involves a controlling node that is hosted via a local VM, alongside another local VM node and a cloud node hosted on AWS EC2:
- **Control Node:** Rocky Linux (Local Management)
- **Managed Node 1:** Rocky Linux VM (VirtualBox)
- **Managed Node 2:** AWS EC2 Instance (RHEL)
- **Automation Tool:** Ansible (SSH key-based authentication)
## Features
- **OS-Aware Package Management and idempotency:** Conditional logic utilizing `ansible_os_family` facts to update DNF/APT repositories dynamically.
- **Service Deployment:** Automated installation, enablement, and execution of Nginx web services.
- **Security Baseline:** Firewalld rules enforcement for HTTP traffic.
- **IAM Integration:** Role-based service access configured on cloud target.
