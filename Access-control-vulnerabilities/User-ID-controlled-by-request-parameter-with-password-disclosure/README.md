# User ID controlled by request parameter with password disclosure

## Description:

[User ID controlled by request parameter with password disclosure](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-password-disclosure)

![DES](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/des.jpg)

> *Theo đề bài mô tả, ở trang tài khoản của người dùng có chức năng cập nhật mật khẩu và mật khẩu được hiện điền sẵn ở đó. Nhiệm vụ của ta là lấy lại được mật khẩu của `administator` rồi đăng nhập xóa user `carlos`. Ta có thể dùng account `wiener:peter`.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra như bên dưới:*

![1](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image1.jpg)

* *Login bằng account `wiener:peter`:*

> *Ta thấy sau khi đăng nhập, phần password sẽ hiện như ở bên dưới:*

![2](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image2.jpg)

* *Sử dụng tool `Burp Suite` để bắt request khi truy cập vào trang `My account`, ta thấy có `?id=wiener`:*

![3](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image3.jpg)

* *Thay đổi `wiener` thành `administrator` rồi kiểm tra `Respone`:*

![4](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image4.jpg)

* *Ở `Respone` trả về trang tài khoản của admin và tất nhiên có cả password có value như ở dưới:*

![5](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image5.jpg)

* *Sau khi biết password của administrator, tiến hành login:*

![6](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image6.jpg)

* *Ở account của administrator có thêm `Admin panel`:*

![7](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image7.jpg)

* *Tiến hành xóa user `carlos` và ta đã solved được bài lab này:*

![8](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image8.jpg)

![9](../User-ID-controlled-by-request-parameter-with-password-disclosure/images/image9.jpg)