# Lightweight Cybersecurity Lab using Docker

## Overview
This lab leverages Docker to run vulnerable applications in isolated containers on a dedicated Kali Linux host. This provides a safe, portable, and easily resettable environment for penetration testing practice.

## Tools Used
- **Host OS:** Kali Linux
- **Containerization:** Docker.io
- **Target:** DVWA (Damn Vulnerable Web Application) Container

## Lab Setup Steps
1.  Update Kali Linux: `sudo apt update && sudo apt full-upgrade -y`
2.  Install Docker: `sudo apt install docker.io -y`
3.  Add user to the docker group: `sudo usermod -aG docker $USER`
4.  Log out and back in (or run `newgrp docker`).
5.  Deploy the DVWA container:
    ```bash
    docker run --rm -d -p 80:80 vulnerables/web-dvwa
    ```

## Proof of Concept
The DVWA application was successfully accessed at `http://127.0.0.1` from the host machine.

![DVWA Login Page](https://raw.githubusercontent.com/wasif-rahman/cybersecurity-docker-lab/main/dvwa_login.png)

## Container Management
- List running containers: `docker ps`
- Stop a container: `docker stop <CONTAINER_ID>`
- Important: After a system reboot, simply re-run the `docker run...` command to restart the lab.

## Purpose
This lab will be used for hands-on practice with tools like Nmap, Metasploit, and Burp Suite as part of my cybersecurity portfolio.
