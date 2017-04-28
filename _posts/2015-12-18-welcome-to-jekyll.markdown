---
layout: post
title:  "Giới Thiệu Về React-Native"
date:   2017-4-28 21:45:10 +0800
tags:

categories:

---
React-native là framewokd giúp lập trình viên viết ứng dụng trên nền tảng android và iOS, sử dụng javasript nhưng mang lại cảm giác native app thực sự.
Ở React-native có ưu điểm là tích hợp tính năng Live Reaload khác với ReLoad. Nếu ReLoad  cần tải lại mã nguồn để cập nhật thì Live ReLoad chỉ cập nhập lại các chức năng của tập tin nếu có sự thay đổi.
Cài đặt Node js, SDK tool, thiết bị máy ảo, Android studio, set lại biến Environment, đường dẫn path, PATH.
Để tạo react-native ta dùng lệnh cmd: npm install –g react-native cli.
Để run một folder tại tại folder đó ta dùng cmd: react-native run-android.
### Cách hoạt động của React-native.
Gồm phần View ( hiển thị ) và phần xử lí.
  * Phần hiển thị biên dịch từ java sẽ map với component.
  * Phần xử lí được thực hiện trực tiếp bằng javascript được xử lí dưới bộ core của 
  javascript, không phải thông dịch qua java.
##### Ưu điểm: 
  * Mang lại cảm giác trải nghiệm giống native.
  * Có thể tiếp cận nhiều hơn với ko chỉ javascript mà còn web.
#####Khuyết điểm: 
  * Còn thiếu nhiều Component view.
  * Chỉ hỗ trợ cho IOS và Android, không hỗ trợ Window Phone.
  *Không build được các ứng dụng phức tạp vì mỗi ứng dụng native  bằng javascript luôn có các component được viết sẵn. Vì vậy khi ứng dụng của bạn quá phức tạp bạn phải chỉnh sửa lại component  viết bằng ngôn ngữ IOS hoặc android thì mới build được.

### Cách xây dựng chức năng cơ bản của React-native.
 * B1: Import các thư viện
  * Import thư viện react,Component from  react
  * Import danh sách các kiểu lable mà ta sử dụng (Text,  AppRegistry, View, StyleSheet ) from react-native.
  * Import các class  gọi Component phụ nếu có.
 * B2: Viết code cho các Component.
  * Mỗi class là một Componet vì nó được kế thừa từ Component.
  * Class chính của Component có render() và trong Render(  return () )để trả về View mà ta vừa thiết kế. 
  * Có thể có Class phụ , khi đó ta cần đặt từ khóa export default trước class phụ đó ( thường android sẽ không hỗ trợ cách thiết kế này mà thay vào đó thiết kế một component riêng biệt ở một thư mục khác).


