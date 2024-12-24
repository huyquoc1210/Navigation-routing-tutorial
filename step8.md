# Navigate with Flip Transition

Minh hoạ cách navigation đến 1 page với hiệu ứng chuyển tiếp.Cả 2 hướng tiến và lùi sẽ sử dụng flip nhưng hướng khác nhau. Chúng ta sẽ tạo một liên kết đơn giản trên `Employee` view để kích hoạt điều hướng flip đến một trang hiển thị dữ liệu lý lịch (resume) của một employees nhất định. Khi nhấn nút `Back`, hệ thống sẽ điều hướng quay lại `Employee` view với hiệu ứng flip ngược

Thêm 1 `Flip to Resume` link ở `Employee Details`, view để trigger navigation resume hiện đang hiển thị

Sau đó, chúng ta thay đổi file `Employee.controller.js` bằng cách thêm trình xử lý sự kiện `onShowResume` cho liên kết "Flip to Resume". Trình xử lý này đơn giản điều hướng đến một route mới `employeeResume` và điền tham số bắt buộc `employeeId` với thuộc tính `EmployeeID` từ context đã được ràng buộc của view. Route `employeeResume` hiện chưa có, vì vậy chúng ta sẽ cần thêm nó vào cấu hình định tuyến của chúng ta.

Trong cấu hình định tuyến, chúng ta thêm một route mới `employeeResume` tham chiếu đến một target có cùng tên. Mẫu của route này yêu cầu tham số bắt buộc `{employeeId}` và kết thúc với chuỗi tĩnh `/resume`.

Target employeeResume tham chiếu đến view `employee.Resume` mà chúng ta sắp tạo. Mức độ của target này là 4; so với target `employee`, đây là một mức thấp hơn một cấp nữa. Để cấu hình điều hướng flip, chúng ta chỉ cần thiết lập transition của target là `flip`. Cùng với cấu hình mức độ chính xác, điều này sẽ kích hoạt điều hướng flip đúng khi target được hiển thị, bao gồm cả điều hướng tiến và lùi.

Tạo file `Resumee.controller.js` trong thư mục `webapp/controller/employee`. Trong controller này, chúng ta sẽ đảm bảo rằng view được ràng buộc với thông tin nhân viên đúng khi route `employeeResume` được match. Chúng ta đã sử dụng phương pháp này trong bước trước, vì vậy bạn sẽ nhận ra các phần cấu thành trong mã trên. Nếu không tìm thấy nhân viên, chúng ta sẽ hiển thị target `notFound`.

Tạo file `ResumeProjects.view.xml` trong thư mục `webapp/view/employee`. View này không cần controller vì nó chỉ hiển thị một điều khiển `Text` với nội dung về các dự án của nhân viên được chọn. Nó minh họa rằng việc sử dụng nested views kết hợp với điều hướng và định tuyến trong SAPUI5 hoạt động rất tốt.
