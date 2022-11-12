Ansible Role: Docker Fluentd
=========

An Ansible Role that installs Fluentd in docker container.

Requirements
------------

```text
- Docker
- Docker-compose
- Python SDK:
    - docker 
    - docker-compose
```

Role Variables
--------------

```text
fluentd_image               version of fluentd docker image. 
opensearch_plugin_version   version of fluentd opensearch plugin
fluentd_dir                 directory where docker-compose and configuration files are located
elastic_host                elasticsearch/opensearch IP address/domain name
elastic_port                elasticsearch/opensearch port
elastic_user                name of elasticsearch/opensearch user
elastic_password            password for elasticsearch/opensearch
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
    - role: docker_fluentd
```

License
-------

MIT / BSD

Author Information
------------------

Vitaly Konykhov vitaliykonyukhov@gmail.com
