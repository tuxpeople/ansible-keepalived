# ansible-keepalived

## Example playbook

See all possible vars in the defaults.

Note: Name of the servers must match names in the inventory.

```yaml
- hosts: all
  vars:
    keepalived_enable_vrrp_firewall: true
    keepalived_vrrpinstances:
      - name: mygroup
        master: server1
        masterif: eth0
        masterpriorityanchor: 200
        slave1: server2
        slave1if: eth0
        slave1priorityanchor: 199
        slave2: server3
        slave2if: eth0
        slave2priorityanchor: 199
        routerid: 1
        vips:
          - 192.168.8.222
  roles:
    - ansible-keepalived
```