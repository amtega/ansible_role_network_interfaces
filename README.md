# Amtega network_interfaces role

This is an [Ansible](http://www.ansible.com) role configure ipv4 network interfaces.

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

The role setups the following facts:

- network_interfaces_ip_mac_map: dictionary mapping ip addresses to mac addresses

## Example Playbook

This is an example playbook:

``` yaml
---
- name: Network_interfaces role sample
  hosts: localhost
  roles:  
    - amtega.network_interfaces
  vars:
    network_interfaces_hostname: "{{ inventory_hostname }}"
    network_interfaces_gateway: 192.168.5.1
    network_interfaces_ipv6: no
    network_interfaces_dns_domain: acme.com
    network_interfaces_dns_search:
      - acme.com
      - acme.org
    network_interfaces_dns_nameserver:
      - 192.168.5.200
      - 192.168.5.201
    network_interfaces_dns_options:
      - timeout:1
      - rotate

    network_interfaces:
      - logicalname: management-01
        macaddress: 08:00:27:06:c1:f8
        ipv4:
          - address: 192.168.5.15
            cidr: 24
        mtu: 1500
        route:
          - net: 192.168.6.0/24
            gateway: 192.168.5.34
        route_multicast: no
        vlanid: 1024
        bond: no      
```

## Testing

Tests are based on vagrant virtual machines. You can setup vagrant engine quickly using the playbook `files/setup.yml` available in the role [amtega.vagrant_engine](https://galaxy.ansible.com/amtega/vagrant_engine).

Once you have vagrant, you can run the tests with the following commands:

```shell
$ cd amtega.network_interfaces/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2019 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify it under the terms of:

GNU General Public License version 3, or (at your option) any later version; or the European Union Public License, either Version 1.2 or – as soon they will be approved by the European Commission ­subsequent versions of the EUPL.

This role is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for more details or European Union Public License for more details.

## Author Information

- José Enrique Mourón Regueira
- Juan Antonio Valiño García.
