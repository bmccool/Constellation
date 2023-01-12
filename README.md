# Constellation!

## Requirements
1. ssh access already configured to the PVE node - Note, this can be setup with the setup.yml playbook
    Setup ~/.ssh/config like
    ```
    Host gauss-pve
        User username
        HostName 192.XXX.XXX.XXX
    ```
2. DNS Server access
    All VMs should be accessible by name
    This may require a "search dns-suffix" entry in resolve.conf

