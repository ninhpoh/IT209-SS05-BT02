# Bài 2: Tái cấu trúc lịch sử commit bằng Interactive Rebase

## 1. Mục tiêu

* Sử dụng Interactive Rebase để chỉnh sửa lịch sử commit.
* Gộp nhiều commit nhỏ thành một commit duy nhất.
* Thay đổi thông điệp commit.
* Xóa commit chứa file rác thử nghiệm.

## 2. Các commit ban đầu

Đã tạo 4 commit:

```text
feat: khoi tao module auth
fix typo
adds utility functions
add temp file for debug
```

## 3. Thực hiện Interactive Rebase

Sử dụng lệnh:

```bash
git rebase -i HEAD~4
```

Cấu hình:

```text
pick    feat: khoi tao module auth
squash  fix typo
squash  adds utility functions
drop    add temp file for debug
```

## 4. Thông điệp commit sau khi gộp

Sau khi thực hiện squash, thông điệp commit được thay đổi thành:

```text
feat: hoan thien module authentication
```

## 5. Kiểm tra lịch sử commit

Sử dụng:

```bash
git log --oneline
```

Kết quả mong đợi:

```text
<commit-id> feat: hoan thien module authentication
```

Các commit nhỏ đã được gộp thành một commit duy nhất.

Commit `add temp file for debug` đã được xóa bằng `drop`.

## 6. Kiểm tra file

Sử dụng:

```bash
ls -la
```

File `temp.txt` không còn tồn tại.

## 7. Kết luận

Đã hoàn thành việc tái cấu trúc lịch sử commit bằng Interactive Rebase.

Lịch sử tính năng sau khi làm sạch chỉ còn một commit:

```text
feat: hoan thien module authentication
```
