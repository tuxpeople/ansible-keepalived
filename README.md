# ansible-keepalived

## Example playbook

See all possible vars in the defaults.

Note: Name of the servers must match names in the inventory.

```yaml
- hosts: all
  vars:
    keepalived_enable_vrrp_firewall: true
    keepalived_vrrpinstances:
      - name: "mygroup"
        master: "server1"
        routerid: 1
        servers:
          server1:
            interface: "eth0"
            priority: 200
          server2:
            interface: "eth0"
            priority: 199
          server3:
            interface: "ens192"
            priority: 198
        vips:
          - 192.168.8.222
  roles:
    - ansible-keepalived
```
