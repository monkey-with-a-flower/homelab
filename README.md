```mermaid
flowchart TB
    A[🌐 Internet] --> B[📡 NetComm ISP Router]
    B --> C[🛡️ pfSense Firewall]
    C --> D[🖥️ Proxmox Server - PVE Node]

    D --> D1[🪟 Windows VM]
    D --> D2[🐉 Kali Linux VM - VNC Support]

    D --> Containers
    subgraph Containers
        E1[📄 PaperNGX - Docs Storage]
        E2[🛠️ Pi-hole - DNS Filtering]
        E3[🔍 Mitmproxy - Traffic Intercept]
        E4[🔒 Netbird - VPN Access]
        E5[🌍 Pangolin - AWS tc2-micro]
        E6[📊 Splunk - Log Monitoring]
        E7[🕵️ Snort - IDS Monitoring]
    end

    D --> F1[📂 rclone Cron Backup → Google Drive]

    C --> Clients
    subgraph Clients
        G1[💻 Laptop]
        G2[📱 iPhones]
    end
