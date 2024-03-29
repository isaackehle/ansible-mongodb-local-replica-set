# Ansible Role - mongodb_local_replica_set

Manage a Local MongoDB installation as a Replica Set

Available on Ansible Galaxy: [isaackehle.mongodb_local_replica_set](https://galaxy.ansible.com/isaackehle/mongodb_local_replica_set)

This project manages a local replica set instance of MongoDB. The default MongoDB installation is not a replica set. In order to take advantages of some of the features that a replica set brings, the local configuration needs to be enabled as a replica set.

## Variables

```yaml
data_path: /opt/mongodb
rs_servers:
  - { _id: 0, name: rs0_0, port: "27019" }
local_user: "{{ lookup('env','USER') }}"
home_dir: "{{ lookup('env','HOME') }}"
agents_dir: "{{ home_dir }}/Library/LaunchAgents"
config_dir: "/usr/local/etc"
```

## Examples

```yaml
- hosts: all
  gather_facts: inventory_hostname != 'localhost'
  roles:
    - isaackehle.mongodb_local_replica_set
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

## License

MIT

## Author Information

Isaac Kehle
@isaackehle ([twitter](https://twitter.com/isaackehle), [github](https://github.com/isaackehle), [linkedin](https://www.linkedin.com/in/isaackehle))
