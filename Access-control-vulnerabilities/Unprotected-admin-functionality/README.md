# Unprotected admin functionality

## Description:

[Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)

![DES](../Unprotected-admin-functionality/images/des.jpg)

> *Theo đề bài mô tả, trang web có một bảng admin nhưng không được bảo vệ, nhiệm vụ của ta là truy cập và bảng admin và xóa user `carlos`.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiển ra:*

![1](../Unprotected-admin-functionality/images/image1.jpg)

* *Ta thử truy cập vào /admin /admin.php nhưng không được, ta thử truy cập vào file ẩn `robots.txt`:*

![2](../Unprotected-admin-functionality/images/image2.jpg)

* *Sau khi truy cập vào file `robots.txt`, ta có thể thấy được phần `Disallow` của trang web là `/administrator-panel`, đó là bảng admin mà ta cần truy cập:*

![3](../Unprotected-admin-functionality/images/image3.jpg)

* *Ta thêm `/administrator-panel` vào url:*

![4](../Unprotected-admin-functionality/images/image4.jpg)

* *Sau khi dán, ta đã có thể truy cập vào bảng admin:*

![5](../Unprotected-admin-functionality/images/image5.jpg)

* *Tiến hành xóa user `carlos` và ta đã solved được lab này:*

![6](../Unprotected-admin-functionality/images/image6.jpg)