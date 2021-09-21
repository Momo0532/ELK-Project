# ELK-Project
## ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

These files have were modified and tested to generate na ELK deployment on Azure. They can be used to initialize and recreate the ELK-Stack project.

The following document contains:

- Description of the Topology

- Access Policies

- ELK Configuration

  1.Beats 

  2.Machines Being Monitored

  3.The Ansible Build

### Description of the Topology

The main purpose of this network is to describe the  load-balanced and monitor the instances containing  the Damn Vulnerable Web Application.

Load balancing will ensure that the application would  be available and  in addition to restricting unauthorized accesss to the network. Load balancers are an important tool that  can help against a DDos attack. Jump boxes are usefull tool they provide access point for administrative tasks. JumpBoxes are considered  Secure Admin Worstation(SAW), which enables  an administrator to access the JumpBox before accesssing the servers.

Integrating an ELK server allows users to monitor vulnerable VMs for changes to logs and system traffic.

1. Filebeat watches for log files/locations and collects events related to those files and locations.
2. Metricbeat records metrics and statistical data from the operating system and services that are running on the server.

The configuration details of each machine may be found below.

| Name     | Function   | IP Address | Public IP Address | Operating System |
| -------- | ---------- | ---------- | ----------------- | ---------------- |
| Jump Box | Gateway    | 10.0.0.4   | 20.191.96.61      | Linux            |
| Web-1    | Web Server | 10.0.0.5   | 20.98.104.71      | Linux            |
| Web-2    | Web Server | 10.0.0.6   | 20.98.104.71      | Linux            |
| ELK-VM   | ELK Stack  | 10.2.0.4   | 20.106.89.128     | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the JumpBox Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from an single IP Address

Machines within the network can only be accessed by SSH. 1. The ELK Server is only accessible by SSH from the JumpBox.

A summary of the access policies illustrated in the  table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
| -------- | ------------------- | -------------------- |
| Jump Box | Yes/No              | Set in RedTeam-SG    |
| Web-1    | No                  | 10.0.0.4             |
| Web-2    | No                  | 10.0.0.4             |
| ELK-VM   | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. 

1. The primary  advantage of automation was the  installation process that one could  spin-up multiple servers effectiently and quickly.Another plus is  avoiding  manually configuring each server.

The playbook runs the following tasks:

1. Configures the machine with Docker.
2. Installs Docker.io and pip3.
3. Downloads and configures ELK docker container.
4. Activates ports 5601, 9200, and 5044.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

### Target Machines & Beats

This ELK server is configured to monitor the following machines:

1. Web-1 10.0.0.5
2. Web-2 10.0.0.6

We have installed the following Beats on these machines:

1. Filebeat
2. Metricbeat

These Beats allow us to collect the following information from each machine:

1. Filebeat watches for log files/locations and collects events related to those files and locations.
2. Metricbeat records metrics and statistical data from the operating system and services that are running on the server.

### Using the Playbook

To use the playbook, you will need to have an Ansible control node already configured. 

SSH into the control node and follow the steps below:

- Copy the install_elk_yml file to your /etc/ansible/roles directory.
- Update the host file to include the IP Addresses of your Web-1, Web-2, and ELK server as well as assign python3 as the interpreter.
- Run the playbook, and navigate to your ELK server to check that the installation worked as expected.

Navigate to [http://publicip(elkserver):5601](http://publicip(elkserver):5601/) to check that the installation worked as expected.
