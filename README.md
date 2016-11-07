# Ansible: storage-init

Initialize Storage for a machine

Available on Ansible Galaxy: [pgkehle.storage-init](https://galaxy.ansible.com/pgkehle/storage-init)

# Examples

## Example to generate a Certificate Signing Request 

```YAML
- hosts: all
  remote_user: root

  vars_files:
    - ./vars/configs/{{ ansible_hostname }}.yml

  vars:

    # Better to have in common vars_files input file  
    storage:
      array_num: 1
      size:
        quan: 1
        type: "T"
    disk_name: "sdb"

    # 
    partition_num: 1
    mnt_loc: "/mnt/data"                                   
    drive_path: "/dev/{{ disk_name }}"                        
    partition_name: "{{ disk_name }}{{ partition_num }}"      
    partition_path: "/dev/{{ partition_name }}"               

  roles:
    - { role: pgkehle.storage-init }
```

This will create a csr in:

- `~/certs/<fqdn>.csr`


## License

MIT

## Author Information

Paul Kehle  
@pgkehle ([twitter](https://twitter.com/pgkehle), [github](https://github.com/pgkehle), [linkedin](https://www.linkedin.com/in/pgkehle))
