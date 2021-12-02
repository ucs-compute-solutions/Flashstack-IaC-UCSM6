# FlashStack Converged Infrastructure setup using Ansible for FlashStack Virtual Server Infrastructure with Cisco UCS 4.2(1) in UCS Managed Mode, VMware vSphere 7.0 U2, and Pure Storage FlashArray//X R3 Series

This repository for FlashStack contains Ansible playbooks to configure Cisco Nexus, Cisco UCS, Cisco MDS, Pure FlashArray for VMware ESXi and VMware vCenter. This repository can be used for setting up Cisco devices, Pure FlashArray as well as VMware ESXi and vCenter as covered in the following Cisco Validated Design (CVD): https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/flashstack_vsi_xseries_70u2_design.html.

The CVD lays out the complete process for configuring the FlashStack using Ansible. Since these playbooks are intended to save time in setting up a working FlashStack, a complete FlashStack as shown below is needed to execute the playbooks. Various simulators could be used to partially test individual playbooks.

# FlashStack - physical topology for IP connectivity

![image](https://user-images.githubusercontent.com/3585414/144472122-bd8f417f-87a7-4ce1-b24d-9a5f0e903b81.png)

# FlashStack - physical topology for IP connectivity

![image](https://user-images.githubusercontent.com/3585414/144472208-26c0459a-81e7-4294-9805-055676847052.png)

# Set up the execution environment
To execute various ansible playbooks, a linux based system will need to be setup as described in the CVD with the packages listed at the following pages:
 •	Cisco UCS: https://galaxy.ansible.com/cisco/ucs
 •	Cisco NxOS: https://galaxy.ansible.com/cisco/nxos
 •	Pure FlashArray: https://galaxy.ansible.com/purestorage/flasharray
 •	VMware: https://galaxy.ansible.com/community/vmware
 
# How to execute these playbooks?

# FlashStack Automated Deployment Workflow

![image](https://user-images.githubusercontent.com/3585414/144469881-a647e3fa-f48e-411c-b13c-822bfb9a15ea.png)

# High-Level FlashStack Automation

![image](https://user-images.githubusercontent.com/3585414/144469966-5bb64054-b070-4ab2-a61f-866c3beb47c3.png)

### Playbook Execution Commands – Summary:
Setup all the variables before executing the playbooks as detailed in the CVD: https://www.cisco.com/c/en/us/td/docs/unified_computing/ucs/UCS_CVDs/flashstack_redhat-OCP.html

1.	Setup LAN on Nexus and UCS: "ansible-playbook ./Setup_Nexus.yml -i inventory"
2.	Setup Pure FlashArray Initial Config - Optional: "ansible-playbook ./Setup_Pure.yml -i inventory"
3.	Setup Cisco UCS: "ansible-playbook ./Setup_UCS.yml -i inventory"
4.	Setup Pure FlashArray: "ansible-playbook ./Setup_MDS.yml -i inventory"
5.	Setup Pure FlashArray: "ansible-playbook ./Setup_Pure.yml -i inventory"
6.	Setup VMWare ESXi servers: "ansible-playbook ./Setup_ESXi.yml -i inventory"
7.	Setup VMWare Cluster and vCenter Setup: "ansible-playbook ./Setup_vCenter.yml -i inventory"	
