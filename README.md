# Ansible Role - storage-init

Initialize Storage for a machine

Available on Ansible Galaxy: [pgkehle.storage-init](https://galaxy.ansible.com/pgkehle/storage-init)

## Examples

Example to create a 1 TB storage block that will eventually be assigned to `/dev/sdb1/`   

```yaml
- hosts: all
  remote_user: root

  vars_files:
    - ./vars/configs/{{ ansible_hostname }}.yml

  vars:

    # Better to have in common vars_files input file  
    mnt_loc: "/mnt/data"

    storage:
      disk_name: vdb
      partition_num: 1
      size: 3T
      name: vdb
      type: xfs


  roles:
    - { role: pgkehle.storage-init }
```

## License

MIT

## Author Information

Paul Kehle  
@pgkehle ([twitter](https://twitter.com/pgkehle), [github](https://github.com/pgkehle), [linkedin](https://www.linkedin.com/in/pgkehle))

