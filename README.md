# Constellation!

## Requirements
1. ssh access already configured to the PVE node - Note, this can be setup with the setup.yml playbook
    Setup ~/.ssh/config like
    ```
    Host gauss-pve
        User username
        HostName <PVE IP Address, 192.XXX.X.X>
    ```
2. DNS Server access
    All VMs should be accessible by name
    This may require a "search dns-suffix" entry in resolve.conf as well as a nameserver:
    ```
    # DNS requests are forwarded to the host. DHCP DNS options are ignored.
    nameserver <dns primary address>
    search <domain name suffix, abc.com>
    ```

