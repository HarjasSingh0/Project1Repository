# Project1Repository
This repository contains the files I need to submit for project 1. 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![image](https://user-images.githubusercontent.com/86083871/147609309-f4e291a3-56a0-4be5-bfa2-5c57d2b4a331.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

[Ansible Files](https://github.com/HarjasSingh0/Project1Repository/tree/main/Ansible)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly avalible, in addition to restricting traffic to the network.
load balacers keep the systems safe from attacks from bad actors such as ddos attacks by redirecting the attack. And the jumpbox is a conviencent method a user can have access but he/she will is easliy monitored. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
filebeat watches for changes in files and when it happens
metricbeats just takes the statistics and metrics and outputs them to you. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| web1     |   sever  | 10.0.0.5   |          Linux   |
| web2     |   sever  | 10.0.0.6   |          Linux   |
| elk-vm   |   sever  | 10.1.0.4   |          Linux   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
my public ip address 

Machines within the network can only be accessed by _____.
jumpbox 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | public ip            |
|   web1   |           no        |      10.0.0.5        |
|    web2  |           no        | 10.0.0.6             |
    elk                no               10.1.0.4
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
main advantage is that we can put commands on multiple machines from just 1 script

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install: docker.io
- Install: python-pip
- Install: docker
- Command: sysctl -w vm.max_map_count=262144
- Launch docker container: elk
The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

/c/Users/Harjas Singh/Downloads/CompletedREADME/README/Images/dockerPS.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5
10.0.0.6
10.1.0.4
We have installed the following Beats on these machines:
web1, web2, elk-vm

These Beats allow us to collect the following information from each machine:
filebeat just collects the changes that happens and metric beats collects statistics and metrics. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?/etc/ansible/filebeat.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?/etc/ansible/host and then you have to add the elksever ip address
- _Which URL do you navigate to in order to check that the ELK server is running?
20.83.240.48:5601
