# Mô tả kết quả đạt được

## 1. Tổng quan
Dự án này triển khai một **Minimal API** với .NET, sử dụng **In-Memory Database** để quản lý các công việc (To-Do Items). API cung cấp đầy đủ các chức năng CRUD (Create, Read, Update, Delete) với cấu trúc đơn giản và hiệu quả.

---

## 2. Kết quả đạt được

### Chức năng chính của API
- **Tạo mới công việc** (POST):  
  Cho phép thêm một công việc vào danh sách với các thông tin như tên (`Name`) và trạng thái hoàn thành (`IsComplete`).

- **Lấy danh sách tất cả công việc** (GET):  
  Truy xuất danh sách tất cả các công việc hiện có trong cơ sở dữ liệu.

- **Lấy danh sách công việc đã hoàn thành** (GET):  
  Truy xuất danh sách các công việc có trạng thái `IsComplete = true`.

- **Lấy thông tin chi tiết của một công việc** (GET):  
  Truy xuất một công việc cụ thể theo `Id`.

- **Cập nhật thông tin công việc** (PUT):  
  Cho phép chỉnh sửa tên (`Name`) hoặc trạng thái hoàn thành (`IsComplete`) của một công việc.

- **Xóa một công việc** (DELETE):  
  Xóa một công việc khỏi danh sách dựa trên `Id`.

---

## 3. Endpoint API

| HTTP Method | Endpoint                      | Mô tả                                      |
|-------------|-------------------------------|--------------------------------------------|
| GET         | `/todoitems`                  | Lấy danh sách tất cả công việc.            |
| GET         | `/todoitems/complete`         | Lấy danh sách công việc đã hoàn thành.     |
| GET         | `/todoitems/{id}`             | Lấy thông tin chi tiết của một công việc.  |
| POST        | `/todoitems`                  | Thêm một công việc mới.                    |
| PUT         | `/todoitems/{id}`             | Cập nhật thông tin một công việc.          |
| DELETE      | `/todoitems/{id}`             | Xóa một công việc khỏi danh sách.          |

---

## 4. Các bước thử nghiệm API
Dưới đây là các bước thử nghiệm API bằng công cụ như Postman hoặc HTTP Client (`MinimalAPI.http` file):

1. **Thêm một công việc mới** (POST)
   - URL: `http://localhost:5000/todoitems`
   - Body:
     ```json
     {
       "name": "walk dog 3",
       "isComplete": false
     }
     ```

2. **Lấy danh sách tất cả công việc** (GET)
   - URL: `http://localhost:5000/todoitems`

3. **Lấy danh sách công việc hoàn thành** (GET)
   - URL: `http://localhost:5000/todoitems/complete`

4. **Xóa một công việc** (DELETE)
   - URL: `http://localhost:5000/todoitems/1`

5. **Lấy thông tin chi tiết một công việc** (GET)
   - URL: `http://localhost:5000/todoitems/2`

6. **Cập nhật thông tin công việc** (PUT)
   - URL: `http://localhost:5000/todoitems/2`
   - Body:
     ```json
     {
       "name": "walk dog Test Put Method",
       "isComplete": true
     }
     ```

---

## 5. Công nghệ sử dụng
- **Back-End**: ASP.NET Core Minimal API, Entity Framework Core
- **Cơ sở dữ liệu**: In-Memory Database
- **Quản lý yêu cầu HTTP**: HTTP Client (`MinimalAPI.http` file)

---
