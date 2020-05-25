# Practical Ansible Nginx redirect

[![Integration](https://github.com/practical-ansible/nginx-redirect/workflows/CI/badge.svg)](https://github.com/practical-ansible/nginx-redirect/actions)
[![Quality](https://img.shields.io/ansible/quality/21427.svg)](https://galaxy.ansible.com/practical-ansible/nginx_redirect)
[![Downloads](https://img.shields.io/ansible/role/d/21427.svg)](https://galaxy.ansible.com/practical-ansible/nginx_redirect)
[![Role](https://img.shields.io/ansible/role/21427)](https://galaxy.ansible.com/practical-ansible/nginx_redirect)

Define domain redirect on your Nginx. Useful when adding/removing from `www.` from URL, useful when your domain has multiple aliases.

## Example: Remove www.

```yml
- name: Configure redirect to remove www from URL
  hosts: myhosts
  become: yes
  roles:
    - role: practical-ansible.nginx_redirect
      project_name: example
      server_names: www.example.com
      destination_domain: example.com
      status: 301
```

## Example: Redirect subdomain to a URL

```yml
- name: Configure redirect to remove www from URL
  hosts: myhosts
  become: yes
  roles:
    - role: practical-ansible.nginx_redirect
      project_name: example
      server_names: marketing-campaign.example.com
      destination_url: example.com/landing-page
```
