# CAMPUS HUB - DOCKER

Họ tên: Trần Minh Đức<br>
Mã sinh viên: PTIT-HCM-085

Source: https://github.com/dinhthanhnam/campus-hub-base

## Chạy ứng dụng

Yêu cầu Docker Desktop hoặc Docker Engine đang hoạt động.

```powershell
Copy-Item .env.example .env
docker compose config
docker compose up --build -d
docker compose ps
Invoke-RestMethod http://localhost:8080/actuator/health
```

Backend chạy tại http://localhost:8080. Health endpoint: http://localhost:8080/actuator/health.

Kiểm thử backend trước khi build image:

```powershell
Set-Location backend
.\gradlew.bat test
Set-Location ..
```

Compose truyền cấu hình database qua `DB_URL`, `DB_USERNAME` và `DB_PASSWORD`. Backend kết nối tới service `mysql` trên network nội bộ. Giá trị trong `.env.example` chỉ dùng cho môi trường thực hành; không dùng lại mật khẩu này ở môi trường thật.

## Minh chứng

Ảnh Docker image, trạng thái Compose và health endpoint sẽ được bổ sung sau khi Docker Engine chạy được trên máy kiểm thử.
