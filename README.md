# Practical Ansible Nginx redirect

Define domain redirect on your Nginx. Useful when adding/removing from `www.` from URL, useful when your domain has multiple aliases.


## Variables

* `nginx_redirect_project_name` - Name that is used to identify your redirect
* `nginx_redirect_server_name` - Space separated list of domain names that are to be redirected
* `nginx_redirect_destination_domain` - Target domain name, preferred over url.
* `nginx_redirect_destination_url` - Target URL
* `nginx_redirect_enabled` - Enable (default True)
* `nginx_redirect_status` - Http status used for redirect (default 301)


## Minimal config example

```yml
- name: Configure redirect to remove www from URL
  hosts: myhosts
  become: yes
  roles:
    - role: practical-ansible.nginx-redirect
      nginx_redirect_project_name: example
      nginx_redirect_server_name: www.example.com
      nginx_redirect_destination_domain: example.com
```
