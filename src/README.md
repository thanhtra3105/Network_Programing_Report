Project này là **server điều khiển và giám sát UAV/Drone** bằng MAVLink, viết bằng Python + Flask.  
Được phát triển bởi ...

## Cấu trúc thư mục
```
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
```

## Yêu cầu
- Hệ điều hành Ubuntu
- PX4
- Python 3.12+  
- Virtual environment
- Các thư viện Python:
  - flask
  - flask-cors
  - pymavlink

---

## Cài đặt và chạy server

### 1. Clone repo về
```bash
git clone https://github.com/thanhtra3105/Network_Programing_Report.git
cd Network_Programing_Report
```
### 2. Tạo virtual environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Cài thư viện
```bash
pip install -r requirements.txt
```
### 4. Chạy server
```bash
python source/server.py
```

Server sẽ chạy tại port: 5000

## API Endpoints

| Endpoint | Phương thức | Mô tả |
|----------|-------------|-------|
| `/` | GET | Trang chủ |
| `/telemetry` | GET | Dashboard giám sát |
| `/api/telemetry` | GET | Dữ liệu telemetry (JSON) |
| `/upload-mission` | POST | Upload mission planning |
| `/start-mission` | POST | Bắt đầu mission |
| `/vehicle-position` | GET | Vị trí GPS của UAV |
| `/vehicle-info` | GET | Thông tin UAV (tốc độ, pin, hướng) |
| `/mission-progress` | GET | Trạng thái tiến trình mission |
| `/get-mission` | GET | Danh sách mission đã upload |

## 📊 Hệ Thống Logging

Server tự động ghi log vào các thư mục sau:

- **Latency & Packet Loss**: `logs/latency_and_loss/`
  - Theo dõi độ trễ mạng cho các kênh dữ liệu khác nhau
  
- **PX4 Data**: `logs/px4_data/px4_data_log.csv`
  - Ghi nhận dữ liệu từ flight controller
  
- **Command RTT**: `logs/command_rtt/command_rtt.csv`
  - Đo thời gian phản hồi của các lệnh điều khiển

*Các thư mục sẽ được tự động tạo nếu chưa tồn tại.*

## Tài Liệu Tham Khảo

- [Flask Documentation](https://flask.palletsprojects.com/)
- [MAVLink Developer Guide](https://mavlink.io/)
- [PX4 Autopilot](https://docs.px4.io/)

---

**@Copyright thanhtra3105**
