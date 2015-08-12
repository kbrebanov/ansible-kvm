kvm
===

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-kbrebanov.kvm-660198.svg)](https://galaxy.ansible.com/list#/roles/3299)

Installs KVM.

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Variable | Definition | Type |Default Value |
| -------- | ---------- | ---- | :-----------: |
| kvm_listen_tls | Whether or not to listen for TLS connections | boolean | true |
| kvm_listen_tcp | Whether or not to listen for unencrypted TCP connections | boolean | false |
| kvm_tls_port | The port on which to listen for TLS connections | number | 16514 |
| kvm_tcp_port | The port on which to listen for unencrypted TCP connections | number | 16509 |
| kvm_listen_address | The address on which to listen for TLS and/or unencrypted TCP connections | string | 0.0.0.0 |
| kvm_mdns_adv | Whether or not to use ZeroConf | boolean | false |
| kvm_mdns_name | The name used for ZeroConf advertisements.  Only set if kvm_mdns_adv is enabled. | string | ``{{ ansible_hostname }}`` |
| kvm_key_file | The path to the SSL private key for TLS connections.  Only set if kvm_listen_tls is enabled | /etc/pki/libvirt/private/serverkey.pem |
| kvm_cert_file | The path to the SSL certificate for TLS connections.  Only set if kvm_listen_tls is enabled | /etc/pki/libvirt/private/servercert.pem |
| kvm_ca_file | The path to the SSL CA certificate for TLS connections.  Only set if kvm_listen_tls is enabled | /etc/pki/libvirt/private/cacert.pem |
| kvm_crl_file | The path to the certificate revocation list for TLS connections.  Only set if kvm_listen_tls is enabled | /etc/pki/libvirt/private/crl.pem |
| kvm_no_verify_certificate | Whether or not to verify certifications for TLS connections.  Only set if kvm_listen_tls is enabled | false |
| kvm_max_clients | The maximum number of client connections | number | 20 |
| kvm_max_queued_clients | The maximum number of queued client connections | number | 1000 |
| kvm_max_works | The maximum number of worker threads servicing client connections | number | ``{{ kvm_max_clients }}`` |
| kvm_log_level | The level at which to log (4 errors, 3 warnings, 2 information, 1 debug) | number | 3 |
| kvm_log_filters | An expression to select different log levels based on event type | string | "" |
| kvm_log_outputs | An expression to direct different log outputs based on event type | string | "" |
| kvm_vnc_listen | The address on which to listen for VNC connections | string | 0.0.0.0 |

Dependencies
------------

None

Example Playbook
----------------

Install KVM
```
- hosts: all
  roles:
    - { role: kbrebanov.kvm }
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
