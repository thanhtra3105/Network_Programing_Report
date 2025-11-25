# Network_Programing_Report
Project này là **server điều khiển và giám sát UAV/Drone** bằng MAVLink, viết bằng Python + Flask.  
Được phát triển bởi ...

## Cấu trúc thư mục
source/
├── __pycache__/
├── logs/
│   ├── command_rtt/
│   │   └── command_rtt.csv
│   ├── latency_and_loss/
│   │   ├── mission-progress_latency.csv
│   │   ├── vehicle-info_latency.csv
│   │   └── vehicle-position_latency.csv
│   └── px4_data/
│       └── px4_data_log.csv
├── static/
│   ├── boat.png
│   ├── script.js
│   └── style.css
├── templates/
│   ├── base.html
│   ├── dashboard.html
│   ├── index.html
│   └── stream.html
├── requirements.txt
├── server.py
└── README.md
