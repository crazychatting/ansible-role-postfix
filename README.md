# Ansible Role: Postfix

[![CI](https://github.com/geerlingguy/ansible-role-postfix/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-postfix/actions?query=workflow%3ACI)

Installs postfix on RedHat/CentOS or Debian/Ubuntu.

## Requirements

If you're using this as an SMTP relay server, you will need to do that on your own, and open TCP port 25 in your server firewall.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    postfix_config_file: /etc/postfix/main.cf

The path to the Postfix `main.cf` configuration file.

    postfix_service_state: started
    postfix_service_enabled: true

The state in which the Postfix service should be after this role runs, and whether to enable the service on startup.

    postfix_inet_interfaces: localhost
    postfix_inet_protocols: all
    postfix_relayhost: ''

Options for values `inet_interfaces`, `inet_protocols` and `relayhost` in the `main.cf` file. Relayhost defaults to empty, can be something like `mailgw.example.com`.

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - geerlingguy.postfix

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
