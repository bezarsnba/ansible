# Ansible Wordpress

This playbook install following packages:

- Nginx
- PhP
- MariaDB

## Contains rules to install:
- Wordpress 5.1
- MariaDB

## Necessary
- Python >2.7
- Ansible 2.6~2.7

## Test in Operation system:
- Ubuntu Bionic (18.04)

To running this playbook is necessary:

```bash
$ ansible-playbook -i hosts/hosts playbook.yaml
```