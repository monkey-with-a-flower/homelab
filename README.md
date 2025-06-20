# homelab
My Homely setup and architecture 

```mermaid
%%{ init : { "theme": "default", "themeVariables": { "fontSize": "16px" }}}%%
flowchart TD
    A([🌐 Internet])
    B([📡 NetComm ISP Router])
    C([🛡️ pfSense Firewall])
    D([🖥️ Proxmox Server (PVE Node)])

    subgraph VMs
        D1([🪟 Windows VM])
        D2([🐉 Kali Linux VM (VNC Support)])
    end

    subgraph LXC Containers
        E1([📄 PaperNGX - Docs Storage])
        E2([🛠️ Pi-hole - DNS Filtering])
        E3([🔍 Mitmproxy - Traffic Intercept])
        E4([🔒 Netbird - VPN Access])
        E5([🌍 Pangolin (AWS tc2-micro)])
        E6([📊 Splunk - Log Monitoring])
        E7([🕵️ Snort - IDS Monitoring])
    end

    subgraph Backup
        F1([📂 rclone Cron Backup to Google Drive])
    end

    subgraph Client Devices
        G1([💻 Laptop])
        G2([📱 iPhones])
    end

    A --> B
    B --> C
    C --> D
    D --> VMs
    D --> LXC Containers
    D --> Backup
    C --> Client Devices
