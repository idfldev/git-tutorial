# Khóa Học: Làm Chủ Git Command Từ Cơ Bản Đến Nâng Cao

## Mục tiêu khóa học
- Hiểu và sử dụng thành thạo các lệnh Git từ cơ bản đến nâng cao.
- Áp dụng Git trong các dự án thực tế, từ quản lý mã nguồn cá nhân đến làm việc nhóm.
- Xử lý các tình huống phức tạp như xung đột merge, quay lại lịch sử commit, và quản lý branch.

## Đối tượng
- Người mới bắt đầu học lập trình hoặc chưa từng sử dụng Git.
- Lập trình viên muốn nâng cao kỹ năng quản lý mã nguồn.

## Yêu cầu
- Cài đặt Git trên máy tính ([Hướng dẫn cài đặt Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)).
- Một trình soạn thảo văn bản (VD: VS Code).
- Kiến thức cơ bản về dòng lệnh (command line).

---

## Mô-đun 1: Giới Thiệu và Cài Đặt Git

### Bước 1: Hiểu về Git và Version Control
- **Git là gì?**: Git là một hệ thống quản lý phiên bản phân tán (distributed version control system) giúp theo dõi các thay đổi trong mã nguồn.
- **Tại sao dùng Git?**:
  - Lưu trữ lịch sử thay đổi.
  - Hỗ trợ làm việc nhóm.
  - Phục hồi mã nguồn khi cần.

