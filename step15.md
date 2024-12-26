# Reuse an Existing Route

Employees table hiện thị employees data. Tuy nhiên resumes của employees

Trong EmployeeOverviewContent, chúng tôi register event handle `itemPress` và đặt attribute `type` của `ColumnListItem` thành `Active` để chúng tôi có thể chọn một mục trigger và navigation

Add handler itemPress `.onItemPressed`vào `EmployeeOverviewContent`. Nó đọc binding context được chọn và navigation đến workerResume. Thêm route và mục tiêu tương ứng và hiện có thể sử dụng lại. Từ giờ trở đi, bạn có navigation employeeResume route đến employee detail page (the route name is employee)
