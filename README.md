# XCP-ng guest tools for CoreOS VMs

XCP-ng is a virtualization platform. You can read more about it here: [https://xcp-ng.org](https://xcp-ng.org)

Fedora CoreOS is a minimal OS with automatic updates for container workloads. Scalable and secure. More info here: [https://fedoraproject.org/coreos/](https://fedoraproject.org/coreos/)

This repository has an alpine linux docker image that contains the XCP-ng [guest tools](https://xcp-ng.org/docs/guests.html#alpine), configured to expose telemetry to the xcp-ng host. It was created to speed up the configuration process of a virtualized RancherOS VM within XCP-ng.
The code is a fork of the [Image: XCP-ng guest tools for RancherOS](https://github.com/GeoMSK/ros-xe-guest-utilities)

# Installation (From [GitHub Container Repo](https://github.com/wus-technik/coreos-xe-guest-utilities/pkgs/container/coreos-xe-guest-utilities))

Run with a very simple docker-compose file:

``` yaml
services:
  xe-guest-utilities:
    container_name: xe-guest-utilities
    image: ghcr.io/wus-technik/coreos-xe-guest-utilities:latest
    network_mode: host
    privileged: true
    restart: always
```

The guest tools will be recognized by the XCP-ng host without installations on the CoreOS VM.
Tested with the podman container runtime shipped with the current Fedora CoreOS 41+.

# Versions

- 20250314: xe-guest-utilities-8.4.0-r2
