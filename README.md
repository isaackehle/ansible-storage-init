# Ansible Role - storage-init

Initialize Storage for a machine

Available on Ansible Galaxy: [pgkehle.storage-init](https://galaxy.ansible.com/pgkehle/storage-init)

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
    - { role: pgkehle.storage-init }
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

## License

MIT

## Author Information

Paul Kehle  
@pgkehle ([twitter](https://twitter.com/pgkehle), [github](https://github.com/pgkehle), [linkedin](https://www.linkedin.com/in/pgkehle))
