# System Architecture

## 1. Pattern Selection

| Pattern | Selected? | Justification |
|---------|-----------|--------------|
| API Gateway | YES | Centralized request handling |
| Database per Service | YES | Each service manages its own data |
| Shared Database | NO | Avoid tight coupling |
| Saga | NO | No complex transaction |
| Event-driven | NO | System is simple |
| CQRS | NO | Not required |
| Circuit Breaker | NO | Not required |
| Service Registry | NO | Using Docker DNS |

---

## 2. System Components

| Component | Responsibility | Tech Stack | Port |
|------------|-------------|-----------|------|
| Frontend | Giao diện người dùng | React | 3000 |
| Gateway | Điều phối API | Node.js + Express | 8080 |
| User Service | Quản lý tài khoản | Node.js + Express | 5001 |
| Topic Service | Quản lý đề tài | Node.js + Express | 5002 |
| Registration Service | Xử lý đăng ký | Node.js + Express | 5003 |

---

## 3. Communication

| From → To     | User Service | Topic Service | Registration Service | Gateway |
|---------------|--------------|---------------|----------------------|---------|
| Frontend      | —            | —             | —                    | REST    |
| Gateway       | REST         | REST          | REST                 | —       |
| User Service  | —            | —             | —                    | —       |
| Topic Service | —            | —             | —                    | —       |
| Registration  | —            | —             | —                    | —       |

---

## 4. Architecture Diagram

```mermaid
flowchart LR
    A[User] --> B[Frontend :3000]
    B --> C[API Gateway :8080]
    C --> D[User Service :5001]
    C --> E[Topic Service :5002]
    C --> F[Registration Service :5003]
    D --> G[(User Database)]
    E --> H[(Topic Database)]
    F --> I[(Registration Database)]
