# Playbook Ansible to create instance in Google Cloud Plataform

## Contain tasks:
- Create instance GCE modules:
    - gcp_compute_instance
    - gcp_compute_address
- Destroy instance GCE

## Google CLoud Plataform Project

1. You will need to create a Google Cloud Plataform  account
2. You'll need a [Service Account](https://cloud.google.com/compute/docs/access/service-accounts#serviceaccount).
3. Next you will want to install the [Cloud SDK](https://cloud.google.com/sdk/)

## Softwares

1. Install Ansible [running from source instructions](http://docs.ansible.com/intro_installation.html#running-from-source).

2. Install GCP modules:

```
pip install googleauth requests

```

3. You can set a couple of environment variable to simplify SSH interactions.

```
export ANSIBLE_HOST_KEY_CHECKING=False
```

## Ansible
1. Edit the `roles/gcp-inst-c/vars/auth.yaml` specify your Project ID in the `project` variable, Service Account in the `service_account_email` variable, and the location Json in the `credentials_file`, example:

project: <PROJECT_NAME>
auth_kind: serviceaccount
credentials_file: files/<JSON_FILE_CREDENTIALS>
service_account_email: <SERVICE_ACCOUNT_EMAIL>

## Running the playbook

### Create instance
Use the `ansible-playbook` command to create the instance and pass the variable `create-inst`, for example

```bash
ansible-playbook -i hosts/ansible_hosts --extra-vars "staging=create-inst" playbook.yaml
```

### Destroy Instance

Use the `ansible-playbook` command to destroy the instance and pass the variable `destroy-inst`, for example

```bash
ansible-playbook -i hosts/ansible_hosts --extra-vars "staging=destroy-inst" playbook.yaml
```

[Repository GoogleCloud Plataform](https://github.com/GoogleCloudPlatform/compute-video-demo-ansible)

[Slides DevFestCerrado](https://pt.slideshare.net/bezalielramos/descubra-como-o-ansible-pode-ajudar-no-provisionamento-de-gce-184847824)

[Youtube Demo](https://www.youtube.com/watch?v=jvdwDGZ1amo)
