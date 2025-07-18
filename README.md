# Personal Firewall using Python

A lightweight and customizable personal firewall developed using Python. It monitors network traffic in real-time, allows/blocks traffic based on user-defined rules, and supports GUI-based monitoring.

---

##  Features

-  Real-time packet sniffing using Scapy
-  Customizable rules for IP, port, and protocol filtering
-  Logging of suspicious or dropped packets
-  Optional system-level rule enforcement using `iptables` (Linux only)
-  GUI interface (Tkinter) for live monitoring and rule management

---

## Project Structure

```
personal-firewall-python/
├── firewall.py                  # Core logic (packet sniffing + rule checking)
├── gui.py                       # Optional GUI for monitoring and rule control
├── rules.json                   # JSON-based firewall rule set
├── logs/
│   └── firewall.log             # Log file storing suspicious/dropped packets
├── utils.py                     # Helper functions (e.g., logging, rule parser)
├── requirements.txt             # Python dependencies
├── README.md                    # Project documentation
└── report/
    └── Personal_Firewall_Report.docx  # Project report (editable format)
```

---

##  Technologies Used

- Python 3.x  
- [Scapy](https://scapy.readthedocs.io/en/latest/) – Packet sniffing and analysis  
- [Tkinter](https://docs.python.org/3/library/tkinter.html) – GUI (Optional)  
- `iptables` – Optional system-level firewall (Linux only)  
- Logging module

---

##  How It Works

1. **Sniffs** incoming and outgoing packets using Scapy.
2. **Applies rules** defined in `rules.json` (e.g., block IPs, specific ports).
3. **Logs** suspicious or dropped packets to `logs/firewall.log`.
4. **Optionally** applies permanent rules via Linux `iptables`.
5. GUI allows users to:
   - View active connections
   - Add/remove rules
   - View log entries live

---

## Getting Started

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Run Firewall (CLI Mode)

```bash
sudo python3 firewall.py
```

### 3. Run with GUI

```bash
sudo python3 gui.py
```

>  Note: Root privileges (`sudo`) are required to sniff packets and manage iptables rules.

---

##  Rule Format (`rules.json`)

```json
[
  {
    "action": "block",
    "protocol": "TCP",
    "src_ip": "192.168.1.100",
    "dst_port": 22
  },
  {
    "action": "allow",
    "protocol": "ICMP"
  }
]
```

- `action`: `"block"` or `"allow"`
- `protocol`: `"TCP"`, `"UDP"`, `"ICMP"`
- `src_ip`, `dst_ip`, `src_port`, `dst_port`: Optional filters

---

## Logs

All suspicious or dropped packets are saved to:

```
logs/firewall.log
```

Each entry includes:
- Timestamp
- Source IP
- Destination IP
- Protocol
- Action Taken

---

## Project Report

The full report is available in the `report/` folder:

- **Personal_Firewall_Report.docx** – Editable report with Introduction, Abstract, Tools Used, Steps, and Conclusion.

---

##  License

This project is licensed under the [MIT License](LICENSE). Feel free to fork and modify!

---

##  Author

Developed by: *Rahi Shah*  
GitHub: [github.com/yourusername](https://github.com/rahi1701)
