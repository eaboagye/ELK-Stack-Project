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

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_


| Name          | Function | IP Address | Operating System |
|----------     |----------|------------|------------------|
| Jump Box      | Gateway  | 10.0.0.1   | Linux            |
| VM 1          |          | 10.0.0.1   | Linux            |
| Load Balancer |          | 10.0.0.1   | Linux            |
| VM 2          |          | 10.0.0.1   | Linux            |
| VM 3          |          | 10.0.0.1   | Linux            |
| VM 4 - ELK    |          | 10.0.0.1   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

