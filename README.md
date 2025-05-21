# Installing, Configuring & Managing Nagios

## Objective
The objective of this lab is to show my ability to design and deploy a lab-based monitoring solution using Nagios Core that enables real-time health and performance monitoring of servers, services, and network devices. This lab serves as a learning platform to understand the practical implementation of IT infrastructure monitoring and alerting systems.

## Tools Used
- Microsoft Azure and Virtual Box for virtualization
- OS : RHEL 9.5 and Windows

### Skills Learned

- Application of cyber frameworks such as Diamond Model, Kill Chaun and time analysis to understand attacker behavior and impact.
- Cyber Threat Intelligence.
- Starting, stoping and managing docker.

## Components
### Virtualization Platform
- **Microsoft Azure:** Acts as the hypervisor hosting my server and windows client.
- **Virtual Box:** Acts as the hypervisor that hosting my RHEL client.

### Monitoring 
- **Nagios:**
  - Free, powerful monitoring and alerting for servers, networks, applications and services..
- **AllienVault Connector :**
  - a software component that i connected to OpenCTI to facilitates data integration and automation between AlienVault's Open Threat Exchange (OTX) OpenCTI.

### Operating System
- **RHEl 9.5:**
  -A popular, free and open-source Linux-based operating system. I used this as my server operating System which is used to deplor docker.
- **Windows 10:**

### SSH Client
- **Putty:**
  - I used this to connect with my remote Ubuntu server hosted in Azure.
    
## Configuration Steps

1. **Installing Required Packages:**
   - The first step I performed in this lab is to install all packages required to successfully deploy Nagios. The following packages were installed Apache web server, PHP development tool, make, unzip, wget and net-snmp.

  - Next, I created a nagios user "Habib" and a group "NagiosAdmin" and adding the user to the group. The purpose of creating the user and group is to ensure that only authorised users can run critical commands within Nagios
  
     
     <img src="images/vm1.png" alt="VM deployment" width="500">
     
   - Setting up inbound firewall rule to allow http traffic on port 8080 to allow me connect to the openCTI application via my web browser. 

    <img src="images/fw1.png" alt="Inbound firewall configuration" width="600">

1. **Installation, configuration and deployment of OpenCTI via docker:**
   - Connected to my OpenCTI1 server using putty to perform all installations and configuration.

    <img src="images/putty1.png" alt="Connecting to my server" width="600">
     
   - I downloaded and install the Docker Compose CLI plugin.

    <img src="images/dc1.png" alt="docker compose installation" width="500">

    - Next, I gained root access to my server and navigated to the /opt/ directory where I created a new directory /opencti/, navigated into the opencti directory and cloned this github directory git clone https://github.com/OpenCTI-Platform/docker.git

    <img src="images/clone.png" alt="cloning a github directory" width="500">
    
   - Configure the environment: I edited the .env file retrieved from cloning the above repository and edited the openCTL admin email and admin password fields to email and password of my preference. I also, set the base url to my Ubuntu server ip address to enable me access my openCTL application and finally generated UUID online to use in the healthcheck access key and admin token field.

    <img src="images/env1.png" alt="setting up environment variable" width="500">

- Next, I started docker service and ran the container in detached mode.

    <img src="images/cont.png" alt="Starting the Container" width="500">
  
   - Finally, I am able to access the OpenCTI application via my web browser using the server ip address on port 8080.
     
     <img src="images/openCTI.png" alt="OpenCTI login Page" width="500">
 
    - I proceeded to login using the email address and password I configured in the .env file.
 
       <img src="images/login.png" alt="OpenCTI login Page" width="500">
       
       <img src="images/dash.png" alt="OpenCTI login Page" width="500">

3. **Adding AlienVault Connector to OpenCTI:**

