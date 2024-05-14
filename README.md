# Ansible-Role: acr-ansible-install-flask-app

AIT-CyberRange: Installs flask dependencies 


## Requirements

- Debian or Ubuntu 

## Role Variables

```yaml
app_user: "{{ app_name }}"
app_basepath: /opt/{{ app_name }}

app_python_version: "3.9"
app_packages: []
app_default_packages:
  - python{{ app_python_version }}
  - python3-pip
  - python{{ app_python_version }}-venv
  - nginx

app_requirements_file: "{{ app_basepath }}/requirements.txt"
app_virtualenv: "{{ app_basepath }}/venv"
app_virtualenv_command: python3.9 -m venv

app_use_setuptools: false

```

## Example Playbook

```yaml
- hosts: all
  roles:
    - acr-ansible-install-flask-app
      vars:
        app_user: "username"
        app_python_version: "3.9"
```

## License

GPL-3.0

## Author

- Lenhard Reuter