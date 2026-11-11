# BÀI LÀM – HACKATHON 02

- **Mã đề:** 01
- **Họ tên:** Nguyễn Vũ Quốc Anh
- **Lớp:** CNTT2
- **Link repository:**
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
PS D:\starter-kit\san-bong-website> pwd
PS D:\starter-kit\san-bong-website> ls -force 
PS D:\starter-kit\san-bong-website> mv "ghi_chu_ban_giao.txt" .\docs\
PS D:\starter-kit\san-bong-website> cp .\data\dat_san_thang_10.xlsx .\backup
PS D:\starter-kit\san-bong-website> cd  .\logs\ 
PS D:\starter-kit\san-bong-website\logs> ls -Force
PS D:\starter-kit\san-bong-website\logs> cd ..
PS D:\starter-kit\san-bong-website> ls -Force -Recurse
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
 Directory: D:\starter-kit\san-bong-website


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
d-----        11/10/2026   1:49 PM                backup                                                                                                         
d-----        11/10/2026   1:37 PM                data                                                                                                           
d-----        11/10/2026   1:47 PM                docs                                                                                                           
d-----         11/8/2026   5:33 AM                evidence                                                                                                       
d-----        11/10/2026   1:37 PM                logs                                                                                                           
d-----        11/10/2026   1:37 PM                web                                                                                                            
-a----         11/8/2026   3:46 AM             76 .env                                                                                                           
-a----         11/8/2026   3:46 AM           2409 bai_lam.md                                                                                                     


    Directory: D:\starter-kit\san-bong-website\backup


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
-a----         11/8/2026   3:46 AM           6074 dat_san_thang_10.xlsx                                                                                          


    Directory: D:\starter-kit\san-bong-website\data


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
-a----         11/8/2026   3:46 AM           6074 dat_san_thang_10.xlsx                                                                                          


    Directory: D:\starter-kit\san-bong-website\docs


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
-a----         11/8/2026   3:46 AM            154 ghi_chu_ban_giao.txt                                                                                           


    Directory: D:\starter-kit\san-bong-website\logs


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
-a----         11/8/2026   3:46 AM            956 access.log                                                                                                     


    Directory: D:\starter-kit\san-bong-website\web


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
d-----        11/10/2026   1:37 PM                images                                                                                                         
-a----         11/8/2026   3:46 AM            590 app.js                                                                                                         
-a----         11/8/2026   3:46 AM            529 index.html                                                                                                     
-a----         11/8/2026   3:46 AM            460 style.css                                                                                                      


    Directory: D:\starter-kit\san-bong-website\web\images


Mode                 LastWriteTime         Length Name                                                                                                           
----                 -------------         ------ ----                                                                                                           
-a----         11/8/2026   3:46 AM           3101 logo-san-bong.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
PS D:\starter-kit\san-bong-website> Select-String "status=500" logs/access.log > logs/loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
logs\access.log:8:2026-10-28 08:24:34 POST /api/thanh-toan status=500
logs\access.log:9:2026-10-28 08:28:45 POST /api/thanh-toan status=500
```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
PS D:\starter-kit\san-bong-website> (Get-Content logs/access.log | Select-String "status=404").count  
```

```text
4
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
PS D:\starter-kit\san-bong-website> Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass 
PS D:\starter-kit\san-bong-website> ./tong_hop.ps1
PS D:\starter-kit\san-bong-website> Get-Content .\logs\tong_hop.txt
```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-10-28 08:07:39 GET /tin-tuc status=404
2026-10-28 08:13:01 GET /dat-san-cu status=404
2026-10-28 08:34:07 GET /images/san-7.jpg status=404
2026-10-28 08:57:24 GET /khuyen-mai status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 |  |  |  |
| 2 |  |  |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:** 
- **Expected:** 
- **Actual:** 
- **Log:** 

### Câu tìm kiếm Google

```text
(Ghi câu tìm kiếm vào đây – xoá dòng này)

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/dat_san_thang_10.xlsx`, không cần ghi vào đây.
