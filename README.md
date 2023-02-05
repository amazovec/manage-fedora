# Manage-Fedora

    This repo is all about setting up Fedora workstation with customized requirements for sysops test candidates tasks

## Requirements

- **Platforms:**
  - Fedora - 

- **Dependencies:**
  - Ansible >= 2.9.6

## Installation

Clone the repository to your desired location. 

## Usage

Once inside the ansible directory `manage-fedora`. There are three essential playbooks.
1. users-creation.yml
	- Creates two users i.e. simple user and super user
	- Passwordless sudo for superuser
	- Copies ansible controller's ssh-key to both user's `authorized_keys`
2. install-developer-ws.yml
	 -  Contains following roles:
		   - packages
		   - ssh		   
		  
3. install-plain-ws.yml
	 -  Contains following roles:
		   - packages
		   - ssh		

Edit the `hosts.ini` that is present at `./inventory/hosts.ini` and construct your cluster based on:
1. Place all `developer` hosts under the `developer` group with their corresponding IP Addresses.
2. Place all `plain` hosts (non developers) under the `plain` group.
3. Make sure a group of groups `workstation` is present and add both groups `developer` and `plain` as its children.

#Note `./inventory/hosts.ini` is defined as default host file under `ansible.cfg`

4. Prepare these essentials variables

### Variables

###### 1. Vars inside the playbook

The playbooks `install-developer-ws.yml` require following essential vars:
```
- ws_developer: true          ## Only for install-developer-ws.yml

```

- Notes:
	- For `install-developer-ws.yml`, the variable `ws_developer` variable must be defined and for `install-plain-ws.yml` it must not (should be commented out). Based on this variable, additional packages are installed for `developer` users.