### Bước 2: Cài đặt Git
- Tải và cài đặt Git từ [git-scm.com](https://git-scm.com).
- Kiểm tra cài đặt:
  ```bash
  git --version
  ```
  Kết quả: `git version x.x.x`

### Bước 3: Cấu hình Git
- Thiết lập thông tin người dùng:
  ```bash
  git config --global user.name "Tên của bạn"
  git config --global user.email "email@example.com"
  ```
- Kiểm tra cấu hình:
  ```bash
  git config --list
  ```

**Bài tập**:
- Cài đặt Git trên máy tính.
- Cấu hình tên và email, sau đó kiểm tra bằng `git config --list`.

---

## Mô-đun 2: Các Lệnh Git Cơ Bản

### Bước 1: Khởi tạo Repository
- Tạo một repository mới:
  ```bash
  mkdir my-project
  cd my-project
  git init
  ```
  Kết quả: Tạo một thư mục `.git` để theo dõi repository.

### Bước 2: Theo dõi và Commit
- Tạo file mới (VD: `index.html`):
  ```bash
  echo "<h1>Hello Git</h1>" > index.html
  ```
- Thêm file vào staging:
  ```bash
  git add index.html
  ```
- Commit thay đổi:
  ```bash
  git commit -m "Thêm file index.html"
  ```

### Bước 3: Kiểm tra trạng thái và lịch sử
- Xem trạng thái repository:
  ```bash
  git status
  ```
- Xem lịch sử commit:
  ```bash
  git log
  ```

**Bài tập**:
- Khởi tạo một repository mới.
- Tạo và commit một file `README.md`.
- Kiểm tra trạng thái và lịch sử commit.

---

## Mô-đun 3: Làm Việc Với Branch

### Bước 1: Tạo và Chuyển Branch
- Tạo branch mới:
  ```bash
  git branch feature-1
  ```
- Chuyển sang branch:
  ```bash
  git checkout feature-1
  ```
  Hoặc kết hợp tạo và chuyển:
  ```bash
  git checkout -b feature-1
  ```

### Bước 2: Merge Branch
- Chuyển về branch chính (`main`):
  ```bash
  git checkout main
  ```
- Gộp branch:
  ```bash
  git merge feature-1
  ```

### Bước 3: Xóa Branch
- Xóa branch sau khi merge:
  ```bash
  git branch -d feature-1
  ```

**Bài tập**:
- Tạo branch `add-readme`.
- Thêm nội dung vào `README.md` và commit.
- Merge branch vào `main` và xóa branch.

---

## Mô-đun 4: Làm Việc Với Remote Repository

### Bước 1: Kết nối với Remote Repository
- Tạo repository trên GitHub/GitLab/Bitbucket.
- Liên kết local repository:
  ```bash
  git remote add origin <URL-repository>
  ```
- Kiểm tra remote:
  ```bash
  git remote -v
  ```

### Bước 2: Push và Pull
- Đẩy code lên remote:
  ```bash
  git push origin main
  ```
- Lấy code từ remote:
  ```bash
  git pull origin main
  ```

**Bài tập**:
- Tạo repository trên GitHub.
- Liên kết và đẩy code từ local lên GitHub.
- Thử pull code từ remote về local.

---

## Mô-đun 5: Xử Lý Xung Đột Merge

### Bước 1: Hiểu về Xung Đột
- Xung đột xảy ra khi hai branch chỉnh sửa cùng một dòng trong cùng một file.
- Ví dụ: Cả `main` và `feature-1` chỉnh sửa `index.html`.

### Bước 2: Giải quyết Xung Đột
- Khi merge và có xung đột, Git sẽ đánh dấu trong file:
  ```text
  <<<<<<< HEAD
  Nội dung từ branch main
  =======
  Nội dung từ branch feature-1
  >>>>>>> feature-1
  ```
- Chỉnh sửa file để giữ nội dung mong muốn, sau đó:
  ```bash
  git add index.html
  git commit
  ```

**Bài tập**:
- Tạo xung đột bằng cách chỉnh sửa cùng một file trên hai branch.
- Merge và giải quyết xung đột.

---

## Mô-đun 6: Các Kỹ Năng Git Nâng Cao

### Bước 1: Quay Lại Lịch Sử Commit
- Xem lịch sử commit:
  ```bash
  git log --oneline
  ```
- Quay lại commit cũ (không xóa lịch sử):
  ```bash
  git checkout <commit-hash>
  ```
- Hoàn tác commit cuối:
  ```bash
  git revert <commit-hash>
  ```

### Bước 2: Reset và Xóa Thay Đổi
- Xóa thay đổi chưa commit:
  ```bash
  git restore index.html
  ```
- Reset về commit cụ thể (cẩn thận, có thể mất dữ liệu):
  ```bash
  git reset --hard <commit-hash>
  ```

### Bước 3: Stash - Lưu Tạm Thay Đổi
- Lưu tạm thay đổi:
  ```bash
  git stash
  ```
- Áp dụng lại thay đổi:
  ```bash
  git stash apply
  ```
- Xóa stash:
  ```bash
  git stash drop
  ```

### Bước 4: Rebase
- Sử dụng rebase để làm sạch lịch sử:
  ```bash
  git rebase main
  ```
- Rebase tương tác để chỉnh sửa commit:
  ```bash
  git rebase -i <commit-hash>
  ```

**Bài tập**:
- Thử hoàn tác một commit.
- Lưu tạm thay đổi bằng stash, chuyển branch, và áp dụng lại.
- Sử dụng rebase để gộp hai commit thành một.

---

## Mô-đun 7: Best Practices và Tình Huống Thực Tế

### Bước 1: Quy tắc làm việc với Git
- Commit thường xuyên với thông điệp rõ ràng.
- Sử dụng branch cho từng tính năng hoặc lỗi.
- Kéo code thường xuyên từ remote để tránh xung đột.

### Bước 2: Tình huống thực tế
- **Tình huống 1**: Khôi phục file bị xóa nhầm:
  ```bash
  git checkout HEAD^ -- index.html
  ```
- **Tình huống 2**: Sửa thông điệp commit:
  ```bash
  git commit --amend
  ```

**Bài tập**:
- Mô phỏng một dự án nhóm với 2 branch.
- Xử lý các tình huống như xóa nhầm file hoặc sửa commit.

---

## Kết Luận
- Sau khóa học, bạn sẽ nắm vững các lệnh Git cơ bản và nâng cao, từ việc khởi tạo repository đến xử lý xung đột và tối ưu hóa lịch sử commit.
- Tiếp tục thực hành bằng cách tham gia các dự án mã nguồn mở trên GitHub.

## Tài liệu tham khảo
- [Pro Git Book](https://git-scm.com/book/en/v2)
- [GitHub Docs](https://docs.github.com/en)