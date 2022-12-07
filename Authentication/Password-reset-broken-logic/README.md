# Password reset broken logic

## Description:

[Password reset broken logic](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-broken-logic)

![DES](../Password-reset-broken-logic/images/des.jpg)

> *Theo đề bài mô tả, lab này có chức năng reset mật khẩu có thể bị tấn công. Nhiệm vụ của ta là reset mật khẩu của user `carlos` sau đó login và truy cập trang `My account` của tài khoản này:*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra:*

![1](../Password-reset-broken-logic/images/image1.jpg)

* *Ở giao diện login, có phần `Forgot password?`:*

![2](../Password-reset-broken-logic/images/image2.jpg)

* *Nhập `wiener` vào phần username vì `Email client` để mặc định là của user `wiener`:*

![3](../Password-reset-broken-logic/images/image3.jpg)

![4](../Password-reset-broken-logic/images/image4.jpg)

* *Ở giao diện `Email client` có một đường link dẫn ta đến giao diện nhập password mới:*

![5](../Password-reset-broken-logic/images/image5.jpg)

* *Nhập password bất kì rồi sử dụng tool `Burp Suite` bắt request:*

![6](../Password-reset-broken-logic/images/image6.jpg)

* *Ta thấy ở phần request có tham số `temp-forgot-password-token` không đổi mỗi khi ta reset password:*

![7](../Password-reset-broken-logic/images/image7.jpg)

* *Ta thay đổi value của user từ `wiener` thành `carlos` còn password có thể giữ nguyên:*

![8](../Password-reset-broken-logic/images/image8.jpg)

* *Tiến hành login bằng account `carlos:123` và ta đã solved được bài lab này:*

![9](../Password-reset-broken-logic/images/image9.jpg)