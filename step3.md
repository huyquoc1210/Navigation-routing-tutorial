# Catch Invalid Hashes

Đôi khi, việc hiển thị thông báo rằng tài nguyên được yêu cầu không được tìm thấy là rất quan trọng. Ví dụ: nếu một người dùng cố gắng truy cập một đường dẫn không hợp lệ mà không khớp với bất kỳ `route` nào đã được cấu hình, người dùng sẽ nhận được thông báo rằng có sự cố xảy ra. Bạn cũng có thể biết điều này như là một trang `404` hoặc `Not Found Page` trong các trang web truyền thống. Trong bước này, chúng ta sẽ triển khai một tính năng phát hiện các hash không hợp lệ và hiển thị chúng một cách đẹp mắt.

Mở rộng routing trong file descriptor bằng cách thêm property `bypassed` và đặt target của nó là `notFound`. Cấu hình này cho phép router hiển thị target `notFound` trong trường hợp không co route nào khớp với hash hiện tại. Tiếp theo, chúng thêm targets `notFound` vào phần `bypassed`. Targets `notFound` này chỉ đơn giản cấu hình một view `notFound` với hiệu ứng chuyển đổi `show`

Bây giờ, chúng ta sẽ tạo view đã được tham chiếu ở trên trong một tệp mới có tên là `NotFound.view.xml` trong thư mục `webapp/view`. View này sử dụng control `sap.m.MessagePage` để hiển thị thông báo lỗi cho người dùng. Trong một ứng dụng thực tế, bạn có thể sử dụng một thông báo động phù hợp với tình huống lỗi hiện tại. Tuy nhiên, ở đây, chúng ta chỉ đơn giản hiển thị một đoạn văn bản được cấu hình sẵn từ resource bundle.
