# Username enumeration via different responses

## Description:

[Username enumeration via different responses](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses)

![DES](../Username-enumeration-via-different-responses/images/des.jpg)

> *Theo đề bài mô tả, lab này có thể tấn công bằng phương pháp `brute-force`. Nhiệm vụ là tìm ra được username hợp lệ rồi tìm ra password rồi login bằng account tìm ra được.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra:*

![1](../Username-enumeration-via-different-responses/images/image1.jpg)

* *Nhập một `username` và `password` bất kì và sử dụng tool `Burp Suite` bắt request của phiên login này:*

![2](../Username-enumeration-via-different-responses/images/image2.jpg)

* *Chuyến sang tab `Intruder` để tiến hành tấn công `brute-force`:*

![3](../Username-enumeration-via-different-responses/images/image3.jpg)

* *Trước tiên, tiến hành tấn công `brute-force` username để tìm ra username hợp lệ:*

![4](../Username-enumeration-via-different-responses/images/image4.jpg)

* *Ở mục `Payload`, sử dụng những username mà theo mô tả đã cho sẵn:*

![5](../Username-enumeration-via-different-responses/images/image5.jpg)

* *Sau khi `brute-force`, filter `Status` và `Length` và ta thấy có một username trả về `Length` khác:*

![6](../Username-enumeration-via-different-responses/images/image6.jpg)

* *Và phần `Respone` trả về `Invalid Password` trong khi những phần khác trả về `Invalid Username`, chứng tỏ `username` này là hợp lệ:*

![EXTRA1](../Username-enumeration-via-different-responses/images/extra1.jpg)

* *Khi đã có `username` hợp lệ, ta tiến hành `brute-force` `password`:*

![7](../Username-enumeration-via-different-responses/images/image7.jpg)

* *Sử dụng những `password` mà phần mô tả đã cho sẵn:*

![8](../Username-enumeration-via-different-responses/images/image8.jpg)

* *Sau khi `brute-force`, ta thấy có một `password` trả về `Status` và `Length` khác với các `password` còn lại:*
 
![9](../Username-enumeration-via-different-responses/images/image9.jpg)

![EXTRA2](../Username-enumeration-via-different-responses/images/extra2.jpg)

* *Tiến hành login bằng `username` và `password` ta đã tìm ra,solved thành công bài lab này:*

![10](../Username-enumeration-via-different-responses/images/image10.jpg)

![11](../Username-enumeration-via-different-responses/images/image11.jpg)