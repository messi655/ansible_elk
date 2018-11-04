# Requirement
- Ansible: >= 2.3.2.0
- Ansible Playbook: >= 2.3.2.0
- Docker: >= 17.06.2-ce
- Docker API version: >= 1.30
- Docker compose version: >= 1.16.1
- Docker-py version: >= 2.5.1


# How to run
1) Edit file group_vars/all.yml

```
nginx_kibana_port: xxxx
elk_server_ssl_cert_port: xxxx
kibana_user: xxxx
kibana_password: xxxx
logstash_port: xxxx
es_port: xxxx
elk_server_1: xxx.xxx.xxx.xxx
logstash_server_1: xxx.xxx.xxx.xxx
elk_server_2: xxx.xxx.xxx.xxx
logstash_server_2: xxx.xxx.xxx.xxx
elk_proxy: xxx.xxx.xxx.xxx
elk_proxy_port: xxx
docker_user: docker_private_username
docker_pass: docker_private_password

```
2) Run 
+ Build and push images to private docker registry
```
 ansible-playbook --private-key /media/mount/Work/keys/private_key -i monitoring.hosts build_sites.yml
```
+ Deploy ELK by docker
```
ansible-playbook --private-key /media/mount/Work/keys/my_key -i monitoring.hosts deploy_sites.yml
```