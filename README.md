# What does this Repo?
This Repo contains an ansible Playbook, that will install two instances of a Kusama Validator on your Debian/Ubuntu Server.

# How to use this Playbook?

## Requirements:
To use this Playbook you need:
- ssh access to a Machine with a user that has root permissions
- ansible installed on the Machine you want to execute the Playbook from
- declare some Varibales

## Variables to declare
### In the file 'group_vars/all.yml' you can change this variables:
- system_username
- hyperbridge_username
- version

### Examples and explanation
#### system_username
Thats the username of your Ubuntu/Debian User.
If you login into your System for example with the command 'ssh hyperbridge@<IP-ADDRESS>' your system_username is 'hyperbridge'.   
```
system_username: hyperbridge
```

#### hyperbridge_username
Thats the Name your Hyperbridge Node and its systemd services will have.   
Open this website, switch to Kusama and check if your desired Validator Names arent already taken:
[Telemtery Polkadot](https://telemetry.polkadot.io/#list/0x19c5b43935ee2a7e4a090e2bde16ea106bcb1b3668a9abcd37bbceb8c9df16d4)
```
hyperbridge_username: some-name-you-like
```

#### version
Thats the Version you want to run for the Validatpor.
Check whats the latest Version here [GitHub Hyperbridge](https://github.com/polytope-labs/hyperbridge).    
You dont need to write the 'v' of the beginning of your Version!
```
version: 0.3.4
```

### In the file 'inventory.yml' you need to change this variables:
- ansible_host

### Examples and explanation
#### ansible_host
Thats the IP-Address of your Target Machine.
Your Machine needs to be accessable using ssh with that IP.
```
ansible_host: 192.168.1.10
```

# Run the Playbook
## Execute Ansible
cd into this Repo and run the Playbook with 'ansible-playbook playbook.yml'