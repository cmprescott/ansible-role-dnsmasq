Ansible Role: dnsmasq
=========

Installs dnsmasq. Configures from *SIMPLE* templates.

Requirements
------------

**TODO**: OS support

Role Variables
--------------

Each array element is a line in the conf file. See the templates/dnsmasq.conf.j2 for examples.

```yaml
# --- conf paths ---
dnsmasq_path_conf: "/etc/dnsmasq.conf"
dnsmasq_path_dhcp_hosts: "/etc/dnsmasq.d/dhcp.hosts"
dnsmasq_path_dhcp_opts: "/etc/dnsmasq.d/dhcp.opts"

# --- dnsmasq.conf dns ---
dnsmasq_dns_cache: [ "cache-size=1000" ] 
dnsmasq_dns_domains: []
dnsmasq_dns_filters: [ "domain-needed", "bogus-priv" ] 
dnsmasq_dns_hosts: []
dnsmasq_dns_interfaces: [ "interface=wlan0" ] 
dnsmasq_dns_resolv: []
dnsmasq_dns_servers: []

# --- dnsmasq.conf dhcp ---
dnsmasq_dhcp_hosts_opts: [] 
dnsmasq_dhcp_lease: [] 
dnsmasq_dhcp_ranges: [] 

# --- dnsmasq.conf misc ---
dnsmasq_confs:
  - "dhcp-hostsfile={{ dnsmasq_path_dhcp_hosts }}"
  - "dhcp-optsfile={{ dnsmasq_path_dhcp_opts }}"
dnsmasq_logs: []
dnsmasq_run: []

# --- dnsmasq.d/dhcp.hosts ---
dnsmasq_dhcp_hosts: [] 

# --- dnsmasq.d/dhcp.opts ---
dnsmasq_dhcp_options: [] 
```

Dependencies
------------

None!

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: cmprescott.dnsmasq
      sudo: Yes
```

License
-------

BSD

Author Information
------------------

Presccott Chris
