# User role controlled by request parameter

## Description:

[User role controlled by request parameter](https://0a0e006f045a9e22c0b34e5c003600e7.web-security-academy.net/)

![DES](../User-role-controlled-by-request-parameter/images/des.jpg)

> *Theo đề bài mô tả, có một bảng admin ở trang `/admin` nhưng cần xác minh, nhiệm vụ của ta là xóa user `carlos`, ta có thể sử dụng account `wiener/peter`.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra như bên dưới:*

![1](../User-role-controlled-by-request-parameter/images/image1.jpg)

* *Sử dụng account rồi đăng nhập:*

![2](../User-role-controlled-by-request-parameter/images/image2.jpg)


![3](../User-role-controlled-by-request-parameter/images/image3.jpg)

* *Ta thử truy cập vào `/admin` nhưng chỉ khi đăng nhập bằng admin mới có thể sử dụng:*

![EXTRA](../User-role-controlled-by-request-parameter/images/extra.jpg)

* *Sử dụng tool `Burp Suite` rồi bắt request, ta có thể thấy value của `Admin=false`:*

![4](../User-role-controlled-by-request-parameter/images/image4.jpg)

* *Thay đổi value `Admin=True` rồi `Forward`:*

![5](../User-role-controlled-by-request-parameter/images/image5.jpg)

* *Trong giao diện của người dùng giờ có thêm choice `Admin panel` hoặc có thể truy cập bằng url `/admin`:*

![6](../User-role-controlled-by-request-parameter/images/image6.jpg)

* *Truy cập và xóa user `carlos`, ta đã solved được bài lab này:*

![7](../User-role-controlled-by-request-parameter/images/image7.jpg)

![8](../User-role-controlled-by-request-parameter/images/image8.jpg)