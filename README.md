# Patrices-Elk-Project
# Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Elk network diagram](Images/elk network diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - _FILEBEAT_PLAYBOOK.YML

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting inbound access to the network.
- The load balancer ensures that work to process incoming traffic will be shared by both vulnerable web servers. Access controls will ensure that only authorized users — namely, ourselves — will be able to connect in the first place. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the file systems of the network and system metrics.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| NAME    	| PUBLICLY ACCESSIBLE 	| ALLOWED IP ADDRESSES  	|   	|   	|
|---------	|---------------------	|-----------------------	|---	|---	|
| Jumpbox 	| YES                 	| 20.39.54.251          	|   	|   	|
| elk     	| NO                  	| 10.1.0.4-254          	|   	|   	|
| DVWA1   	| NO                  	| 10.0.0.6-254          	|   	|   	|
| DVWA2   	| NO                  	| 10.0.0.7-254          	|   	|   	|
|         	|                     	|                       	|   	|   	|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:20.39.54.251


Machines within the network can only be accessed by eachother.
The DVWA1 and DVWA2 will allow to access your ELK VM with IP address 
10.0.0.7 and 10.0.0.6

A summary of the access policies in place can be found in the table below.

| NAME    	| PUBLICLY ACCESSIBLE 	| ALLOWED IP ADDRESSES  	|   	|   	|
|---------	|---------------------	|-----------------------	|---	|---	|
| Jumpbox 	| YES                 	| 20.39.54.251          	|   	|   	|
| elk     	| NO                  	| 10.1.0.4-254          	|   	|   	|
| DVWA1   	| NO                  	| 10.0.0.6-254          	|   	|   	|
| DVWA2   	| NO                  	| 10.0.0.7-254          	|   	|   	|
|         	|                     	|                       	|   	|   	|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/docker ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
-Filebeat
-Metricbeat
-Packetbeat

These Beats allow us to collect the following information from each machine:
- Filebeat: Filebeat detects changes to the filesystem. Specifically, we use it to collect Apache logs.

Metricbeat: Metricbeat detects changes in system metrics, such as CPU usage. We use it to detect SSH login attempts, failed sudo escalations, and CPU/RAM statistics.

Packetbeat: Packetbeat collects packets that pass through the NIC, similar to Wireshark. We use it to generate a trace of all activity that takes place on the network, in case later forensic analysis should be warranted.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to ansible note.
- Update the filebeat playbook file to include...
- Run the playbook, and navigate to DVWA Containers to check that the installation worked as expected.


- _The filebeat is the playbook and you copy it in the ansible container under the ansible directory 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
The  URL do you navigate to in order to check that the ELK server is running is http://10.1.0.4:5601/app/kibana 

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.

command line to download the playbook:ansible playbook filebeat-playbook.yml
