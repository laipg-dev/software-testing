## Giới thiệu ứng dụng quản lý sản phẩm
Ứng dụng bao gồm frontend, backend và hệ thống kiểm thử tự động (Automation + Performance), được đóng gói bằng Docker.

### Công nghệ sử dụng
- **Frontend:** ReactJS  
- **Backend:** Spring Boot, Spring Security  
- **Testing:**  
  - k6/Grafana (Performance Testing)  
  - Cypress (Automation Testing)  
  - JUnit 5 (Backend Unit Test)  
- **Database:** PostgreSQL  
- **Containerization:** Docker & Docker Compose  

### Tính năng chính
- Đăng nhập bằng username/password.
- Quản lý CRUD sản phẩm.
- API được bảo vệ bằng Spring Security.

---

## Hướng dẫn chạy ứng dụng

### 1. Yêu cầu hệ thống
Cần cài đặt:
- Docker Desktop  
- Git  
- Node.js  
- Java 21  
- Maven  

---

### 2. Hướng dẫn khởi chạy

#### Clone dự án:
```bash
git clone https://github.com/laipg-dev/software-testing.git
cd software-testing
```

#### Build frontend:
```bash
cd frontend
npm install
npm run build
cd ..
```

#### Khởi động ứng dụng bằng Docker Compose:
```bash
docker-compose up --build -d
```

#### Truy cập ứng dụng:
- **Frontend:** http://localhost:3000  
- **Backend:** http://localhost:8080  
- **Adminer:** http://localhost:8081  

---

## Hướng dẫn chạy test

### Frontend Unit Test:
```bash
cd frontend
npm test
```

### Frontend Automation Test (Cypress):
```bash
cd frontend
npm run test:e2e
```

### Backend Unit Test:
```bash
cd backend
mvn clean test
```

### Performance Test (k6):
```bash
cd backend
docker compose run k6 run login-test.js
docker compose run k6 run login-stress.js
docker compose run k6 run product-test.js
```
