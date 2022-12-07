# User ID controlled by request parameter

## Description:

[User ID controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter)

![DES](../User-ID-controlled-by-request-parameter/images/des.jpg)

> *Theo đề bài mô tả, trang web này có lỗ hổng leo quyền theo chiều ngang. Nhiệm vụ của chúng ta là tìm được mã API của user `carlos`. Ta có thể dùng account `wiener:peter`.*

## Solution:

* *Đây là giao diện web sau khi ta truy cập đường link:*

![1](../User-ID-controlled-by-request-parameter/images/image1.jpg)

* *Sau khi đăng nhập với tài khoản, đây là giao diện của người dùng, có mã API của user `wiener`:*

![2](../User-ID-controlled-by-request-parameter/images/image2.jpg)

* *Sử dụng tool `Burp Suite` để bắt request, ta thấy dòng url có `?id=wiener`:*

![3](../User-ID-controlled-by-request-parameter/images/image3.jpg)

* *Đổi `wiener` thành `carlos` rồi send request:*

![EXTRA](../User-ID-controlled-by-request-parameter/images/extra.jpg)

* *Trong phần respone kéo xuống ta sẽ thấy mã API của user `carlos`.*

![4](../User-ID-controlled-by-request-parameter/images/image4.jpg)

* *Nhập mã API của `carlos` và ta đã solved được bài lab này:* 

![5](../User-ID-controlled-by-request-parameter/images/image5.jpg)

![6](../User-ID-controlled-by-request-parameter/images/image6.jpg)

