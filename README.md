# 🎓 Hệ thống đăng ký đề tài đồ án (Microservices)

## 👨‍🎓 Thành viên nhóm

| Họ và tên       | Mã số sinh viên | Vai trò           | Đóng góp                                      |
| --------------- | --------------- | ----------------- | --------------------------------------------- |
| Đinh Viết Chiến | B22DCVT076      | Backend Developer | API Gateway, User Service                     |
| Phạm Đức Thiện  | B22DCDT309      | Backend Developer | Topic Service, Registration Service, Frontend |



## 📌 Mô tả dự án

Dự án xây dựng hệ thống **đăng ký đề tài đồ án tốt nghiệp** theo kiến trúc **Microservices**.

Hệ thống giúp tự động hóa quy trình:

* Giảng viên tạo và quản lý đề tài
* Sinh viên tìm kiếm và đăng ký đề tài
* Giảng viên xét duyệt đăng ký
* Hệ thống lưu trữ và cập nhật kết quả

👉 Giải pháp sử dụng **API Gateway kết hợp các dịch vụ độc lập**, giúp hệ thống dễ mở rộng và bảo trì.



## 🚀 Bắt đầu

Để thiết lập và chạy dự án, xem file:

👉 `GETTING_STARTED.md`

Nội dung bao gồm:

* Hướng dẫn cài đặt môi trường
* Quy trình làm việc
* Checklist nộp bài



## 🔄 Quy trình nghiệp vụ

**Đăng ký và xét duyệt đề tài đồ án**

### Tác nhân

* Sinh viên
* Giảng viên
* Quản trị viên

### Quy trình

1. Quản trị viên tạo tài khoản người dùng
2. Giảng viên tạo đề tài
3. Sinh viên xem danh sách đề tài
4. Sinh viên đăng ký đề tài
5. Hệ thống kiểm tra điều kiện
6. Giảng viên xét duyệt (duyệt / từ chối)
7. Hệ thống cập nhật kết quả đăng ký



## 🏗️ Kiến trúc hệ thống

(Sơ đồ chi tiết xem trong ` docs/architecture.md `)

```mermaid
flowchart LR
    A[Người dùng] --> B[Frontend :3000]
    B --> C[API Gateway :8080]
    C --> D[User Service :5001]
    C --> E[Topic Service :5002]
    C --> F[Registration Service :5003]


### Thành phần hệ thống

| Thành phần           | Chức năng                    | Công nghệ         | Cổng |
| -------------------- | ---------------------------- | ----------------- | ---- |
| Frontend             | Giao diện người dùng         | React             | 3000 |
| API Gateway          | Điều phối request            | Node.js + Express | 8080 |
| User Service         | Quản lý tài khoản, đăng nhập | Node.js + Express | 5001 |
| Topic Service        | Quản lý đề tài               | Node.js + Express | 5002 |
| Registration Service | Xử lý đăng ký và xét duyệt   | Node.js + Express | 5003 |


## ⚡ Hướng dẫn nhanh

Chạy hệ thống:

```bash
docker compose up --build
```

Xác minh:

```bash
curl http://localhost:8080/health
curl http://localhost:5001/health
curl http://localhost:5002/health
curl http://localhost:5003/health
```



## 📚 Tài liệu

| Tài liệu                        | Mô tả                           |
| ------------------------------- | ------------------------------- |
| GETTING_STARTED.md              | Hướng dẫn thiết lập và workflow |
| docs/analysis-and-design.md     | Phân tích & thiết kế hệ thống   |
| docs/analysis-and-design-ddd.md | Thiết kế theo DDD               |
| docs/architecture.md            | Kiến trúc hệ thống              |
| docs/api-specs/                 | Định nghĩa API (OpenAPI)        |



## 📄 Giấy phép

Dự án sử dụng giấy phép MIT.



## 🙏 Ghi chú

Dự án được thực hiện phục vụ môn **Phát triển phần mềm hướng dịch vụ**.
