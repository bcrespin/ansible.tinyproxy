Role Name
=========

install and configure tinyproxy 
tested on OpenBSD, but can be quickly updated for  linux or FreeBSD

Requirements
------------

none

Role Variables
--------------

```yaml
---
# defaults file for ansible.tinyproxy
tinyproxy_service_name: tinyproxy
tinyproxy_configfile: tinyproxy.conf
tinyproxy_dir: /etc/tinyproxy/
tinyproxy_user: _tinyproxy
tinyproxy_group: _tinyproxy
tinyproxy_port: 8888
tinyproxy_listen: 127.0.0.1
tinyproxy_bind_same: False
tinyproxy_bind: ''
tinyproxy_timeout: 600
tinyproxy_defaulterrorfile: "/usr/local/share/tinyproxy/default.html"
tinyproxy_statfile: "/usr/local/share/tinyproxy/stats.html"
tinyproxy_syslog: False
tinyproxy_loglevel: Connect
tinyproxy_max_clients: 100
tinyproxy_min_spareservers: 5
tinyproxy_max_spareservers: 20
tinyproxy_start_servers: 10
tinyproxy_max_requests_per_child: 0
tinyproxy_allow:
  - 127.0.0.1
tinyproxy_via_proxy_name: "tinyproxy"
tinyproxy_disable_via: False
tinyproxy_connect_ports: ['443', '563' ]
```
Dependencies
------------

none

Example Playbook
----------------
this install and configure tinyproxy listening on any interface, but allowing only 192.168.10/24 and localhost as client.
it's also hide the clients by not using Via header..

```yaml
- hosts:  proxy_hosts
  vars:
    tinyproxy_listen: 0.0.0.0
    tinyproxy_disable_via: true
    tinyproxy_allow:
      - 192.168.1.0/24
      - 127.0.0.1
```

License
-------

BSD


