# Step1

## The Initial App

### Home Page

Home page trong app được xác định webapp/index.html. Khởi động SAPUI5 và cho bộ thực thi biết nới tìm custom resources.Hơn nữa khởi tạo MockServer back-end requests. Cuối cùng ,chúng ta khởi tạo app, gắn nó `m.Sell` và đặt `m.Shell` làm body.`Component.js`

### Data

`webapp/localService/mockserver.js`. Sử dụng mock server

file `metadata.xml` mô phỏng `OData`:

- Employee: employees có tất property điển như `firstName` và `lastName` cũng như property navigation resume được tham chiếu bởi ResumeID. ID property: EmployeeID. `EntitySet` là Employees. Data tương ứng một số employees nằm file `webapp/localService/mockdata/Employees.json file`

- Resume: chúng tôi muốn giữ resume của employees very simple.
  Vì vậy, chúng ta chỉ có các properties đơn giản type `Edm.String`. Các properties Information, Project, Hobbies and Node ; tất cả đều chứa văn bản. Thực thể có property ID ResumeID và EntitySet tương ứng là Resume. Resume data nằm trong webapp/localService/mockdata/Resumes.json.

### Config App

file webapp/manifest.json, cấu hình app.

- sap.app
  tham chiếu i18n.properties và sử dụng special syntax để liên kết title và description properties

  dataSources, chúng tôi cho app biết employees từ ODataRemote của chúng tôi. uri tương quan với rootUri của mockServer, có thể tìm thấy webapp/localService/mockserver.js .

- sap.ui5
  Trong SAP UI5, sử dụng `rootView`để khai rằng view `sap.ui.demo.nav.view.App` sử dụng tải và sử dụng làm rootView cho ứng dụng của chúng ta. Bên cạnh đó, dùng 2 model 1 là i18n và "" (mặc định). Model mặc định tham chiếu đến `employeeRemote` trong `dataSource`, được khai báo trong `sap.app` như là nguồn tài liệu OData 2.0 file `i18n` có thể được tìm thấy tại `webapp/i18n/i18n.properties`. Nguồn dữ liệu được giả lập (mock) bởi mock server của chúng ta
