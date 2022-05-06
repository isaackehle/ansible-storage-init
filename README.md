# Ansible Role - storage-init

Initialize Storage for a machine

Available on Ansible Galaxy: [isaackehle.storage-init](https://galaxy.ansible.com/isaackehle/storage-init)

## Examples

Example to create a 1 TB storage block that will eventually be assigned to `/dev/sdb1/`

```yaml
- hosts: all
  remote_user: root

  vars_files:
    - ./vars/configs/{{ inventory_hostname }}.yml

  vars:
    # Better to have in common vars_files input file
    mnt_dir: "/mnt/data"
    partition_type: xfs
    device_name: sdb
    partition_num: 1

  roles:
    - { role: isaackehle.storage-init }
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

## License

MIT

## Author Information

Isaac Kehle
@isaackehle ([twitter](https://twitter.com/isaackehle), [github](https://github.com/isaackehle), [linkedin](https://www.linkedin.com/in/isaackehle))
