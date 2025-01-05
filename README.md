[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Copier](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/copier-org/copier/master/img/badge/badge-grayscale-inverted-border.json)](https://github.com/copier-org/copier)
[![Podman Badge](https://img.shields.io/badge/Podman-892CA0?logo=podman&logoColor=white)](https://podman.io/)
[![Hatch project](https://img.shields.io/badge/%F0%9F%A5%9A-Hatch-4051b5.svg)](https://github.com/pypa/hatch)
![CI](https://github.com/ansible-selfhosted/selfhosted.services.frigate.git/actions/workflows/ci.yml/badge.svg)
[![Ansible](https://img.shields.io/badge/Ansible-Molecule-EE0000?style=plastic&logo=ansible&logoColor=white)](https://github.com/ansible/molecule)

<!-- BEGIN_ANSIBLE_DOCS -->

# Ansible Role: [frigate](https://docs.frigate.video/)

A role to deploy Frigate using rootless Podman with systemd.

## Role Requirements

- none

*Refer to services collection for general requirements*

## Role Arguments

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
|frigate_additional_options|List of additional key=value for the quadlet container<br>ex: - "Network=custom.network"<br>Can also be used to leave comments by preceding with a '#'|list|False|[]|
|frigate_allow_unauthenticated|Expose the port for unauthenticated access|bool|False|False|
|frigate_config_label|The labels for to the frigate config directory<br>Comma separated values (ex: rw,Z)|str|False||
|frigate_config_path|Path to the config directory|str|False|~/.config/frigate/|
|frigate_hwaccel|Enable hardware acceleration|bool|False|False|
|frigate_hwaccel_path|Path to the hardware acceleration device<br>Only used if frigate_hwaccel is true|str|False|/dev/dri/renderD128|
|frigate_pci_coral|Enable coral support via PCI for hardware acceleration|bool|False|False|
|frigate_privileged|Run frigate in privileged mode<br>This may not be necessary for all setups|bool|False|True|
|frigate_rpi4|Enable support for the Raspberry Pi 4|bool|False|False|
|frigate_rtsp_port|RTSP port|int|False|8554|
|frigate_shm_size|Shared memory size<br>[reference](https://docs.frigate.video/frigate/installation#calculating-required-shm-size)|str|False|64mb|
|frigate_storage_label|The labels for to the frigate storage directory<br>Comma separated values (ex: rw,Z)|str|False||
|frigate_storage_path|Path to the storage directory|str|False|~/.local/share/containers/storage/frigate/|
|frigate_tmpfs_size|Size of the tmpfs<br>Only used if frigate_use_tmpfs is true|int|False|1000000000|
|frigate_unauthenticated_port|Unauthenticated port<br>Only used if frigate_allow_unauthenticated is true|int|False|5000|
|frigate_usb_coral|Enable coral support via USB for hardware acceleration|bool|False|False|
|frigate_usb_coral_path|Path to the Coral USB device<br>Only used if frigate_usb_coral is true|str|False|/dev/bus/usb|
|frigate_use_tmpfs|Use tmpfs|bool|False|True|
|frigate_version|Version of frigate to use<br>[Reference](https://docs.frigate.video/frigate/installation#docker)|str|False|stable|
|frigate_web_port|Port to access the web interface via https|int|False|8971|
|frigate_webrtc_port|WebRTC port|int|False|8555|


## Example Playbook

```
- hosts: all
  tasks:
    - name: Importing frigate role
      ansible.builtin.import_role:
        name: selfhosted.services.frigate
      vars:
```

## License

This project is licensed under the [MIT License](LICENSE)


⊂(▀¯▀⊂)

<!-- END_ANSIBLE_DOCS -->
