# Ansible Role: role-resizepv_vm_rhel

## Author
- Thomas DUPOUY <moz@free.fr>

## Licence
MIT

## Description
This role allows to grow dynamically a disk of a VMWare virtual guest
Tested on RHEL 6 (need reboot + replay) and RHEL 7 / VCenter 6 and 6.5


## Role Variables
```
vg_destination: data_vg
extension_requise_go: 10
- controleurs:
      - vim.vm.device.ParaVirtualSCSIController
      - vim.vm.device.VirtualLsiLogicController
```

## Exemple Playbook

```
- hosts: "{{ targets }}"
  gather_facts: true
  gather_subset: hardware
  become: yes
  become_user: root
  roles:
    - role: role-resizepv_vm_rhel
```

## Changelog
- 1.0.0 : Initial release
- 1.2.0 : Idempotence