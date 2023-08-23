# Ansible Playbooks for Proxmox Homelab 

This is a collection of Ansible playbooks and roles for managing my Proxmox homelab.  It is a work in progress and is not intended for general use.  It is not intended to be a complete solution for managing a Proxmox cluster.  It is intended to be a starting point for managing a Proxmox cluster. 

## Usage

### Prerequisites

- Have Ansible installed: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
- Copy your SSH public key to the Proxmox cluster nodes

### Run

Setup env var: `export ANSIBLE_CONFIG=ansible.cfg`
Run playbook: `ansible-playbook -i inventory.yml RestartGluster.yml` 

## Playbook List

### Restart Gluster

This playbook will restart the gluster service on all nodes in the cluster.  This is useful if you have a gluster volume that is in a degraded state and you need to restart the gluster service on all nodes to get the volume back to a healthy state.   

You can use this by running the following command: `ansible-playbook -i inventory.yml RestartGluster.yml` 

### "Wake Up Jeff" (Wake On Lan)

This playbook will send a Wake On Lan (WOL) packet to all nodes in the cluster.  This is useful if you have a Proxmox node that is powered off and you want to power it on.  You can use this by running the following command: `ansible-playbook -i inventory.yml WakeUpJeff.yml`