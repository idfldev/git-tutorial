# Hướng Dẫn Sử Dụng Git Version Control

## Mục Lục
1. [Giới thiệu](#giới-thiệu)
2. [Cài đặt Git](#cài-đặt-git)
3. [Khởi Tạo Kho Chứa](#khởi-tạo-kho-chứa)
4. [Các Lệnh Cơ Bản](#các-lệnh-cơ-bản)
5. [Làm Việc Với Nhánh](#làm-việc-với-nhánh)
6. [Làm Việc Với Kho Chứa Từ Xa](#làm-việc-với-kho-chứa-từ-xa)
7. [Kỹ Thuật Nâng Cao](#kỹ-thuật-nâng-cao)
8. [Tài Nguyên Bổ Sung](#tài-nguyên-bổ-sung)

## Giới Thiệu
Git là một hệ thống quản lý phiên bản phân tán, 
giúp theo dõi các thay đổi trong mã nguồn và quản lý lịch sử phát triển của dự án. 
Git cho phép nhiều người làm việc cùng một lúc mà không làm gián đoạn công việc của nhau.

## Cài Đặt Git
### Windows
- Tải Git từ [git-scm.com](https://git-scm.com).
- Chạy trình cài đặt và làm theo hướng dẫn.

### macOS
- Sử dụng Homebrew:
    ```bash
    brew install git
    ```

### Linux
- Sử dụng package manager:
    ```bash
    sudo apt-get install git
    ```

### Cấu Hình Git
```bash
git config --global user.name "Tên Của Bạn"
git config --global user.email "email@example.com"
```

### Khởi Tạo Kho Chứa
Tạo Kho Chứa Mới
```bash
git init tên_thư_mục
```

### Sao Chép Kho Chứa Từ Xa
```bash
git clone https://github.com/username/repo.git
```

### Các Lệnh Cơ Bản
Kiểm Tra Trạng Thái
```bash
git status
```

### Thêm Thay Đổi Vào Stage
```bash
git add tên_tệp
```

### Thêm tất cả:
```bash
git add .
```

### Commit Thay Đổi
```bash
git commit -m "Mô tả thay đổi"
```

### Xem Lịch Sử Commit
```bash
git log
```

### Làm Việc Với Nhánh
Tạo Nhánh Mới
```bash
git branch tên_nhánh
```

### Chuyển Đổi Giữa Các Nhánh
```bash
git checkout tên_nhánh
```

### Gộp Nhánh
```bash
git merge tên_nhánh
```

### Làm Việc Với Kho Chứa Từ Xa
Thiết Lập Kho Chứa Từ Xa
```bash
git remote add origin https://github.com/username/repo.git
```

### Đẩy Thay Đổi Lên Kho Chứa Từ Xa
```bash
git push origin tên_nhánh
```

### Kéo Thay Đổi Từ Kho Chứa Từ Xa
```bash
git pull origin tên_nhánh
```

### Kỹ Thuật Nâng Cao
```bash
Sử Dụng .gitignore
Tạo file .gitignore để loại trừ các tệp không cần thiết.
```

### Xem Sự Khác Biệt
```bash
git diff
```

### Khôi Phục Thay Đổi
```bash
git checkout -- tên_tệp
```

### Xóa Nhánh
```bash
git branch -d tên_nhánh
```

### Rebase
```bash
git rebase tên_nhánh
```

### 1. Kiểm Tra Số Lượng Tệp Trong Thư Mục
```bash
find . -type f | wc -l

find . -type f: Tìm tất cả các tệp (files) trong thư mục hiện tại và các thư mục con.
wc -l: Đếm số lượng dòng, tức là số lượng tệp.
```

### 2. Kiểm Tra Số Lượng Tệp Đã Được Theo Dõi Bởi Git
```bash
git ls-files | wc -l

git ls-files: Liệt kê tất cả các tệp mà Git đang theo dõi.
wc -l: Đếm số lượng tệp trong danh sách.

```

### 3. Kiểm Tra Số Lượng Tệp Chưa Được Theo Dõi 
```bash
git status --porcelain | grep '^??' | wc -l

git status --porcelain: Hiển thị trạng thái của kho chứa theo dạng dễ đọc.
grep '^??': Lọc ra các tệp chưa được theo dõi.
wc -l: Đếm số lượng tệp chưa được theo dõi.
```

### Bước 1: Mở file README.md 
```bash
nano README.md
```

### Bước 2: Thêm Dòng Mới
```bash
Bước 3: Lưu File
Nếu bạn đang dùng nano, bạn có thể lưu và thoát bằng cách nhấn Ctrl + O, sau đó nhấn Enter, và cuối cùng nhấn Ctrl + X để thoát.
Nếu bạn dùng vim, nhấn Esc, gõ :wq, và nhấn Enter.
```
