# HCM_KS26_CNTT2_IT108_BTTH

# 📚 IT108 | TỔNG HỢP BÀI TẬP NHẬP MÔN CÔNG NGHỆ THÔNG TIN

> Tài liệu tổng hợp kiến thức, bài tập thực hành và ví dụ ứng dụng trong học phần Nhập môn Công nghệ thông tin.

---

## 👨‍💻 THÔNG TIN BÀI THỰC HÀNH

| Thông tin | Nội dung |
|---|---|
| Học phần | IT108 - Nhập môn Công nghệ thông tin |
| Chuyên ngành | Công nghệ thông tin |
| Nội dung | Kiến thức máy tính, Terminal, PowerShell, Markdown |
| Môi trường | Windows, PowerShell, Git Bash |
| Định dạng | Markdown (.md) |

## 📑 MỤC LỤC

1. [Phần I - Kiến thức máy tính và hệ thống](#phần-i--kiến-thức-máy-tính-và-hệ-thống)
2. [Phần II - Thực hành Terminal và PowerShell](#phần-ii--thực-hành-terminal-và-powershell)
3. [Phần III - Quản lý Log và tự động hóa](#phần-iii--quản-lý-log-và-tự-động-hóa)
4. [Phần IV - Markdown và tài liệu kỹ thuật](#phần-iv--markdown-và-tài-liệu-kỹ-thuật)
5. [Tổng kết kiến thức](#tổng-kết-kiến-thức)

---

# PHẦN I – KIẾN THỨC MÁY TÍNH VÀ HỆ THỐNG

## 📝 Bài 1: Quản lý tệp và dung lượng lưu trữ

### 1. Phân tích

**Vị trí lưu trữ dữ liệu**

Không nên lưu bài tập trực tiếp trong thư mục `C:\Windows\System32` bởi đây là thư mục quan trọng của hệ điều hành.

- Dễ gặp lỗi thiếu quyền truy cập.
- Có nguy cơ ảnh hưởng đến các tệp hệ thống.
- Không phù hợp để quản lý tài liệu cá nhân.

**Quy tắc đặt tên**

Có thể sử dụng khoảng trắng trong tên tệp, nhưng nên đặt tên rõ ràng, dễ sử dụng trong Terminal.

Ví dụ:

- `bai-tap-01.py`
- `session-01`
- `IT108_Project`

**Tốc độ truyền dữ liệu**

Cần phân biệt:

| Đơn vị | Ý nghĩa |
|---|---|
| Mbps | Megabit mỗi giây |
| MB/s | Megabyte mỗi giây |
| 1 Byte | 8 bit |

Ví dụ, đường truyền 100 Mbps có tốc độ lý thuyết:

`100 / 8 = 12.5 MB/s`

**Dung lượng ổ cứng**

Ổ SSD được quảng cáo 256 GB nhưng Windows có thể hiển thị khoảng 238 GiB.

Nguyên nhân:

- Nhà sản xuất sử dụng hệ thập phân.
- Hệ nhị phân quy đổi 1 GiB = 1024³ byte.
- 256.000.000.000 / 1024³ ≈ 238.42 GiB.

### 2. Vận dụng

Tổ chức bài tập theo đường dẫn:

~~~text
D:\
└── IT108
    └── BaiTap
        ├── Session-01
        │   └── bai-tap-01.py
        └── Session-02
~~~

**Kết luận:** Lưu trữ khoa học giúp dễ tìm kiếm, sao lưu và tránh nhầm lẫn dữ liệu.

---

## 📝 Bài 2: Hiệu năng máy tính và đường dẫn tệp

### 1. So sánh đường dẫn

| Tiêu chí | Tuyệt đối | Tương đối |
|---|---|---|
| Điểm bắt đầu | Thư mục gốc | Vị trí hiện tại |
| Ví dụ | `D:\Project\img\a.png` | `..\img\a.png` |
| Khả năng chia sẻ | Phụ thuộc cấu trúc máy | Linh hoạt hơn |
| Ứng dụng | Xác định vị trí cố định | Dự án lập trình |

### 2. Phân tích mô hình IPO

Ví dụ: Mở ứng dụng Shopee.

**Input:**

- Người dùng nhấn vào biểu tượng ứng dụng.
- Hệ điều hành nhận yêu cầu khởi chạy.

**Process:**

- Hệ điều hành nạp dữ liệu cần thiết vào RAM.
- CPU thực thi các lệnh của chương trình.
- Ứng dụng kết nối mạng để tải thông tin sản phẩm.

**Output:**

- Giao diện Shopee xuất hiện.
- Người dùng có thể tìm kiếm và xem sản phẩm.

### 3. Ví dụ đường dẫn tương đối

Giả sử tệp hiện tại nằm trong `src`:

~~~text
project/
├── src/
│   └── main.py
└── assets/
    ├── logo.png
    ├── user.png
    └── product.jpg
~~~

Các đường dẫn có thể sử dụng:

~~~text
../assets/logo.png
../assets/user.png
../assets/product.jpg
~~~

### 4. Giảm tình trạng máy bị lag

- Đóng các chương trình không sử dụng.
- Kiểm tra mức sử dụng RAM và CPU trong Task Manager.
- Tắt ứng dụng khởi động cùng Windows nếu không cần.
- Khởi động lại máy khi cần giải phóng tài nguyên.

---

## 📝 Bài 3: Ứng dụng mô hình DIKW vào trang trại thông minh

DIKW gồm bốn cấp độ:

`Data → Information → Knowledge → Wisdom`

### 1. Data – Dữ liệu

Các cảm biến thu thập:

- Nhiệt độ không khí.
- Độ ẩm đất.
- Cường độ ánh sáng.
- Lượng mưa.

### 2. Information – Thông tin

Hệ thống xử lý dữ liệu và hiển thị:

- Nhiệt độ hiện tại: 35°C.
- Độ ẩm đất: 25%.
- Trạng thái: Đất đang khô.

### 3. Knowledge – Kiến thức

Từ các thông số, hệ thống xác định:

- Độ ẩm đất đang thấp.
- Cây có nguy cơ thiếu nước.
- Cần kiểm tra điều kiện tưới phù hợp.

### 4. Wisdom – Trí tuệ

Hệ thống đưa ra hành động:

- Kích hoạt máy bơm khi cần thiết.
- Ngừng tưới khi độ ẩm đạt mức phù hợp.
- Gửi cảnh báo đến điện thoại.

**Kết luận:** DIKW giúp chuyển dữ liệu cảm biến thành quyết định có ích trong thực tế.

---

## 📝 Bài 4: RAM, Storage và tối ưu tài nguyên

### 1. Vì sao máy tính bị chậm?

Khi mở nhiều ứng dụng cùng lúc, dung lượng RAM sử dụng tăng lên.

Nếu thiếu RAM, hệ điều hành có thể phải chuyển một phần dữ liệu ít sử dụng sang bộ nhớ ảo trên ổ đĩa.

Điều này làm một số thao tác chậm hơn do tốc độ truy xuất ổ đĩa thường thấp hơn RAM.

### 2. Phân biệt RAM và Storage

| Đặc điểm | RAM | Storage |
|---|---|---|
| Chức năng | Lưu dữ liệu đang xử lý | Lưu dữ liệu lâu dài |
| Tốc độ | Rất nhanh | Chậm hơn RAM |
| Khi tắt nguồn | Mất dữ liệu đang lưu | Dữ liệu vẫn được giữ |
| Ví dụ | DDR5 16GB | SSD 512GB |

### 3. Giải pháp

- Giảm số lượng chương trình chạy đồng thời.
- Nâng cấp RAM nếu thường xuyên thiếu.
- Dùng SSD để cải thiện tốc độ truy xuất dữ liệu.
- Kiểm tra các ứng dụng tiêu tốn tài nguyên.

### 4. Tổ chức thư mục

~~~text
D:\IT108\
└── BaiTapCaNhan\
    └── Session-03\
        └── main.py
~~~

---

## 📝 Bài 5: Tốc độ tải dữ liệu và đường dẫn an toàn

### 1. Phân biệt đường dẫn

**Absolute Path:** Đường dẫn đầy đủ từ thư mục gốc.

~~~text
D:\Project\data\db.csv
~~~

**Relative Path:** Đường dẫn tính từ thư mục làm việc.

~~~text
./data/db.csv
../data/db.csv
~~~

Ý nghĩa:

- `.` là thư mục hiện tại.
- `..` là thư mục cha.
- `/` hoặc `\` được dùng để phân tách thư mục tùy môi trường.

### 2. Bài toán tính thời gian tải

Giả sử:

- Dung lượng tệp: 2 GB.
- Tốc độ mạng: 80 Mbps.

Đổi đơn vị:

`80 / 8 = 10 MB/s`

Theo hệ thập phân:

`2 GB = 2000 MB`

Thời gian tải lý thuyết:

`2000 / 10 = 200 giây`

Tương đương khoảng **3 phút 20 giây**.

Lưu ý: Thời gian thực tế còn phụ thuộc đường truyền, máy chủ và các yếu tố khác.

---

## 📝 Bài 6: Thiết kế ứng dụng quản lý chi tiêu bằng DIKW và IPO

### 1. Mô hình DIKW

Ví dụ: Ứng dụng quản lý tài chính cá nhân.

| Thành phần | Vai trò |
|---|---|
| Data | Ghi nhận số tiền, thời gian và loại giao dịch |
| Information | Thống kê chi tiêu theo ngày, tháng |
| Knowledge | Phân tích nhóm chi tiêu nhiều nhất |
| Wisdom | Đề xuất cách điều chỉnh ngân sách |

### 2. Mô hình IPO

**Input:**

- Thông tin thu nhập.
- Giao dịch chuyển khoản.
- Hạn mức chi tiêu do người dùng cài đặt.

**Process:**

- Phân loại giao dịch.
- Tính tổng thu nhập và chi phí.
- So sánh thực tế với ngân sách dự kiến.

**Output:**

- Biểu đồ chi tiêu.
- Báo cáo tài chính.
- Thông báo khi vượt ngân sách.

**Kết luận:** IPO mô tả cách hệ thống vận hành, còn DIKW thể hiện cách dữ liệu được chuyển thành thông tin hữu ích.

---

# PHẦN II – THỰC HÀNH TERMINAL VÀ POWERSHELL

## 💻 Bài 1: Khởi tạo cấu trúc dự án Smart Farm

### 1. Vấn đề

Khi tên thư mục chứa khoảng trắng, người dùng cần đặt đường dẫn trong dấu ngoặc kép để Terminal hiểu đó là một đường dẫn duy nhất.

### 2. Thực hành

Tạo thư mục bằng PowerShell:

~~~powershell
mkdir "Smart Farm Project"
~~~

Tạo thư mục con:

~~~powershell
mkdir "Smart Farm Project\src\sensors\temperature"
~~~

Di chuyển đến dự án:

~~~powershell
cd "Smart Farm Project"
~~~

### 3. Kết quả

~~~text
Smart Farm Project/
└── src/
    └── sensors/
        └── temperature/
~~~

**Ghi nhớ:** Không phải khoảng trắng trong tên thư mục là lỗi. Lỗi thường xuất hiện khi nhập đường dẫn có khoảng trắng mà không xử lý đúng cú pháp.

---

## 💻 Bài 2: Xác định thư mục làm việc

### 1. Kiểm tra vị trí hiện tại

~~~powershell
Get-Location
~~~

Hoặc:

~~~powershell
pwd
~~~

### 2. Tạo thư mục và tệp

~~~powershell
mkdir drink_module
cd drink_module
~~~

Tạo hai tệp:

~~~powershell
New-Item -ItemType File -Path "coffee.txt", "tea.txt"
~~~

Kiểm tra:

~~~powershell
Get-ChildItem
~~~

### 3. Giải thích

| Lệnh | Công dụng |
|---|---|
| `mkdir` | Tạo thư mục |
| `cd` | Di chuyển thư mục |
| `pwd` | Hiển thị vị trí hiện tại |
| `New-Item` | Tạo tệp hoặc thư mục |
| `Get-ChildItem` | Liệt kê nội dung thư mục |

---

## 💻 Bài 3: Xây dựng cấu trúc dự án bằng PowerShell

### 1. Yêu cầu

Tạo môi trường cho một hệ thống quản lý trang trại, gồm mã nguồn, dữ liệu, log và thư mục sao lưu.

### 2. Câu lệnh thực hiện

~~~powershell
# Tao thu muc
New-Item -ItemType Directory -Force -Path `
".\smart-farm\code", `
".\smart-farm\data\logs", `
".\backup"

# Tao file cau hinh
New-Item -ItemType File -Force -Path `
".\smart-farm\code\sensors.py", `
".\smart-farm\code\config.json", `
".\smart-farm\code\.env"

# Sao luu thu muc code
Copy-Item -Path ".\smart-farm\code" `
-Destination ".\backup\code_v1" -Recurse
~~~

### 3. Kết quả

~~~text
project/
├── smart-farm/
│   ├── code/
│   │   ├── sensors.py
│   │   ├── config.json
│   │   └── .env
│   └── data/
│       └── logs/
└── backup/
    └── code_v1/
~~~

### 4. Mô hình IPO

- **Input:** Yêu cầu tạo thư mục và tệp cấu hình.
- **Process:** PowerShell thực thi lệnh tạo và sao chép.
- **Output:** Cấu trúc dự án được hình thành.

> Không nên đưa tệp `.env` chứa mật khẩu hoặc API key thật lên GitHub.

---

## 💻 Bài 4: Xử lý đường dẫn khi chuyển dự án

### 1. So sánh

| Tiêu chí | Absolute Path | Relative Path |
|---|---|---|
| Độ dài | Thường dài hơn | Thường ngắn hơn |
| Vị trí gốc | Cố định | Phụ thuộc thư mục hiện tại |
| Chia sẻ dự án | Có thể cần chỉnh sửa | Thường thuận tiện hơn |
| Ví dụ | `C:\App\data\a.csv` | `../data/a.csv` |

### 2. Lựa chọn giải pháp

Trong trường hợp chia sẻ dự án giữa nhiều máy, nên ưu tiên đường dẫn tương đối khi cấu trúc thư mục được giữ nguyên.

Ví dụ:

~~~text
../data/logs.csv
~~~

Dấu `..` giúp quay về thư mục cha trước khi truy cập đến thư mục `data`.

---

## 💻 Bài 5: Tự động phân loại tệp

### 1. Mục tiêu

Tự động sắp xếp tệp trong thư mục dự án.

Quy tắc:

- `.png`, `.jpg` → thư mục `media`.
- `.py` → thư mục `scripts`.
- `.tmp` → tệp tạm cần xem xét xóa.

### 2. Quy trình IPO

**Input:** Các tệp chưa được sắp xếp.

**Process:** Xác định phần mở rộng của từng tệp.

**Output:** Các tệp được chuyển đến đúng thư mục.

### 3. Script PowerShell

~~~powershell
# Tao thu muc
New-Item -ItemType Directory -Force -Path `
".\media", ".\scripts"

# Di chuyen anh
Get-ChildItem -File -Include *.png,*.jpg `
-Path ".\*" | Move-Item -Destination ".\media"

# Di chuyen file Python
Get-ChildItem -File -Filter *.py |
Move-Item -Destination ".\scripts"

# Kiem tra tep tam truoc khi xoa
Get-ChildItem -File -Filter *.tmp |
Remove-Item -WhatIf
~~~

**Lưu ý:** `-WhatIf` chỉ mô phỏng thao tác xóa, giúp kiểm tra trước khi thực hiện thật.

---

## 💻 Bài 6: Thiết lập môi trường cho hệ thống Smart Farm

### 1. Tạo cấu trúc

~~~powershell
New-Item -ItemType Directory -Force -Path `
".\smart-farm\bin", `
".\smart-farm\config", `
".\smart-farm\data", `
".\Public"
~~~

### 2. Tạo tệp

~~~powershell
New-Item -ItemType File -Force `
".\smart-farm\config\.env"

New-Item -ItemType File -Force `
".\Public\template.ps1"
~~~

### 3. Sao chép tệp

~~~powershell
Copy-Item ".\Public\template.ps1" `
".\smart-farm\bin\pump_control.ps1"
~~~

### 4. Kiểm tra toàn bộ cây thư mục

~~~powershell
Get-ChildItem ".\smart-farm" -Recurse -Force
~~~

### 5. Kiến thức rút ra

- `-Recurse`: Duyệt các thư mục con.
- `-Force`: Cho phép hiển thị các mục ẩn khi kết hợp với `Get-ChildItem`.
- `Copy-Item`: Sao chép dữ liệu.
- `.env`: Thường dùng để lưu biến môi trường hoặc cấu hình.

---

# PHẦN III – QUẢN LÝ LOG VÀ TỰ ĐỘNG HÓA

## ⚙️ Bài 1: Đọc tệp Log dung lượng lớn

### 1. Phân tích

Không nên mở trực tiếp một tệp log hàng trăm MB bằng trình soạn thảo văn bản đơn giản vì có thể gây tiêu tốn nhiều bộ nhớ.

Có thể dùng Terminal để xem những dòng cần thiết.

### 2. Câu lệnh

Đọc toàn bộ nội dung:

~~~powershell
Get-Content .\server.log
~~~

Chỉ đọc 10 dòng cuối:

~~~powershell
Get-Content .\server.log -Tail 10
~~~

Theo dõi những dòng mới:

~~~powershell
Get-Content .\server.log -Tail 10 -Wait
~~~

**Kết luận:** Đọc phần cuối của tệp thường phù hợp hơn khi cần kiểm tra lỗi mới phát sinh.

---

## ⚙️ Bài 2: Tìm kiếm lỗi từ Access Log

### 1. Phân biệt hai lệnh

| Lệnh | Chức năng |
|---|---|
| `Get-ChildItem` | Tìm và liệt kê tệp |
| `Select-String` | Tìm nội dung văn bản bên trong tệp |

### 2. Thực hành

Tìm các dòng chứa `ERROR`:

~~~powershell
Select-String -Path ".\access.log" -Pattern "ERROR"
~~~

Tìm lỗi HTTP 404:

~~~powershell
Select-String -Path ".\access.log" -Pattern "404"
~~~

Tìm trong nhiều tệp log:

~~~powershell
Get-ChildItem -Filter *.log -File |
Select-String -Pattern "ERROR"
~~~

### 3. Kết luận

`Get-ChildItem -Filter` lọc theo tên tệp, không phải nội dung bên trong tệp.

Muốn tìm chuỗi ký tự trong log cần sử dụng `Select-String`.

---

## ⚙️ Bài 3: Thống kê lỗi TIMEOUT

### 1. Mục tiêu

Đếm những dòng có `TIMEOUT`, nhưng loại bỏ dòng chứa `NOT TIMEOUT`.

### 2. PowerShell

~~~powershell
(
    Get-Content .\server.log |
    Select-String "TIMEOUT" |
    Where-Object { $_ -notmatch "NOT TIMEOUT" }
).Count
~~~

### 3. Giải thích

Quy trình xử lý:

1. `Get-Content`: Đọc nội dung.
2. `Select-String`: Lọc dòng chứa TIMEOUT.
3. `Where-Object`: Loại bỏ trường hợp không phù hợp.
4. `.Count`: Đếm kết quả còn lại.

### 4. Ví dụ

Giả sử tệp có:

~~~text
ERROR TIMEOUT
REQUEST OK
NOT TIMEOUT
SERVER TIMEOUT
~~~

Kết quả:

~~~text
2
~~~

---

## ⚙️ Bài 4: Ghi báo cáo Log an toàn

### 1. So sánh

| Tiêu chí | Ghi đè | Ghi nối tiếp |
|---|---|---|
| Cú pháp | `>` | `>>` |
| Nội dung cũ | Bị thay thế | Được giữ lại |
| Công dụng | Tạo báo cáo mới | Tích lũy nhật ký |
| Rủi ro | Có thể mất dữ liệu cũ | Có thể bị trùng dữ liệu |

### 2. Ví dụ ghi đè

~~~powershell
"Bao cao he thong" |
Out-File .\report.txt -Encoding utf8
~~~

### 3. Ví dụ ghi nối tiếp

~~~powershell
Get-Content .\server.log |
Select-String "ERROR" |
Out-File .\report.txt -Append -Encoding utf8
~~~

### 4. Nhận xét

Khi cần duy trì lịch sử lỗi, nên dùng cách ghi nối tiếp.

Khi muốn tạo báo cáo mới hoàn toàn, có thể sử dụng ghi đè sau khi xác nhận không cần nội dung cũ.

---

## ⚙️ Bài 5: Xây dựng Script lọc Log tự động

### 1. Cấu trúc Script

Một script PowerShell có thể chia thành bốn phần:

1. Thông tin chương trình.
2. Khai báo biến.
3. Xử lý dữ liệu.
4. Thông báo kết quả.

### 2. Chương trình mẫu

Tên tệp: `auto_report.ps1`

~~~powershell
# ===================================
# AUTO LOG REPORT
# Chuc nang: Loc loi 404 tu server
# ===================================

# 1. Khai bao bien
$logFile = ".\server.log"
$reportFile = ".\report.txt"

# 2. Kiem tra file
if (-not (Test-Path $logFile)) {
    Write-Host "Khong tim thay file log!"
    return
}

# 3. Khoi tao bao cao
"=== BAO CAO LOI 404 ===" |
Out-File $reportFile -Encoding utf8

# 4. Loc du lieu
Get-Content $logFile |
Select-String "404" |
Out-File $reportFile -Append -Encoding utf8

# 5. Thong bao
Write-Host "Da tao bao cao thanh cong!"
~~~

### 3. Kết quả dự kiến

~~~text
=== BAO CAO LOI 404 ===
404 Not Found /login
404 Not Found /images
~~~

**Nhận xét:** Script giúp giảm thao tác thủ công và có thể tái sử dụng trong quá trình quản trị hệ thống.

---

## ⚙️ Bài 6: Kiểm tra an toàn trước khi chạy Script

### 1. Phân tích rủi ro

Lệnh xóa dữ liệu cần được kiểm tra kỹ, đặc biệt khi có:

- `-Recurse`: Tác động đến các thư mục con.
- `-Force`: Cho phép xử lý một số mục bị ẩn hoặc có thuộc tính đặc biệt.
- Đường dẫn chỉ đến vị trí chứa dữ liệu quan trọng.

### 2. Nguyên tắc an toàn

- Không chạy lệnh chưa hiểu rõ.
- Tránh thực hiện thao tác xóa trên thư mục gốc.
- Sử dụng `-WhatIf` trước khi xóa.
- Sao lưu các tệp quan trọng.

### 3. Script kiểm tra Log

~~~powershell
# Tim loi canh bao
Select-String "WARNING" .\logs\system.log |
Out-File .\logs\issues.txt -Encoding utf8

# Xem ket qua
Get-Content .\logs\issues.txt

# Kiem tra tep tam
Get-ChildItem .\logs -Filter *.tmp -File

# Mo phong xoa tep tam
Get-ChildItem .\logs -Filter *.tmp -File |
Remove-Item -WhatIf
~~~

### 4. Kiểm thử

~~~powershell
Test-Path .\logs\issues.txt
~~~

Nếu tệp tồn tại, kết quả trả về:

~~~text
True
~~~

---

# PHẦN IV – MARKDOWN VÀ TÀI LIỆU KỸ THUẬT

## 📘 Bài 1: Chuẩn hóa tài liệu Markdown

### 1. Các lỗi thường gặp

**Lỗi tiêu đề:**

Sử dụng cấp tiêu đề không hợp lý khiến cấu trúc tài liệu khó theo dõi.

Cách dùng:

~~~text
# Tiêu đề chính
## Nội dung lớn
### Nội dung nhỏ
~~~

**Lỗi chèn ảnh:**

Cú pháp liên kết:

~~~text
[Logo](./images/logo.png)
~~~

Cú pháp hiển thị ảnh:

~~~text
![Logo](./images/logo.png)
~~~

**Lỗi định dạng văn bản:**

~~~text
*In nghiêng*
**In đậm**
~~~

### 2. Ví dụ tài liệu đúng

~~~markdown
# 🌱 LỢI ÍCH CỦA RAU SẠCH

## 1. Giới thiệu

Rau sạch đóng vai trò **quan trọng**
trong chế độ dinh dưỡng.

## 2. Các loại rau

- Rau cải
- Rau muống
- Rau xà lách

## 3. Lưu ý

**Rất quan trọng:** Rửa sạch rau
trước khi sử dụng.
~~~

---

## 📘 Bài 2: Viết tài liệu hướng dẫn lắp đặt cảm biến

# 🌡️ HƯỚNG DẪN SỬ DỤNG CẢM BIẾN DHT22

### 1. Giới thiệu

DHT22 là cảm biến được sử dụng để đo nhiệt độ và độ ẩm không khí.

Trong dự án Smart Farm, cảm biến giúp theo dõi điều kiện môi trường để hỗ trợ chăm sóc cây trồng.

### 2. Chuẩn bị thiết bị

- [ ] Raspberry Pi.
- [ ] Cảm biến DHT22.
- [ ] Dây nối.
- [ ] Điện trở kéo lên phù hợp nếu dùng cảm biến DHT22 dạng rời.
- [ ] Nguồn điện và thẻ nhớ.

### 3. So sánh DHT11 và DHT22

| Tiêu chí | DHT11 | DHT22 |
|---|---|---|
| Nhiệt độ | 0–50°C | -40–80°C |
| Độ ẩm | 20–80% RH | 0–100% RH |
| Độ chính xác | Thấp hơn | Cao hơn |
| Chi phí | Thấp | Cao hơn |

### 4. Kết nối thiết bị

Ví dụ khi sử dụng chân GPIO4:

| DHT22 | Raspberry Pi |
|---|---|
| VCC | 3.3V |
| DATA | GPIO4 |
| GND | GND |

Cần xác định đúng sơ đồ chân của loại cảm biến đang sử dụng.

### 5. Cài đặt môi trường Python

~~~bash
sudo apt update
sudo apt install python3-venv libgpiod2

python3 -m venv .venv
source .venv/bin/activate

pip install adafruit-circuitpython-dht
~~~

### 6. Chương trình minh họa

~~~python
import board
import adafruit_dht

sensor = adafruit_dht.DHT22(
    board.D4,
    use_pulseio=False
)

try:
    print("Temperature:", sensor.temperature)
    print("Humidity:", sensor.humidity)
finally:
    sensor.exit()
~~~

### 7. Kết quả mong đợi

Ví dụ dữ liệu cảm biến:

~~~text
Temperature: 28.4
Humidity: 67.1
~~~

> Giá trị trên chỉ minh họa. Kết quả thực tế phụ thuộc môi trường và thiết bị.

---

## 📘 Bài 3: So sánh Markdown và HTML trong hệ thống AI

### 1. Khái niệm Token

Token là đơn vị văn bản mà mô hình AI sử dụng trong quá trình xử lý ngôn ngữ.

Số token phụ thuộc vào nội dung và bộ mã hóa của từng mô hình.

### 2. So sánh định dạng

| Tiêu chí | Markdown | HTML |
|---|---|---|
| Cú pháp | Ngắn gọn | Nhiều thẻ hơn |
| Dễ đọc | Cao | Phụ thuộc cấu trúc |
| Trình bày web | Cần công cụ render | Trình duyệt hỗ trợ trực tiếp |
| Khả năng tùy biến | Cơ bản | Rất linh hoạt |
| Sử dụng trong Prompt | Phù hợp | Dùng khi cần cấu trúc HTML |

### 3. Ví dụ

**HTML:**

~~~html
<h1>Trang trại thông minh</h1>
<p>Hệ thống giám sát nhiệt độ.</p>
<ul>
  <li>Nhiệt độ</li>
  <li>Độ ẩm</li>
</ul>
~~~

**Markdown:**

~~~markdown
# Trang trại thông minh

Hệ thống giám sát nhiệt độ.

- Nhiệt độ
- Độ ẩm
~~~

### 4. Đánh giá

Markdown thường giúp nội dung ngắn gọn, dễ chỉnh sửa và dễ đưa vào prompt.

Tuy nhiên, mức tiết kiệm token không cố định mà phụ thuộc nội dung và mô hình AI sử dụng.

### 5. Ứng dụng

Đối với dự án GreenTech, Markdown có thể dùng để:

- Viết tài liệu kỹ thuật.
- Xây dựng prompt cho chatbot.
- Lưu hướng dẫn vận hành.
- Quản lý phiên bản bằng Git.

---

## 📘 Bài 4: Thiết kế Prompt cho AI Assistant

### 1. Mục tiêu

Xây dựng prompt để AI giải thích mô hình IPO trong trang trại thông minh theo cách dễ hiểu.

### 2. Prompt mẫu

~~~markdown
# Bối cảnh

Tôi là sinh viên năm nhất ngành CNTT,
đang tìm hiểu mô hình IPO.

# Nội dung

Giải thích cách ứng dụng mô hình IPO
vào hệ thống tưới cây tự động.

# Yêu cầu

- Sử dụng từ ngữ đơn giản.
- Trình bày ngắn gọn.
- Có ví dụ minh họa.
- Giải thích rõ Input, Process, Output.
- Đưa ra 2 câu hỏi để tự kiểm tra.
~~~

### 3. Câu trả lời minh họa

**Input – Đầu vào**

Cảm biến đọc độ ẩm đất, ví dụ 25%.

**Process – Xử lý**

Bộ điều khiển so sánh độ ẩm với ngưỡng đã đặt.

~~~python
humidity = 25

if humidity < 40:
    print("Bat may bom")
else:
    print("Tat may bom")
~~~

**Output – Đầu ra**

Máy bơm hoạt động khi đất khô và ngừng khi không cần tưới.

### 4. Đánh giá Prompt

- [x] Có bối cảnh rõ ràng.
- [x] Có mục tiêu cụ thể.
- [x] Xác định hình thức trình bày.
- [x] Có ví dụ thực tế.
- [x] Dễ kiểm tra kết quả.

**Kết luận:** Prompt càng rõ ràng thì AI càng có cơ sở để đưa ra câu trả lời phù hợp với nhu cầu.

---

## 📘 Bài 5: Xây dựng tài liệu kỹ thuật cho Smart Farm

# 🚀 SMART FARM – HỆ THỐNG QUẢN LÝ TRANG TRẠI THÔNG MINH

### 1. Giới thiệu

Smart Farm là mô hình ứng dụng IoT hỗ trợ giám sát các chỉ số môi trường trong trang trại.

**Mục tiêu chính:**

- Theo dõi điều kiện môi trường.
- Hỗ trợ tưới cây tự động.
- Phát hiện các chỉ số bất thường.
- Giảm công việc theo dõi thủ công.

### 2. Mô hình hoạt động

~~~text
CAM BIEN
    |
    v
BO DIEU KHIEN
    |
    v
XU LY DU LIEU
    |
    +----> UNG DUNG GIAM SAT
    |
    +----> MAY BOM / QUAT / DEN
~~~

### 3. Chức năng

- [x] Thu thập dữ liệu cảm biến.
- [x] Xử lý và phân tích thông số.
- [x] Mô phỏng điều khiển máy bơm.
- [ ] Hoàn thiện phần cứng thực tế.
- [ ] Tích hợp ứng dụng di động.
- [ ] Kiểm thử tự động hóa.

### 4. Bảng thông số tham khảo

| Thông số | Thiết bị | Ngưỡng minh họa |
|---|---|---|
| Nhiệt độ | DHT22 | Cảnh báo trên 30°C |
| Độ ẩm đất | Cảm biến độ ẩm đất | Tưới khi dưới 40% |
| Ánh sáng | BH1750 | Theo cấu hình cây trồng |
| Độ ẩm không khí | DHT22 | Theo yêu cầu môi trường |

Các ngưỡng trên là ví dụ phục vụ học tập, cần hiệu chỉnh trước khi sử dụng thực tế.

### 5. Chu trình Fetch – Decode – Execute

**Fetch:**

CPU lấy lệnh từ bộ nhớ.

**Decode:**

CPU giải mã lệnh để xác định thao tác.

**Execute:**

CPU thực thi lệnh tương ứng.

Trong hệ thống tưới cây, chu trình xử lý lệnh của CPU góp phần thực hiện việc đọc cảm biến và điều khiển thiết bị.

### 6. Mô hình DIKW

**Data:**

Nhiệt độ đo được: 35°C.

**Information:**

Nhiệt độ đang cao hơn mức cảnh báo 30°C.

**Knowledge:**

Nhiệt độ cao có thể ảnh hưởng đến cây trồng.

**Wisdom:**

Hệ thống gửi cảnh báo và đề xuất các biện pháp điều chỉnh môi trường phù hợp.

### 7. Kiểm thử hệ thống

**Tình huống:** Bộ nhớ thiết bị điều khiển gần hết.

**Giải pháp dự kiến:**

- Ghi nhận cảnh báo.
- Hạn chế tác vụ không thiết yếu.
- Lưu trạng thái quan trọng nếu được hỗ trợ.
- Áp dụng phương án điều khiển an toàn đã thiết kế.
- Khôi phục hoạt động sau khi khắc phục lỗi.

**Kết luận:** Hệ thống IoT cần được xây dựng với cơ chế kiểm soát và xử lý sự cố để tăng độ tin cậy.

---

## 📘 Bài 6: So sánh tài liệu Word và Markdown trên GitHub

### 1. Vấn đề

Khi làm việc nhóm bằng GitHub, việc lưu tài liệu dưới dạng Word có thể gây khó khăn trong quá trình theo dõi thay đổi.

### 2. So sánh

| Tiêu chí | Word (.docx) | Markdown (.md) |
|---|---|---|
| Định dạng | Tài liệu đóng gói | Văn bản thuần |
| Xem trên GitHub | Hạn chế | Hiển thị trực tiếp |
| Git Diff | Khó so sánh nội dung | So sánh theo dòng |
| Dung lượng | Thường lớn hơn | Thường nhỏ hơn |
| Chỉnh sửa | Phần mềm soạn thảo | Nhiều trình soạn thảo |
| Khả năng trình bày | Rất phong phú | Gọn nhẹ, cơ bản |

### 3. Vì sao nên sử dụng Markdown?

**Dễ đọc:**

GitHub có thể hiển thị Markdown trực tiếp trên trình duyệt.

**Dễ quản lý:**

Git có thể xác định những dòng đã được chỉnh sửa.

**Dễ phối hợp:**

Các thành viên có thể cùng đóng góp qua commit và pull request.

**Dễ khôi phục:**

Markdown là văn bản thuần, nên một số lỗi dữ liệu có thể ảnh hưởng cục bộ thay vì làm hỏng toàn bộ cấu trúc tài liệu. Tuy nhiên, không có định dạng nào hoàn toàn miễn nhiễm lỗi tệp.

### 4. Công cụ hỗ trợ

Có thể sử dụng:

- Visual Studio Code.
- GitHub Web Editor.
- StackEdit.
- Typora.

### 5. Kết luận

Đối với tài liệu hướng dẫn lập trình, README hoặc tài liệu kỹ thuật lưu trên GitHub, Markdown là một lựa chọn phù hợp nhờ cú pháp đơn giản và khả năng quản lý phiên bản thuận tiện.

---

# 🎯 TỔNG KẾT KIẾN THỨC

Qua các nội dung thực hành, có thể rút ra những kiến thức quan trọng sau:

| Nhóm kiến thức | Nội dung |
|---|---|
| Hệ thống máy tính | CPU, RAM, SSD, hiệu năng |
| Quản lý dữ liệu | Tệp, thư mục, đường dẫn |
| Mô hình hệ thống | IPO và DIKW |
| Terminal | Điều hướng và thao tác tệp |
| PowerShell | Quản lý hệ thống bằng câu lệnh |
| Log | Tìm kiếm, thống kê, lập báo cáo |
| Script | Tự động hóa công việc |
| Markdown | Xây dựng tài liệu chuyên nghiệp |
| GitHub | Lưu trữ và quản lý tài liệu |

## ✅ Những kỹ năng đạt được

- [x] Hiểu cách tổ chức và quản lý dữ liệu.
- [x] Phân biệt RAM và bộ nhớ lưu trữ.
- [x] Hiểu và áp dụng mô hình IPO, DIKW.
- [x] Biết sử dụng các lệnh PowerShell cơ bản.
- [x] Biết cách tìm kiếm và xử lý tệp Log.
- [x] Có thể viết Script tự động hóa đơn giản.
- [x] Biết xây dựng README bằng Markdown.
- [x] Hiểu cách lưu trữ tài liệu trên GitHub.

---

## 📌 KẾT LUẬN

Các bài thực hành giúp củng cố kiến thức nền tảng của ngành Công nghệ thông tin, đồng thời tạo cơ hội tiếp xúc với những công cụ thường được sử dụng trong quá trình học lập trình.

Việc kết hợp lý thuyết với các ví dụ thực tế giúp hiểu rõ hơn về cách hệ thống máy tính hoạt động, cách dữ liệu được xử lý và cách tự động hóa những công việc lặp lại.

Đây là nền tảng để tiếp tục học lập trình, quản trị hệ thống, phát triển phần mềm và các lĩnh vực công nghệ khác.

---

## 📚 TÀI LIỆU THAM KHẢO

- Nội dung học phần IT108 – Nhập môn Công nghệ thông tin.
- [Tài liệu tổng hợp IT108 tham khảo](https://github.com/HCM-K26-CNTT2/T-ng_H-p).
- [Microsoft Learn – PowerShell](https://learn.microsoft.com/powershell/).
- [GitHub Docs – Basic Writing and Formatting Syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

---

**📖 IT108 – NHẬP MÔN CÔNG NGHỆ THÔNG TIN**
