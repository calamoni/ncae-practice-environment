## This is a test environment for the NCAE Cyber Games competition. 

### Please be aware that this environment has over 14 machines, not which need to all run concurrently, but scale at your own desire. 

### All of the necessary information and files will have their documentation provided in each section, there may or may not be mistakes. I would appreciate any corrections if found. 

### Hosted in the Proxmox hypervisor 

---
# Proxmox Setup

You will need to create a couple **Linux Bridges** to simulate the environment addressing scheme. 

1. Click your node and navigate to **Network** under **System**
2. Create two Linux Bridges (Name does not matter)
    - Assign the addressing scheme (E.g 172.18.0.0/16 for the External Network) && (E.g 192.168.15.0/24 for the Internal network)


# Scoring Engine 

For this scoring engine I used this repository: [https://github.com/scoringengine/scoringengine](https://github.com/scoringengine/scoringengine) which provides a fully fledged scoring engine and checks. I made the following changes to the competition configuration file which I will leave under the scoring engine directory in this repository. 

Steps: 
1. Install Make && Git
2. Git clone the repository provided above and start the original scoring engine with `docker compose up -d`
3. Replace the original competition configuration file `scoring-engine/bin/competition.yaml` with the one provided in this repository in the `scoreengine` directory
4. Run the command in the base directory of the original scoring engine repository `make rebuild-new`

---
# Hackathon Router (Upstream router)

For the Hackathon router I opted for the open-source router *opnsense*, it works and it works well most of the time. Feel free to use any software defined router of your liking. 

**Note** For access to this environment, I established VPN connectivity for all of my teammates, It is convenient especially when everyone cannot meet in-person all the time. 
    - As a workaround you can simply just use an access point or however you decide to connect to the environment. It's nice to have the jumphost as an option :)

1. Download opnsense && Install it [https://opnsense.org/download/](https://opnsense.org/download/)
2. Assign your interfaces their respective role (WAN, LAN)
    - The WAN will be your external address going out to the internet 
    - The LAN is going to be the external side of the competition 