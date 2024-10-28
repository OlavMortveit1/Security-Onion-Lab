# Security-Onion-Lab
This project sets up an isolated internal network utilizing **Security Onion** for network security monitoring and analysis. It features two **Kali Linux** machines to simulate penetration testing activities. 

## Project Structure
- **Kali Attacker**: Used to perform network scans and attacks.
- **Kali Victim**: Simulates a target for testing and analysis.
- **Security Onion**: Monitors traffic between the attacker and victim, capturing logs and events for analysis.

## Setup Instructions

### Prerequisites
- Virtualization software (e.g., VirtualBox or VMware)
- ISO images for Kali Linux and Security Onion
- Basic knowledge of networking and Linux commands

### Step 1: Create Virtual Machines
1. Create three virtual machines:
   - **Kali Attacker**
   - **Kali Victim**
   - **Security Onion** (Airgapped)
   
2. Configure all VMs to use an **Internal Network** in your virtualization platform.

### Step 2: Configure Network Settings
1. Assign the following static IP addresses (what I used but you can use whatever suits you):
   - **Kali Attacker**: `192.168.1.2/24`
   - **Kali Victim**: `192.168.1.5/24`
   - **Security Onion Management IP**: `192.168.1.3/24`
   - **Security Onion Monitor IP**: `192.168.1.4/24`

## Step 3: Check That The Network Configurations Work
1. Confirm connectivity by using the `ping` command from each machine.
2. Access the Security Onion web interface on the attackers machine (or victim if you want to, but I chose attacker) by typing `http://192.168.1.3` into the web browser.

## Step 4: Start Scanning From Attacker
1. Run Nmap Scan
   - Use nmap to scan the victim machine from the attackers machine. This should trigger alerts in Security Onion.
   - After scanning, check Security Onion's dashboard to confirm detection.
   - This is only an example of what you can do to trigger alerts.

## Other Ideas To Try
- Try different scan types, such as UDP scans or version detection scans, to see how Security Onion responds.
- Experiment with other tools like **Netcat** or **Metasploit** to generate different kinds of alerts and observe the varied logs.
