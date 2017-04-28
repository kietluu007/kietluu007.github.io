---
layout: post
title:  "Giới Thiệu Về React-Native"
date:   2017-4-28 21:45:10 +0800
tags:

categories:

---
# Phần giới thiệu
React-native là framewokd giúp lập trình viên viết ứng dụng trên nền tảng android và iOS, sử dụng javasript nhưng mang lại cảm giác native app thực sự.
Ở React-native có ưu điểm là tích hợp tính năng Live Reaload khác với ReLoad. Nếu ReLoad  cần tải lại mã nguồn để cập nhật thì Live ReLoad chỉ cập nhập lại các chức năng của tập tin nếu có sự thay đổi.
Cài đặt Node js, SDK tool, thiết bị máy ảo, Android studio, set lại biến Environment, đường dẫn path, PATH.
Để tạo react-native ta dùng lệnh cmd: npm install –g react-native cli.
Để run một folder tại tại folder đó ta dùng cmd: react-native run-android.
## Cách hoạt động của React-native.
Gồm phần View ( hiển thị ) và phần xử lí.
  * Phần hiển thị biên dịch từ java sẽ map với component.
  * Phần xử lí được thực hiện trực tiếp bằng javascript được xử lí dưới bộ core của 
  javascript, không phải thông dịch qua java.
**-Ưu điểm:**
  * Mang lại cảm giác trải nghiệm giống native.
  * Có thể tiếp cận nhiều hơn với ko chỉ javascript mà còn web.
**-Khuyết điểm:** 
  * Còn thiếu nhiều Component view.
  * Chỉ hỗ trợ cho IOS và Android, không hỗ trợ Window Phone.
  * Không build được các ứng dụng phức tạp vì mỗi ứng dụng native  bằng javascript luôn có các component được viết sẵn. Vì vậy khi ứng dụng của bạn quá phức tạp bạn phải chỉnh sửa lại component  viết bằng ngôn ngữ IOS hoặc android thì mới build được.

### Cách xây dựng chức năng cơ bản của React-native.
 * B1: Import các thư viện
  * Import thư viện react,Component from  react
  * Import danh sách các kiểu lable mà ta sử dụng (Text,  AppRegistry, View, StyleSheet) from react-native.
  * Import các class  gọi Component phụ nếu có.
 * B2: Viết code cho các Component.
  * Mỗi class là một Componet vì nó được kế thừa từ Component.
  * Class chính của Component có render() và trong Render(return ()) để trả về View mà ta vừa thiết kế. 
  * Có thể có Class phụ , khi đó ta cần đặt từ khóa export default trước class phụ đó (thường android sẽ không hỗ trợ cách thiết kế này mà thay vào đó thiết kế một component riêng biệt ở một thư mục khác).

## Về phần seminar:
### Component của project:
  * gồm thư mục con screen chứa file ManHinh1.js là màn hình chính, và Manhinh2.js là màn hình phụ được gọi sau khi click button ở màn hình chính và ngược lại. 
  *	thư mục api gồm file api.js với chức năng tạo kết nối trên firebase-một dbms lưu dữ liệu trực tuyến.
  * Để tạo firebase ta vào trang chủ https://console.firebase.google.com/ sau đó ta khởi tạo một database mới trong mục creat project  sau khi nhấn nút create xong bạn sẽ lấy được file cấu hình của database treenn firebase. Copy mớ đó vào trong file api.js . Database được lưu dưới dạng object, nó sẽ lưu key của từng dòng dữ liệu, mỗi dòng dữ liệu được cấp một key  trong mỗi key lưu username và password.
  * thư mục image chứa các hình ảnh local.
  * thư mục styles để định nghĩa css. Cuối class ta sử dụng từ khóa export default styles để tạo biến styles là biến toàn cục để truy xuất các thuộc tính trong css ta chỉ cần gọi this.styles.tenthuoctinh. Tại các file screen muốn gọi css phải import file vào.
 * B3: Đăng kí Register cho các Component. Vì một project có nhiều Component ta đăng kí Register để chọn component được chọn.

