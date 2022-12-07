# Username enumeration via subtly different responses

## Description:

[Username enumeration via subtly different responses](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-subtly-different-responses)

![DES](../Username-enumeration-via-subtly-different-responses/images/des.jpg)

> *Theo mô tả, bài lab này có `username` và `password` có thể tấn công bằng `brute-force`. Nhiệm vụ của ta là tìm ra account này rồi login vào.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra:*

![1](../Username-enumeration-via-subtly-different-responses/images/image1.jpg)

* *Nhập một `username` và `password` bất kì:*

![2](../Username-enumeration-via-subtly-different-responses/images/image2.jpg)

* *Rồi sử dụng tool `Burp Suite` để bắt request login:*

![3](../Username-enumeration-via-subtly-different-responses/images/image3.jpg)

* *`Send to Repeater`, ta thấy ở phần Respone, khi nhập sai  thông tin thì sẽ trả về `Invalid username or password.` nên khi `brute-force` ra username hợp lệ sẽ không trả về `Invalid password`:*

![4](../Username-enumeration-via-subtly-different-responses/images/image4.jpg)

* *Tiến hành `brute-force` `username`:*

![5](../Username-enumeration-via-subtly-different-responses/images/image5.jpg)

* *Ở phần `Payload`, thêm những username mà đề bài đã cho sẵn:*

![6](../Username-enumeration-via-subtly-different-responses/images/image6.jpg)

* *Ở phần `Options` kéo đến `Grep - Extract` rồi `Add`:*

![7](../Username-enumeration-via-subtly-different-responses/images/image7.jpg)

* *Sẽ ra một bảng tùy chọn, ta sẽ chọn những thông tin mình muốn tìm ở Respone, nhấn `Fetch response`:*

![8](../Username-enumeration-via-subtly-different-responses/images/image8.jpg)

* *Kéo đến khi thấy dòng `Invalid username or password.` rồi bôi đen, ấn `OK`:*

![9](../Username-enumeration-via-subtly-different-responses/images/image9.jpg)

* *Sau khi `Start attack`, sẽ hiện ra bảng kết quả, filter ta sẽ thấy có một value sẽ trả về response khác với những username còn lại `Invalid username or password` và không có dấu `.`*

![10](../Username-enumeration-via-subtly-different-responses/images/image10.jpg)

* *Sau khi tìm ra được `username` hợp lệ, ta tiến hành `brute-force` để tìm ra `password` hợp lệ:*

![11](../Username-enumeration-via-subtly-different-responses/images/image11.jpg)

* *Sử dụng những `password` đã được liệt kê:*

![12](../Username-enumeration-via-subtly-different-responses/images/image12.jpg)

* *Sau khi `brute-force`, ta thấy có một value trả về `Stutus` và` Length` khác với những value còn lại:*

![13](../Username-enumeration-via-subtly-different-responses/images/image13.jpg)

* *Login bằng account vừa tìm ra và ta đã solved được bài lab này:*

![14](../Username-enumeration-via-subtly-different-responses/images/image14.jpg)

![15](../Username-enumeration-via-subtly-different-responses/images/image15.jpg)