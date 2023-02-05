# Prerequisites
## Virtual machine
These tasks will require a Fedora 37 Workstation virtual machine installed from the default distro and with the default settings. 

## Assume 

## Create two users:

●	superuser
○	Allow sudo rights for remote management
○	Add SSH key to the user for remote management
●	user
○	Plain user

## GitOps

Prepare a public GIT repository, make it public and document all changes of the code. Please send us a GIT repository link on test completion for review. 

Added points for using github actions where possible.
Tasks
Ansible

Prepare ansible playbook and roles with selected tasks:

##	Package management
○	Update packages
○	Enable additional fedora workstation repositories
○	Add additional repositories 
■	Google chrome
■	Slack
■	Docker community (only for developers)
■	MySQL community (only for developers)
■	VSCode - Microsoft repo (only for developers)

##	Install packages (common)
■	gnome-tweaks
■	htop
■	keepassxc
■	slack
■	zsh

##	Install packages (only for developer machines)
■	ansible
■	code (microsoft repo)
■	fd-find
■	fzf
■	fish
■	mysql (community repo)
■	vim
■	zsh 
●	“Development tools” fedora package group
●	“C Development Tools and Libraries” package group

##	Docker role 
○	Install docker packages
■	docker
■	docker-compose-plugin
■	docker-compose
○	Enable docker at startup
○	Add all users to docker group

●	Ansible role for configuring SSH server
○	Disable password logins
○	Disable root login
○	Disallow forwarding
○	Install fail2ban and punish offensive ssh clients

●	Ansible role for configuring firewall
○	Block incoming traffic
○	Allow SSH 
○	Allow ICMP echo reply for private subnets
○	Allow protocols and ports needed by docker deployment

●	CA & internal self signed certificates
○	Create certificate authority 
○	Issue a wildcard certificate with newly created CA
■	Use sysops.jobs domain for example
○	Create ansible role for trusting all certificates issued by our CA

●	Ansible role for installing nix - https://nixos.org/ (developers only)
○	Install as plain user
Docker (bonus task)

○	 

●	Create ansible role for provisioning created docker deployment
Documentation

Documentation is a critical part of any organization, especially those that focus primarily on IT. 

IT Documentation is a detailed description of how to execute a process, method, task, or program and outlines the exact steps needed to do it efficiently.

Documentation works as a guide for internal (employees, management, etc) as well as external (customers, clients, partners) stakeholders, helping them understand a process easily and getting them up to speed without the requirement of proper training.

●	Provide documentation with your GIT repository as README for all tasks/roles/playbooks
●	Provided README should also include documentation on usage and expected results. Consider it as how-to
