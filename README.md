## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.
https://app.diagrams.net/#HJames-gift%2FProject-1---ELK%2Fmain%2FAnsible%2FUntitled%20Diagram.drawio 

files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _filebeat-config.yml , metricbeat-playbook.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly availible , in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? Ensures high availability and reliability by sending requests only to servers that are online. What is the advantage of a jump box?_ A jump box is a secure computer that all admins first connect to before launching any administrative task or use as an origination point to connect to other servers or untrusted environments.
- Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs. 
- _TODO: What does Filebeat watch for?_Filebeat is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers, Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- _TODO: What does Metricbeat record?_ Metricbeat is a lightweight agent that can be installed on target servers to periodically collect metric data from your target servers, this could be operating system metrics such as CPU or memory or data related to services running on the server. It can also be used to monitor other beats and ELK stack itself.
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| ELK      |          | 10.2.0.4   | Linux            |
| Web1     |          | 10.0.0.4   | Linux            |
| Web2     |          | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ElK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:40.76.216.24, 40.77.99.127
- _TODO: 40.76.216.24, 40.77.99.127
-  
Machines within the network can only be accessed by .
- _TODO: _40.76.216.24

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: Servcies running can be limited, system installation and update can be streamlined, and processes become more replicable. 

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://github.com/James-gift/Project-1---ELK/blob/main/Project%201%20docker%20ps.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ 10.0.0.4, 10.0.0.6
We have installed the following Beats on these machines:
- _TODO: Metricbeats , Filebe_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._ 

Filebeat collects log file data.

Metricbeat collects system metric data related to cpu and memory usage as well as other system statistics.

What you'd look to see is that this data is connected to kibana on the elk server and that the dashboards give you a visualization of that data so it can be monitored easily.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to SSH.
- Update the _____ file to include...
- Run the playbook, and navigate to Filebeat installation page to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? /etc/ansible/hosts  Where do you copy it?_ in the src parameter, on the local machine. And then it will copy the file to the remote machine path specified in the dest path.  
- _Which file do you update to make Ansible run the playbook on a specific machine? Ansible works with an inventory file. How do I specify which machine to install the ELK server on versus which to install Filebeat on?- Only the Elk Server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: Workstation Public IP through TCP 5601. Which URL do you navigate to in order to check that the ELK server is running? Only the Elk Server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: Workstation Public IP through TCP 5601.nan

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
