## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Cloud Security Diagram](Diagram/cloud-sercurity.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly `redundant`, in addition to restricting `access` to the network.
- What aspect of security do load balancers protect? Load balancers protect the availability of the servers.
- What is the advantage of a jump box? The advantage of a jump box provides us SSH access to our backend of the web servers. It reduces the attack vectors that hackers have to our backend of our web servers.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- What does Filebeat watch for?_
  - It watches SSH logins, linux account logins, and sudo commands.
- What does Metricbeat record?
  - It watches for CPU, RAM, and network usage.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.2.0.4	  | Linux            |
|   Web-1     |  Web Server    |  10.2.0.7          |    Linux                |
|   Web-2    |    Web Server   |   10.2.0.8         |        Linux            |
| Elk-Server  |    Elk-Stack      | 10.3.0.4           |     Linux               |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the `jumpbox` machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _Only my personal IP address has access to the Jumpbox and no one else._

Machines within the network can only be accessed by `jumpbox`.
- _Which machine did you allow to access your ELK VM? What was its IP address?_
    - `Jumpbox and Jumpbox's IP:10.2.0.4`

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes             | My Personal IP |
|  Web-1       |    No                 |   Jumpbox IP:10.2.0.4       |
|  Web-2        |     No                |   Jumpbox IP: 10.2.0.4                   |
|  Elk      |        No             |        Jumpbox IP: 10.2.0.4              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because we can use Ansible to streamline all the commands to all the virtual machines in one go. This will also produce less human errors and save us time.
- What is the main advantage of automating configuration with Ansible?
   - It saves us time and produces less human errors.

The playbook implements the following tasks:
- In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Configure Elk VM with Docker; Install docker. io 
- Install pip3
-Install Docker Python module; use more memory
-download and launch a docker elk container
-Enable service docker on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Cloud Docker Diagram](Diagram/cloud-docker.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring: Web 1 - IP Address: 10.2.0.7
Web 2 - IP Address: 10.2.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed: Installed Filebeats and Metricbeats

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
FileBeats: It watches SSH logins, linux account logins, and sudo commands
MetricBeats: It watches for CPU, RAM, and network usage.
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to etc/ansible.
- Update the playbook file to include the host name 
- Run the playbook, and navigate to the targeted server to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbookv-the playbook is install-filebeat? Where do you copy it? - to the etc/ansible folder_
- _Which file do you update to make Ansible run the playbook on a specific machine - the host file? How do I specify which machine to install the ELK server on versus which to install Filebeat on?to specify, the host name file is edited on playbook file
- _Which URL do you navigate to in order to check that the ELK server is running? IP address of the Elk Server

