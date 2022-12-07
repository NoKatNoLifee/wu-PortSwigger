# Insecure direct object references

## Description:

[Insecure direct object references](https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references)

![DES](../Insecure-direct-object-references/images/des.jpg)

> *Theo đề bài mô tả, bài lab này có mục live chat ở hệ thống người dùng. Nhiệm vụ của ta là tìm được password của user `carlos` rồi login vào account này.*

## Solution:

* *Sau khi `Access the lab`, một giao diện web sẽ hiện ra như bên dưới:*

![1](../Insecure-direct-object-references/images/image1.jpg)

* *Truy cập vào phần `Live chat`:*

![2](../Insecure-direct-object-references/images/image2.jpg)

* *Nhắn thử vài câu bất kì nhưng có gì xảy ra nhưng sau khi ấn `View transcript` thì đoạn chat sẽ dừng lại và sẽ download một file `txt`:*

![3](../Insecure-direct-object-references/images/image3.jpg)

![4](../Insecure-direct-object-references/images/image4.jpg)

* *Nhưng điều đáng nói ở đây là download file `2.txt` và ấn tiếp 1 lần nữa sẽ download file `3.txt` nên ta suy đoán file `1.txt` đã có sẵn:*

![5](../Insecure-direct-object-references/images/image5.jpg)

* *Sử dụng tool `Burp Suite` rồi thay đổi request thành file `1.txt` rồi xem `Response`:*

![6](../Insecure-direct-object-references/images/image6.jpg)

* *`Response` sẽ trả về nội dung của file `1.txt`, trong đó có password của user `carlos`:*

![7](../Insecure-direct-object-references/images/image7.jpg)

* *Tiến hành login bằng account `carlos` và ta đã solved được bài lab này:*

![8](../Insecure-direct-object-references/images/image8.jpg)

![9](../Insecure-direct-object-references/images/image9.jpg)