### Tương tác các màn hình gọi lẫn nhau trong thư mục index.android.js
### Cách thiết kế các màn hình trong Component với các phương thức class được khởi tạo.

Cách tạo một Component phụ.
  * Tại folder chính chỉ có một Component , để tạo một component khác ta phải tạo một folder từ thư mục gốc ta tạo một file.js ( Tên file phải có kí tự đầu tiên là chữ hoa) .

  * file.js  ta thiết kế một như một Component chính, nhưng tại class này không có Register.
 Để gọi component  phụ này ta phải import vào Component chính theo định dạng:
* *Import  tenclass  from ‘ ./folder/file.js’ (với ./ là để di chuyển tới thư mục gốc)*
  * Sử dụng Constructer  và state để thiết lập trạng thái cho khởi tạo ban đầu.
#### Cách các màn hình gọi nhau
   > Sử dụng Nagivator để định nghĩa sựa lựa chọn màn hình được sử dụng. Trong Nagivator sẽ có 2 thuộc tính là Interout : để chỉ là lấy chọn mang hình nào  Renderscene để thực hiện lựa chọn nào( route,nagivator ). Sử dụng switch-case để truyền vào tên màn hình và sử dụng nagivator để push vào tên màn hình sẽ được gọi.

**Thiết kế các design pattern trong file Ha.js và Manhinh2.js**
Để kéo thả images ta có thể dùng require để lấy ra hình ảnh nội bộ, và hình ảnh internet ta phải dùng biến môi trường uri để load hình ảnh.
 *Ha.js : Gồm hiển thị ListView, đăng nhập, đăng kí tài khoản.*
Để xem cách sử dụng của các phương thức ta vào [đây](https://facebook.github.io/react-native) có hướng dẫn đầy đủ các phương thức. 
#### Cách sử dụng ListView: 
**Đọc dữ liệu từ firebase** 
  * database=firebase.database() *để gọi database từ firebase*                        * user=database.ref('User'); *thực hiện referencen đến bảng User trên db*
  * dataSource:newListView.DataSource({rowHasChanged:(r1,r2)=>r1!==r2}) *để  khởi tạo datasoure bằng một giá trị ListView*
 * Định nghĩa hàm submit()//là hàm để thêm một tài khoản vào user bằng phương thức user.push().
 * Hàm componentWillMount() để đọc dữ liệu database.ref('User').on('value',(snap)// để reference tới bảng user và lắng nghe sự kiện ,các giá trị value được lắng nghe truyền qua biến snap để đọc từng dòng và truyền vào mảng các item[] các giá trị được đọc vào.
Sử dụng phương thức 
  *this.setState({dataSource:this.state.dataSource.cloneWithRows(items)});*
Để sao chép các dòng trong mảng items vào datasource để show trong listview.
 * Hàm  renderRow(data) để in từng dòng dữ liệu trên View.
**Cách sử dụng TextInput**
  * Thiết kế định dạng cho textinput với styles và sau đó đổ textinput lên View bằng phương thức this.setState().
**Sử dụng Button**: định dạng cho button và bắt sự kiện cho button bằng phương thức onPress .
**Cách sử dụng DatePicker để tạo lịch**
 * Thực hiện install datePicker bằng cầu lệnh:
   npm react-native-android-datepicker  --save    , để sử dụng datepicker có sãn trên android.  Thực hiện định dạng kiểu hiển thị ngày tháng , khởi tạo ngày tháng, ngày bắt đầu và ngày kết thúc trên lịch, thực hiện set datepicker lên giao diện (có thể xem ví dụ trên [đây](https://facebook.github.io/react-native/docs/getting-started.html)).
**Cách sử dụng Picker để hiển thị các sự lựa chọn** 
 * Picker.Item lable=”aa”  value=”AA” để hiển thị các giá trị được show.



