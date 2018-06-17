# CentOS 7 Provisioning Ansible Playbook

This playbook will prepare your CentOS 7 instance for Docker production environment.

Tasks that are done within this playbook are :
* Upgrade all packages to latest version (yum module)
* Setup EPEL repo (yum module)
* Remove bloatware such as postfix
* Install yum-cron (yum module)
* Enable yum-cron on boot (service module)
* Copy tum-cron.conf template that will be in `minimal-security-severity:Critical` command mode (template module)
* Install firewalld (yum module)
* Enable firewalld on boot (service module)
* Allow http and https at public zone services in firewalld (firewalld module)
* Disable SELinux (selinux module)
* Install fail2ban (yum module)
* Setup ssh jail for fail2ban (template module)
* Install Docker dependencies (yum-utils, device-mapper-persistent-data, lvm2) (yum module)
* Add official Docker repository (get_url module)
* Install docker (yum module)
* Enable Docker on boot (service module)
* Install docker-compose (yum module)

> List above is bare minimum to have stable, safe and production ready Docker node.
