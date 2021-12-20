[![CI](https://github.com/de-it-krachten/ansible-role-docker_compose/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-docker_compose/actions?query=workflow%3ACI)


# ansible-role-docker_compose

Installs docker-compose


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS



Role Variables
--------------
<pre><code>
# type of installation (binary or pip)
docker_compose_type: binary

# API endpoint to get latest version 
docker_compose_api: https://api.github.com/repos/docker/compose

# Download location for binary
docker_compose_repo: https://github.com/docker/compose

# Should the software be downloaded
docker_compose_download: true

# Version to install
docker_compose_version: latest

# Platform/architecture, as it makes part of the binary to download
docker_compose_platform: "{{ ansible_system | lower }}-{{ ansible_architecture }}"

# Target location/ownership/permissions for the binary
docker_compose_path: /usr/local/bin/docker-compose
docker_compose_owner: root
docker_compose_group: root
docker_compose_mode: '0755'
</pre></code>


Example Playbook
----------------

<pre><code>
- name: Converge
  hosts: all
  vars: null
  tasks:
    - name: Include role 'ansible-role-docker_compose'
      include_role:
        name: ansible-role-docker_compose
</pre></code>
