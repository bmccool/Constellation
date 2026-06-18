# Constellation!

## Usage
1. ansible-playbook setup.yml
2. Modify inventory file to use correct cluster prefix and proxmox host
    #TODO This should be done by the setup playbook eventually.
3. ansible-playbook main.yml -K -i inventory

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
    edit the /etc/resolve.conf file with the above, changes should take place immediately.  It's possible this
    file may be overwritten on startup, in which case there are other base files to edit that this one is
    built from at boot.
3. package "sudo" installed on pve node, along with user created which will be able to ssh and run commands.
4. kubectl installed on the localhost
5. SSH access to github.com/bmccool/Constellation via ~/.ssh/id_rsa and .pub files
6. Create secret files based on examples
    - cert-manager-secret.sops.yaml
    - flux_data.yaml
