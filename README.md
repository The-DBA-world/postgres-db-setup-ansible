PostgreSQL Database Setup with Ansible
This repository contains Ansible playbooks for automating the setup and management of PostgreSQL databases on RHEL 8.10. The playbooks are designed to be dynamic, using variables defined in the inventory-configuration directory.
Project Structure
/postgres-db-setup-ansible
├── inventory-configuration/
│   └── myhost1.yml        # Variable file for myhost1 server
├── inventory              # Ansible inventory file
├── 01-pgsql-init-binaries.yml  # Playbook to initialize PostgreSQL binaries
└── README.md              # Project documentation

Prerequisites

RHEL 8.10 with access to rhel-8-appstream-rpms repository.
Ansible installed on the control node.
SSH access to target hosts (myhost1).
Red Hat Subscription Manager configured for repository access.

Usage

Clone the repository:
git clone https://github.com/The-DBA-world/postgres-db-setup-ansible.git
cd postgres-db-setup-ansible


Update the inventory file with your host details (e.g., SSH user, key, or port).

Modify inventory-configuration/myhost1.yml with your desired PostgreSQL version and settings.

Run the playbook:
ansible-playbook -i inventory 01-pgsql-init-binaries.yml



Playbooks

01-pgsql-init-binaries.yml: Installs and initializes PostgreSQL binaries for the specified version (e.g., 15) from Red Hat repositories.

Variables
Variables are defined in inventory-configuration/myhost1.yml. Key variables include:

postgres_version: PostgreSQL version (e.g., 15).
postgres_env: Environment (e.g., test).
postgres_db: Database name (e.g., myfirsttestdb).
postgres_port: Database port (e.g., 15444).
pg_root_dir, pg_data_dir, pg_log_dir, pg_root_code_dir: Directory paths for PostgreSQL data and scripts.

License
MIT License (or specify your preferred license).
