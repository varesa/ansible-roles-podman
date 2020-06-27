# Ansible-roles-podman

Various roles for running containers using podman

## Example use

```
---

- hosts: all
  become: true

  tasks:
      - include_role:
          name: podman-volume
        vars:
          volume_name: redis-data

      - include_role:
          name: podman-container
        vars:
          container_name: redis
          container_image: registry.access.redhat.com/rhscl/redis-32-rhel7
          container_options: --privileged=true -v redis-data:/var/lib/redis/data -p 6379:6379
```
