# Ansible Role - mongodb_local_replica_set

Manage a Local MongoDB installation as a Replica Set

Available on Ansible Galaxy: [pgkehle.mongodb_local_replica_set](https://galaxy.ansible.com/pgkehle/mongodb_local_replica_set)

This project manages a local replica set instance of MongoDB.  The default MongoDB installation is not a replica set.  In order to take advantages of some of the features that a replica set brings, the local configuration needs to be enabled as a replica set.

## Variables

```yaml
data_path: /data/mongodb
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
   gather_facts: "{{ inventory_hostname != 'localhost' }}"
   roles:
     - pgkehle.mongodb_local_replica_set
```

## License

MIT

## Author Information

Paul Kehle  
@pgkehle ([twitter](https://twitter.com/pgkehle), [github](https://github.com/pgkehle), [linkedin](https://www.linkedin.com/in/pgkehle))
