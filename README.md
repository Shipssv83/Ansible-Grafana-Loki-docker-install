Hi, ![](https://user-images.githubusercontent.com/18350557/176309783-0785949b-9127-417c-8b55-ab5a4333674e.gif)my name is Serhii Shypylov
=========================================================================================================================================

-------------------------------

### Socials
<p align="left">
  <a href="https://t.me/oneitpro">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/telegram-app.png" alt="Telegram" width="30" height="30" />
  </a>
  <a href="https://www.linkedin.com/in/sergey-shipilov-7262a31b4/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/linkedin.png" alt="LinkedIn" width="30" height="30" />
  </a>
  <a href="https://www.instagram.com/shipssvpl/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/instagram-new.png" alt="Instagram" width="30" height="30" />
  </a>
  <a href="https://www.facebook.com/profile.php?id=100083345006373">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/facebook.png" alt="Facebook" width="30" height="30" />
  </a>
  <a href="https://discord.com/invite/6z5EyagDyW?ref=1it.pro">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/discord.png" alt="Discord" width="30" height="30" />
  </a>
  <a href="mailto:admin@1it.pro">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/new-post.png" alt="Mail" width="30" height="30" />
  </a>
  <a href="https://1it.pro/">
    <img src="https://img.icons8.com/ios-glyphs/30/ffffff/domain.png" alt="Website" width="30" height="30" />
  </a>
</p>

# Ansible Playbook for Server and Grafana Loki Docker Installation

This repository contains an Ansible playbook for setting up a server, installing Docker, and deploying Grafana Loki in a Docker container with firewall configuration (UFW).

## Playbook Overview

The playbook includes the following steps:
1. **Server Setup**: Initializes basic server settings.
2. **Docker Installation**: Installs Docker and Docker Compose for container management.
3. **Grafana Loki Installation**: Deploys Grafana Loki in a Docker container and configures it with UFW rules.

## Playbook Structure

### 1. Server Setup (`server-install.yml`)
The `server-install.yml` playbook installs necessary server dependencies and configures the system environment (e.g., timezone).

### 2. Docker Installation (`docker-install.yml`)
The `docker-install.yml` playbook installs Docker and Docker Compose on the server to prepare the system for running containers.

### 3. Grafana Loki Docker Installation (`grafana-install.yml`)
This playbook sets up Grafana Loki within a Docker container, configures the web route, and allows traffic through UFW.

## Requirements

Before running the playbook, make sure the following requirements are met:
- Ansible 2.9+ installed on the control node.
- SSH access to the target hosts.
- A Linux server (Ubuntu, CentOS, etc.) with internet access.

## Roles Used

- **roles/server-install**: Sets up server environment and system-level configurations.
- **roles/docker-install**: Installs Docker and Docker Compose.
- **roles/grafana-docker-install**: Deploys Grafana Loki in a Docker container.


# ansible galaxy roles

```
### install role ansible galaxy
ansible-galaxy install -r roles/requirements.yml

### upgrade role ansible galaxy 
ansible-galaxy install -g -f -r roles/requirements.yml
```

# Run the Playbook install
Run the playbook by specifying your inventory file and variable file:

```
ansible-playbook -i inventory --user root --extra-vars "hosts=host_name" playbooks/grafana-install.yml
```

License
This project is licensed under the MIT License
