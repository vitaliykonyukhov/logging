Ansible Role: Docker Opensearch
=========

An Ansible Role that installs Opensearch and Opensearch dashboard in docker containers.

Requirements
------------

- Docker
- Docker-compose
- Python SDK:
  - docker
  - docker-compose

Role Variables
--------------

```text
opensearch_dir            Directory where docker-compose and configuration files are located
fluentd_enable            When "true" docker use fluentd to store logs
opensearch_version        Opensearch version
dashboard_version         Opensearch container
opensearch_port           Opensearch port
dashboard_port            Opensearch dashbord port
heap_size                 Xms Xmx values for JVM
```

Dependencies
------------

```text
roles:
  - role: geerlingguy.pip
    vars:
      pip_install_packages:
        - name: docker
        - name: docker-compose
  - role: geerlingguy.docker
```

Example Playbook
----------------

```text
- hosts: all
  become: true
  vars_files:
    - vars/vars.yml
    - vaults/vaults.yml
  roles:
    - role: docker_opensearch
```

License
-------

MIT / BSD

Author Information
------------------

Vitaly Konykhov vitaliykonyukhov@gmail.com
