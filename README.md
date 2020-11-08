# ELK-Stack-Project / # Automated ELK Stack Deployment

Before begining with the ELK-STACK Deployment, below are the prequisite to follow:

Prerequisites

To run a container, you will need the following:

    DOCKER

    Install Docker, either using a native package (Linux) or wrapped in a virtual machine. In this case, the docker was installed on a virtual machine using Microsoft Azure.

    A minimum of 4GB RAM assigned to the Docker

    Elasticsearch alone needs at least 2GB of RAM to run.


Setting up an Elk Stack Server to monitor cloud network using Microsoft Azure.

The ELK stack allows analysts to:

Easily collect logs from multiple machines into a single database.

Quickly execute complex searches, such as: Find the 12 internal IP addresses that sent the most HTTP traffic to a gateway between selected date range.

Build graphs, charts, and other visualizations from network data.


The files in this repository were used to configure the network depicted below.

(Red Team Full Network Diagram with ELK.JPG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

##  Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available and responsive, in addition to restricting unauthorized access to the network.
The -load balancer sits between client devices and backend servers, receiving and then distributing incoming requests to any available server capable of fulfilling them.
The load balancers protect an organization against distributed denial-of-service (DDoS) attacks. It does this by shifting attack traffic from the corporate server to a public cloud provider. A jump box is a secure computer that all admins first connect to before launching any administrative task or use as an origination point to connect to other servers or untrusted networks.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat monitors log files and collects log events then forward these logs to the Elasticsearch.
- Metricbeat gather and collect metrics from the serving running on the machine and the operating system.


| Name          | Function                   | IP Address | Operating System |
|---------------|--------------------------- |------------|------------------|
| Jump Box      | Gateway                    | 10.0.0.5   | Linux            |
| VM 1          | Docker                     | 10.0.0.6   | Linux            |
| VM 2          | Docker                     | 10.0.0.7   | Linux            |
| VM 3          | Docker                     | 10.0.0.8   | Linux            |
| VM 4 - ELK    |Management of system logs   | 10.1.0.5   | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elk Server machine can accept  can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 10.0.0.5
  10.0.0.6
  10.0.0.7
  10.0.0.8

Machines within the network can only be accessed by the Jump Box. Its IP address is 10.0.0.5


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | Admin IP             |
| VM 1     | No                  | 10.0.0.5             |
| VM 2     | Np                  | 10.0.0.5             |
| VM 3     | No                  | 10.0.0.5             |
| VM 4 -ELK| No                  | 10.0.0.5             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it is easy to use and determine the flow of data configuations on the various machines. The Ansible helps with easy system automations as well.


The playbook implements the following tasks: 

1. Creating the Elk Stack on a new virtual Machine.
2. Downloading and configuring the Elk Stack on the virtual machine using an ansible-playbook.
3. Launching and exposing the container to verify if there are no installations and connection errors from the JumpBox. Then you create an inbound and outbound security policies or rules to help from unauthorized access.


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-  
   VM 1 WEB - 10.0.0.6
   VM 2 WEB - 10.0.0.7
   VM 3 WEB - 10.0.0.8

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat forwards and centralize log data. It collects log events, monitors locations or log files and forwards them either to Elasticsearch for indexing and configurations.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat.yml file to the directory of /etc/ansible/roles/files/
- Update the configuration file to include the Private IP Address of ELk-Sever.
- Run the playbook, and navigate to the Elk-Server to check that the installation worked as expected.


- Note that the playbook file is the Ansible-Playbooks_filebeat-playbook.yml

- _The filebeat.yml file which is a configuration file is the file to update to make Ansible run the playbook on a specific machine. How do I specify which machine to install the ELK server on versus which to install Filebeat on?_


