# Ansible-playbooks

This project contains Ansible playbooks to deploy micro-services from [micro-platform](https://github.com/micro-platform)

## Requirements

* Linux based OS
* Ansible >= 2.1
* Docker

## Setup

Before deploying, you need to install roles dependencies :

```
ansible-galaxy install -f -r roles/roles_requirements.yml -p roles/external 
```

## Deployment

At the moment, the only playbook working completely is [deploy-poc-hystrix.yml](https://github.com/micro-platform/ansible-playbooks/blob/master/plays/deploy-poc-hystrix.yml)

To deploy it on your machine, run :

```
cd plays
ansible-playbook deploy-poc-hystrix.yml -i ../local
```

3 docker containers corresponding to the 3 components of the poc should be created.

You can view them by typing :

```
docker ps
```

*NB: if you want to do this on other machines, modify the inventory file under prod and adapt the playbook*

*NB2: to execute the playbook, you need to be able to become superuser without a password or launch the playbook with this role*