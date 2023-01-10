# ansible-role-node_exporter
Ansible Role to install the node_exporter binary
## Requirements

- Ansible >= 2.10 **(No tests has been realized before this version)**

## Role Variables

All variables which can be overridden are stored in [default/main.yml](default/main.yml) file as well as in table below.

| Name           | Default Value | Choices | Description                        |
| -------------- | ------------- | ------- | -----------------------------------|
| `node_exporter_version` | latest | [version](https://github.com/prometheus/node_exporter/tags) | node_exporter version. |
| `node_exporter_log_level` | info | debug, info, warn, error | Only log messages with the given severity or above. |
| `node_exporter_log_format` | logfmt | logfmt, json | Output format of log messages. |
| `node_exporter_listen_addresses` | [] |  | Addresses on which to expose metrics and web interface. |
| `node_exporter_extra_opts` | [] |  | Define node_exporter extra options at start. |
| `node_exporter_web_configuration` | [] |  | Variable that contain web configurations. |

## Example Playbook

```yaml
---
- hosts: all
  tasks:
    - name: Include ansible-role-node_exporter
      include_role:
        name: ansible-role-node_exporter
      vars:
        node_exporter_version: '1.4.0'
        node_exporter_web_configuration:
          basic_auth_users:
            prometheus: $hj$12$hLf2lSsxfm0.i0a.1knpSOVyBCfIB51VRczxczxcxGD$^2zcxzcz
```
