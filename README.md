# downloads

npm i

npm run safe-dist

npm run dist

lÔI RPM I
npm : File C:\Program Files\nodejs\npm.ps1 cannot be loaded because running scripts is disabled on this system. For
more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ npm i
+ ~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

  Lỗi bạn gặp phải liên quan đến chính sách thực thi trong PowerShell, ngăn không cho các script chạy trên hệ thống của bạn. Điều này xảy ra khi chính sách thực thi được đặt là Restricted, nghĩa là không cho phép chạy bất kỳ script PowerShell nào, bao gồm cả các lệnh npm.

Để khắc phục vấn đề này, bạn cần thay đổi chính sách thực thi để cho phép chạy các script. Dưới đây là các bước để làm điều đó:

Các bước thay đổi chính sách thực thi:
Mở PowerShell với quyền Administrator:

Nhấn chuột phải vào menu Start và chọn Windows PowerShell (Admin) hoặc Command Prompt (Admin) (tùy thuộc vào hệ thống của bạn).

Kiểm tra chính sách thực thi hiện tại: Trong cửa sổ PowerShell, gõ lệnh sau và nhấn Enter để kiểm tra chính sách thực thi hiện tại:

powershell
Copy
Edit
Get-ExecutionPolicy
Nếu trả về Restricted, đó là lý do bạn gặp phải lỗi.

Thay đổi chính sách thực thi: Để cho phép thực thi các script, bạn cần thay đổi chính sách thực thi. Gõ lệnh sau để thiết lập chính sách thành RemoteSigned:

powershell
Copy
Edit
Set-ExecutionPolicy RemoteSigned
Chính sách này cho phép các script tạo ra trên máy tính của bạn chạy, nhưng các script tải về từ internet sẽ yêu cầu có chữ ký.

Xác nhận thay đổi: Sau khi nhập lệnh trên, PowerShell sẽ yêu cầu bạn xác nhận thay đổi. Gõ Y và nhấn Enter để xác nhận.

Chạy lại lệnh npm: Bây giờ bạn có thể thử lại lệnh npm i mà không gặp phải lỗi bảo mật nữa.

Lưu ý:
RemoteSigned là chính sách tốt để vừa đảm bảo tính bảo mật, vừa cho phép chạy các script nội bộ, nhưng lại yêu cầu chữ ký cho các script tải từ internet.

Nếu bạn muốn thay đổi chính sách trở lại Restricted sau này, bạn có thể chạy:

powershell
Copy
Edit
Set-ExecutionPolicy Restricted
Hy vọng cách làm này sẽ giúp bạn giải quyết vấn đề! Nếu có thắc mắc nào, đừng ngần ngại hỏi nhé.
