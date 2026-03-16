# Project Development Report: Fullstack Patient Management System

## 1. Tổng quan dự án (Project Overview)
Hệ thống bao gồm 3 thành phần chính được thiết kế để hoạt động đồng bộ:
* **Backend:** Xây dựng bằng .NET Core Web API, sử dụng SQL Server với Stored Procedures để quản lý dữ liệu.
* **Web Client:** Ứng dụng Angular để quản lý và hiển thị dữ liệu trên trình duyệt.
* **Mobile App:** Ứng dụng React Native cho phép thao tác dữ liệu linh hoạt trên thiết bị di động.

---

## 2. Kiến thức kỹ thuật đã đạt được (Technical Proficiency)

### Backend & Database (.NET Core & SQL Server)
* **Stored Procedures (SP):** Thay vì viết logic truy vấn trực tiếp trong code C#, tôi đã chuyển toàn bộ các thao tác CRUD vào SP. Điều này giúp:
    * Tăng hiệu suất thực thi câu lệnh SQL.
    * Tách biệt logic dữ liệu (Database) và logic ứng dụng (Code).
    * Tăng tính bảo mật, hạn chế SQL Injection.
* **RESTful API:** Thiết kế các đầu cuối (endpoints) rõ ràng để cả Web và Mobile đều có thể gọi chung một nguồn dữ liệu.
* **CORS (Cross-Origin Resource Sharing):** Hiểu và cấu hình chính xác quyền truy cập để Frontend có thể giao tiếp với Backend.

### Frontend Web (Angular)
* **Component Architecture:** Chia nhỏ giao diện thành các thành phần tái sử dụng được.
* **Angular Services & HttpClient:** Sử dụng Service để quản lý logic gọi API, giúp code trong Component sạch sẽ.
* **Dependency Injection:** Áp dụng để quản lý các instance của Service xuyên suốt ứng dụng.

### Mobile Development (React Native)
* **Cross-platform Development:** Cách xây dựng giao diện bằng các thẻ `View`, `Text`, `FlatList` thay vì HTML/CSS.
* **Networking:** Sử dụng `fetch` hoặc `axios` để thực hiện các yêu cầu mạng trên môi trường di động.
* **Environment Setup:** Cấu hình để Mobile kết nối với Backend Local qua IP nội bộ.

---

## 3. Luồng dữ liệu và Vòng đời (Workflow & Lifecycle)

### Luồng đi của dữ liệu (Data Flow)
1. **Request:** Client gửi yêu cầu kèm theo tham số.
2. **Processing:** Backend nhận yêu cầu, gọi Stored Procedure tương ứng.
3. **Response:** Dữ liệu trả về dưới dạng JSON.
4. **Binding:** Frontend nhận JSON, lưu vào State/Variable và hiển thị lên giao diện.

### Lifecycle Hooks Quan trọng
| Nền tảng | Hook Sử dụng | Mục đích |
| :--- | :--- | :--- |
| **Angular** | `ngOnInit()` | Tự động gọi API lấy dữ liệu ngay khi Component khởi tạo. |
| **React Native** | `useEffect(() => {}, [])` | Thực hiện gọi API một lần duy nhất khi màn hình render lần đầu. |

---

## 4. Các Pattern & Tư duy lập trình (Design Patterns)
* **Separation of Concerns (SoC):** Tách biệt hoàn toàn giữa UI (Frontend) và Logic/Data (Backend).
* **DTO (Data Transfer Object):** Sử dụng các Model trung gian để định dạng dữ liệu trả về từ Database.
* **Asynchronous Programming:** Xử lý gọi API không gây treo giao diện bằng `Observable` (Angular) và `Async/Await` (React Native).

---

## 5. Kinh nghiệm thực tế (Key Takeaways)
* Sử dụng **Postman** để kiểm tra API độc lập.
* Kỹ năng debug lỗi kết nối giữa thiết bị di động và server nội bộ.
* Tổ chức thư mục theo tính năng (Feature-based structure).

---
*Người thực hiện: [Tên của bạn]*
*Ngày hoàn thành: 16/03/2026*
