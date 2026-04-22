🎓 Hệ thống đăng ký đề tài đồ án - Microservices


📌 Mô tả dự án


Dự án xây dựng hệ thống đăng ký đề tài đồ án tốt nghiệp theo kiến trúc hướng dịch vụ (Microservices).


Hệ thống giúp tự động hóa quy trình:


Sinh viên tìm kiếm và đăng ký đề tài

Giảng viên tạo và quản lý đề tài

Giảng viên xét duyệt đăng ký

Hệ thống lưu trữ và cập nhật kết quả


👉 Giải pháp sử dụng API Gateway + các dịch vụ độc lập giúp hệ thống dễ mở rộng và bảo trì.

🚀 Bắt đầu

Bạn mới sử dụng kho lưu trữ này?

Hãy xem GETTING_STARTED.md để biết:


Cách thiết lập môi trường

Quy trình làm việc

Checklist nộp bài

👥 Thành viên nhóm

Họ và tên	Mã số sinh viên	Vai trò	Đóng góp

Đinh Viết Chiến	B22DCVT076	Backend Developer	API Gateway, User Service

Phạm Đức Thiện	B22DCDT309	Backend Developer	Topic Service, Registration Service, Frontend

🔄 Quy trình kinh doanh


Sinh viên đăng ký đề tài đồ án và giảng viên xét duyệt

Tác nhân:

Sinh viên

Giảng viên

Quản trị viên

Quy trình:

Giảng viên tạo đề tài

Sinh viên xem danh sách đề tài

Sinh viên đăng ký đề tài

Hệ thống kiểm tra điều kiện

Giảng viên xét duyệt (duyệt/từ chối)

Hệ thống cập nhật kết quả đăng ký

🏗️ Kiến trúc hệ thống


(Sơ đồ chi tiết xem trong docs/architecture.md)

Thành phần	Trách nhiệm	Công nghệ	Cổng

Giao diện người dùng	Hiển thị và tương tác người dùng	React	3000

Gateway	Điều phối API	Node.js + Express	8080

User Service	Quản lý tài khoản, đăng nhập	Node.js + Express	5001

Topic Service	Quản lý đề tài	Node.js + Express	5002

Registration Service	Xử lý đăng ký và xét duyệt	Node.js + Express	5003

⚡ Hướng dẫn nhanh

Chạy hệ thống:

docker compose up --build

Xác minh:

curl http://localhost:8080/health

curl http://localhost:5001/health

curl http://localhost:5002/health

curl http://localhost:5003/health

📚 Tài liệu

Tài liệu	Mô tả

GETTING_STARTED.md	Hướng dẫn setup và workflow

docs/analysis-and-design.md	Phân tích & thiết kế hệ thống

docs/analysis-and-design-ddd.md	Thiết kế theo Domain-Driven Design

docs/architecture.md	Kiến trúc hệ thống

docs/api-specs/	OpenAPI cho các service

📄 Giấy phép


Dự án sử dụng giấy phép MIT.

 Ghi chú

Dự án được xây dựng phục vụ mục đích học tập môn Phát triển phần mềm hướng dịch vụ.

Mẫu thiết kế bởi Hung Dang
