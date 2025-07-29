# Mesh-Network-Creation
Creating a home mesh network and configuring security

📡 Mesh Network Config <br>
A segmented, three-node mesh network built for secure home connectivity and practical threat modeling.

🛠 Overview <br>
This project documents the configuration and architecture of a home mesh network composed of three Deco nodes. It applies cybersecurity principles like network segmentation, minimal exposure, and strong authentication to create a secure and flexible environment for daily use and learning.

🔗 Nodes <br>
- Main Node: Central routing hub
- Living Room Node: Mesh endpoint for smart devices and streaming
- Office Node: Mesh endpoint for workstations and project lab

🧱 VLAN Architecture <br>
The network is divided into three VLANs for traffic isolation and tailored access control:
| VLAN ID | Purpose | Devices | 
| 10 | Workstations VLAN | Laptops, desktops, mobile phones | 
| 20 | IoT VLAN | Smart bulbs, plugs, appliances | 
| 30 | Guest VLAN | Visitors’ phones and laptops | 

- VLAN10 is prioritized for trusted, productivity-related devices.
- VLAN20 contains all IoT endpoints and is isolated to prevent lateral movement.
- VLAN30 allows guest access to the internet without exposure to critical infrastructure.

🔐 Access Control Strategy <br>
To maintain network integrity without exposing sensitive internal details, the setup leverages the built-in application for the mesh system to manage device connections. A strict whitelisting approach ensures only authorized devices can join the network. Signal strength has been calibrated to remain within the physical boundaries of the home, reducing potential external access. A strong, unique password secures all wireless communications, and notifications are enabled for any new connection attempts. Port forwarding is pre-configured for future flexibility but remains disabled to minimize the attack surface.

⚙️ Configuration Notes <br>
Configuration was handled entirely via the Deco mobile application:
- VLANs were configured directly within the Deco app, allowing internal traffic segmentation without external hardware.
- SSID separation for each VLAN
- Whitelisted MAC addresses
- No open ports enabled
- Signal strength tuned to reduce bleed beyond property perimeter

📊 Monitoring & Observations <br>
Basic connection tracking and new-device alerts are configured within the Deco app. While Deco’s capabilities are limited, additional network inspection and anomaly detection are performed via auxiliary tools such as:
- Wireshark (for packet analysis during test sessions)
- Pi-hole integration (not yet implemented) is being considered to enable DNS query logging and potential ad/malware domain blocking.

🌟 Limitations & Future Improvements <br>
While Deco provides reliable mesh coverage, it lacks advanced firewall rule creation and VLAN management. Future plans may include:
- Integrating pfSense or Firewalla for advanced traffic control
- Expanding network visibility with Netdata or Grafana dashboards
- Setting up device-level intrusion alerts for IoT devices
