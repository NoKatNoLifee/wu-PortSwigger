# Password brute-force via password change

## Description:

[Password brute-force via password change](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-brute-force-via-password-change)

![DES](../Password-brute-force-via-password-change/images/des.jpg)

> *Theo mô tả, chức năng đổi mật khẩu của bài lab này có thể bị tấn công `brute-force`. Nhiệm vụ của ta là đăng nhập được vào account `carlos`, sử dụng `brute-force` và list `password` đã được liệt kê. Ta có thể sử dụng account `wiener:peter`.*

## Solution:

* *Sau khi `Access the lab`. một giao diện web sẽ hiện ra:*

![1](../Password-brute-force-via-password-change/images/image1.jpg)

* *Login bằng account `wiener:peter`:*

![2](../Password-brute-force-via-password-change/images/image2.jpg)

* *Ta thấy có một giao diện thay đổi mật khẩu, trong đó có những ô: `Nhập mật khẩu hiện tại`, `Nhập mật khẩu mới` và `Xác nhận mật khẩu mới`:*

![3](../Password-brute-force-via-password-change/images/image3.jpg)

* *Sử dụng tool `Burp Suite` và bắt request khi thay đổi mật khẩu rồi `Send to Repeater`:*

![4](../Password-brute-force-via-password-change/images/image4.jpg)

* *Đầu tiên ta thử nhập `Mật khẩu hiện tại` chính xác và `Mật khẩu mới` và `Xác nhận mật khẩu mới` trùng nhau*
  *-> Sẽ trả về `Thay đổi mật khẩu thành công`.*

![5](../Password-brute-force-via-password-change/images/image5.jpg)

* *Sau đó ta thử nhập `Mật khẩu hiện tại` chính xác và `Mật khẩu mới` và `Xác nhận mật khẩu mới` không trùng nhau*
  *-> Sẽ trả về `Mật khẩu mới không trùng nhau`.*

![6](../Password-brute-force-via-password-change/images/image6.jpg)

* *Sau đó ta thử nhập `Mật khẩu hiện tại` không chính xác*
  *-> Sẽ trả về `Mật khẩu hiện tại không chính xác`.*

![7](../Password-brute-force-via-password-change/images/image7.jpg)

> *Từ những trường hợp trên ta có thể suy ra, nếu nhập mật khẩu hiện tại đúng thì sẽ trả về `Mật khẩu Mật khẩu mới không trùng nhau`.*

* *Sử dụng `Intruder`, thay đổi value `username = carlos`, nhập `Mật khẩu mới` và `Xác nhận mật khẩu mới` không trùng nhau và tiến hành `brute-force`.*

![8](../Password-brute-force-via-password-change/images/image8.jpg)

* *Thêm những `password` mà đã được liệt kê sẵn:*

![9](../Password-brute-force-via-password-change/images/image9.jpg)

* *Ở tab `Options`, phần `Grep-Match`, thêm dòng `New password do not match.` để ta có thể filter những value có Response trả về xuất hiện dòng này rồi `Start attack`:*

![10](../Password-brute-force-via-password-change/images/image10.jpg)

* *Sau khi `brute-force` xong, filter ta thấy có một value trả về có Response xuất hiện dòng `New password do not match.`:*

![11](../Password-brute-force-via-password-change/images/image11.jpg)

* *Sau khi có được `password`, tiến hành login bằng account `carlos` và ta đã solved được bài lab này:*

![12](../Password-brute-force-via-password-change/images/image12.jpg)

![13](../Password-brute-force-via-password-change/images/image13.jpg)