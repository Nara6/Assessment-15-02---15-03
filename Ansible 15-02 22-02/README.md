# Assessment Ansible
## Purpose
<b>NGINX</b> is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more.
It started out as a web server designed for maximum performance and stability.
In this demo, we want you to be able to install the service to the 3 clients' machines in different OS with one ansible script. So Users are
able to access host a web application.
You have to use docker for the client machines and an ansible script to do this.
## Detail Description
- Create 3 clients' machines using:
    - Ubuntu
    - CentOS
    - Debian
- From the Master, the machine installs the Nginx service to all the client machines
    - Install Nginx Service
    - Enable Nginx Service
Output
- Ensure that the Nginx service is installed
- Ensure that the Nginx service is enabled