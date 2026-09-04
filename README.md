# Network-Device-Monitoring-Dashboard

Network-Device-Monitoring-Dashboard/
│
├── monitor.py
├── database.py
├── requirements.txt
├── README.md
│
├── database/
│   └── devices.db
│
├── screenshots/
│   ├── dashboard.png
│   ├── online.png
│   └── reports.png
│
└── docs/
    └── project_report.pdf
Features

✅ Monitor Device Status

✅ Online/Offline Detection

✅ Network Monitoring

✅ Device Reports

✅ Dashboard Interface

README.md
# Network Device Monitoring Dashboard

## Overview

A Python application used to monitor network devices and determine whether devices are online or offline.

## Features

- Device Monitoring
- Network Diagnostics
- Online/Offline Status
- Device Reporting
- Dashboard Interface

## Technologies

- Python
- SQLite
- Tkinter

## Installation

```bash
git clone https://github.com/yourusername/Network-Device-Monitoring-Dashboard.git
cd Network-Device-Monitoring-Dashboard
pip install -r requirements.txt
python monitor.py
```

## Skills Demonstrated

- Networking
- Python Programming
- Troubleshooting
- Monitoring Solutions
Core Code (monitor.py)
import subprocess
from tkinter import *

def ping_device():
    host = ip_entry.get()

    response = subprocess.call(
        ["ping", "-n", "1", host],
        stdout=subprocess.DEVNULL,
        stderr=subprocess.DEVNULL
    )

    if response == 0:
        result.config(text="ONLINE")
    else:
        result.config(text="OFFLINE")

root = Tk()
root.title("Network Device Monitoring Dashboard")

Label(root,text="IP Address").pack()

ip_entry = Entry(root)
ip_entry.pack()

Button(root,text="Check Status",command=ping_device).pack()

result = Label(root,text="")
result.pack()

root.mainloop()
