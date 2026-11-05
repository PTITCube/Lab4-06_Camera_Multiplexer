# Lab4-06_Camera_Multiplexer

**Chuyển mạch MUX giữa Camera (ESP32-CAM) & GPS**

Bài thực hành thuộc Lab4 (Sensor) trong hệ thống CubeSat-LMS.

### Mô tả:
Do cả GPS và ESP32-CAM đều giao tiếp nối tiếp qua UART, hệ thống vệ tinh PTITCube sử dụng IC ghép kênh (Multiplexer - MUX) để chia sẻ cổng UART2 của ESP32 OBC (RX=GPIO 16, TX=GPIO 17) giữa hai thiết bị:
- **Kênh Camera:** Chuyển mạch UART2 đến ESP32-CAM (sử dụng UART2 của CAM: TX=GPIO 14, RX=GPIO 15, tốc độ 115200 baud).
- **Kênh GPS:** Chuyển mạch UART2 đến module GPS NEO-xM (tốc độ 9600 baud).

### Chân điều khiển MUX từ ESP32 OBC:
- `gpsSelectPin`: GPIO 12
- `camSelectPin`: GPIO 14
