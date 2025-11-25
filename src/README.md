# UAV/Drone Control and Monitoring Server

This project is a **UAV/Drone control and monitoring server** using MAVLink protocol, built with Python + Flask.

---

## Directory Structure
```
source/
├── __pycache__/                      # Python bytecode cache
├── logs/                             # System logs
│   ├── command_rtt/                  # Command Round Trip Time
│   │   └── command_rtt.csv
│   ├── latency_and_loss/             # Network latency and packet loss
│   │   ├── mission-progress_latency.csv
│   │   ├── vehicle-info_latency.csv
│   │   └── vehicle-position_latency.csv
│   └── px4_data/                     # PX4 flight controller data
│       └── px4_data_log.csv
├── static/                           # Static assets
│   ├── boat.png                      # Vehicle icon
│   ├── script.js                     # Client-side JavaScript
│   └── style.css                     # Stylesheet
├── templates/                        # HTML templates
│   ├── base.html                     # Base template
│   ├── dashboard.html                # Dashboard interface
│   ├── index.html                    # Home page
│   └── stream.html                   # Data stream display
├── requirements.txt                  # Python dependencies
├── server.py                         # Main server file
└── README.md                         # Documentation
```

---

## Requirements

- **Operating System**: Ubuntu
- **Flight Controller**: PX4
- **Python**: 3.12+
- **Virtual Environment**: Recommended
- **Python Libraries**:
  - flask
  - flask-cors
  - pymavlink

---

## Installation and Setup

### 1. Clone the Repository
```bash
git clone https://github.com/thanhtra3105/Network_Programing_Report.git
cd Network_Programing_Report
```

### 2. Create Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Server
```bash
python source/server.py
```

Server will run on port: **5000**

---

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Home page |
| `/telemetry` | GET | Monitoring dashboard |
| `/api/telemetry` | GET | Telemetry data (JSON) |
| `/upload-mission` | POST | Upload mission planning |
| `/start-mission` | POST | Start mission execution |
| `/vehicle-position` | GET | UAV GPS position |
| `/vehicle-info` | GET | UAV information (speed, battery, heading) |
| `/mission-progress` | GET | Mission progress status |
| `/get-mission` | GET | List of uploaded missions |

---

## Logging System

The server automatically logs data to the following directories:

- **Latency & Packet Loss**: `logs/latency_and_loss/`
  - Monitors network latency across different data channels
  
- **PX4 Data**: `logs/px4_data/px4_data_log.csv`
  - Records telemetry data from the flight controller
  
- **Command RTT**: `logs/command_rtt/command_rtt.csv`
  - Measures response time for control commands

*Directories will be automatically created if they don't exist.*

---

## References

- [Flask Documentation](https://flask.palletsprojects.com/)
- [MAVLink Developer Guide](https://mavlink.io/)
- [PX4 Autopilot](https://docs.px4.io/)

---

**© Copyright thanhtra3105**
