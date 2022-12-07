# User ID controlled by request parameter, with unpredictable user IDs

## Description:

[User ID controlled by request parameter, with unpredictable user IDs](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-unpredictable-user-ids)

![DES](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/des.jpg)

* *Theo đề bài mô tả, có một lỗ hổng truy nhập phân quyền theo chiều ngang nhưng được mã hóa bằng GUIDs. Nhiệm vụ của chúng ta là tìm được GUIDs của user `carlos` và tìm mã API của user này. Ta có thể sử dụng account `wiener:peter`.*

## Solution:

* *Một giao diện web sẽ hiển ra sau khi `Access the lab`:*

![EXTRA](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/extra.jpg)

* *Đăng nhập bằng account `wiener:peter`:*

![1](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image1.jpg)

* *Sử dụng tool `Burp Suite` bắt request của user, ta thấy id của wiener đã được mã hóa, giờ ta phải tìm id đã được mã hóa của user `carlos`:*

![2](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image2.jpg)

* *Ta thấy phần `Home` có các bài đăng của các user:*

![3](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image3.jpg)

* *Ta tìm một bài đăng của author `carlos`:*

![4](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image4.jpg)

* *Rồi sau đó bắt request rồi chuyển sang `Repeater`:*

![5](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image5.jpg)

* *Ở phần respone có trả về author và id của `carlos` như trong hình dưới:*

![6](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image6.jpg)

* *Trở về sửa đổi request của `My account` đổi GUIDs của `wiener` thành GUIDs của `carlos` mới tìm được lúc trước:*

![7](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image7.jpg)

* *Ở phần respone có trả về mã API của `carlos`:*

![8](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image8.jpg)

* *Sau khi submit mã API của `carlos`, ta đã solved được bài lab này:*

![9](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image9.jpg)

![10](../User-ID-controlled-by-request-parameter-with-unpredictable-user-IDs/images/image10.jpg)