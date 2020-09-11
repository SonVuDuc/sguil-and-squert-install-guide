# Sguil và Squert Install Guide

## 1. Yêu cầu 
  + VM với RAM 4GB, CPU 2 cores và ổ cứng 25GB
  + VMware
  + File ISO Security Onion download tại https://github.com/Security-Onion-Solutions/security-onion/blob/master/Verify_ISO.md
  
## 2. Cài đặt

### 2.1 Verify file ISO và cài đặt VM

Tạo 1 thư mục tên là SecurityOnion

Download signing key và import key bằng lệnh 
```
wget https://raw.githubusercontent.com/Security-Onion-Solutions/security-onion/master/KEYS
gpg --import KEYS
```
Download signature file cho file ISO
```
wget https://github.com/Security-Onion-Solutions/security-onion/raw/master/sigs/securityonion-16.04.7.1.iso.sig
```

Download ISO image
```
wget https://download.securityonion.net/file/Security-Onion-16/securityonion-16.04.7.1.iso
```

Verify file ISO bằng lệnh
```
gpg --verify securityonion-16.04.7.1.iso.sig securityonion-16.04.7.1.iso
```

Verify hoàn tất

![Screenshot from 2020-09-12 00-51-30](https://user-images.githubusercontent.com/32956424/92957088-3207dc80-f492-11ea-99b2-36675858948a.png)

Sau đó có thể cài đặt VM bằng file ISO

### 2.2 Cài đặt Security Onion

Cài đặt VM Security Onion với file ISO đã download trước đó
![VirtualBox_Security Onion_11_09_2020_17_04_30](https://user-images.githubusercontent.com/32956424/92940454-5905e480-f479-11ea-9092-baf6a184c73a.png)

![VirtualBox_Security Onion_11_09_2020_17_06_15](https://user-images.githubusercontent.com/32956424/92940541-73d85900-f479-11ea-85bb-b2a7c90690b7.png)

Click vào icon **Install SecurityOnion** để cài đặt Security Onion

![VirtualBox_Security Onion_11_09_2020_17_07_36](https://user-images.githubusercontent.com/32956424/92940763-b39f4080-f479-11ea-8b76-ec5c08ff3ede.png)

Tích vào ô **Download Update** và chọn **Continue**

![VirtualBox_Security Onion_11_09_2020_17_08_34](https://user-images.githubusercontent.com/32956424/92941230-51930b00-f47a-11ea-920c-e5db61ccde1d.png)

Chọn **Install Now**

![VirtualBox_Security Onion_11_09_2020_17_08_48](https://user-images.githubusercontent.com/32956424/92940992-04169e00-f47a-11ea-816d-8907571deb74.png)

Quá trình cài đặt sẽ mất khoảng 5 phút

![VirtualBox_Security Onion_11_09_2020_17_11_35](https://user-images.githubusercontent.com/32956424/92941295-64a5db00-f47a-11ea-9f7b-2ec8aebfc65f.png)

Sau khi cài đặt xong, hệ thống sẽ yêu cầu restart

![VirtualBox_Security Onion_11_09_2020_17_20_01](https://user-images.githubusercontent.com/32956424/92941370-7ab39b80-f47a-11ea-8d8f-793fa0096291.png)

Click vào file Setup 

![Security Onion-2020-09-11-21-30-19](https://user-images.githubusercontent.com/32956424/92941436-9028c580-f47a-11ea-9b09-01af7985ffa1.png)

Chọn **Yes, configure /etc/network/interfaces**

![Security Onion-2020-09-11-21-30-35](https://user-images.githubusercontent.com/32956424/92941577-c36b5480-f47a-11ea-9eff-71d020ac5641.png)

Chọn **DHCP**

![Security Onion-2020-09-11-21-30-45](https://user-images.githubusercontent.com/32956424/92941640-da11ab80-f47a-11ea-8bd9-983ef4e1cbc0.png)

Chọn **Yes, make changes!**

![Security Onion-2020-09-11-21-30-49](https://user-images.githubusercontent.com/32956424/92941684-e5fd6d80-f47a-11ea-98f8-1b9f58579a76.png)

Configure xong, chọn **Yes, reboot**

![Security Onion-2020-09-11-21-30-55](https://user-images.githubusercontent.com/32956424/92941748-f7467a00-f47a-11ea-935b-559f149bf658.png)

Sau khi reboot, click vào file setup một lần nữa

Chọn **Yes, skip network configuration**

![Security Onion-2020-09-11-21-32-21](https://user-images.githubusercontent.com/32956424/92941872-1d6c1a00-f47b-11ea-83a5-d7b203b15e6e.png)

Tích vào **Evaluation Mode** và chọn **OK**

![Security Onion-2020-09-11-21-37-17](https://user-images.githubusercontent.com/32956424/92942010-442a5080-f47b-11ea-975e-4a5892788d9f.png)

Tạo 1 user, user này sẽ dùng để đăng nhập vào **Sguil**, **Squert** và **Kibana**

![Security Onion-2020-09-11-21-37-29](https://user-images.githubusercontent.com/32956424/92942123-67ed9680-f47b-11ea-81d5-df360b19f31e.png)

Nhập password

![Security Onion-2020-09-11-21-37-34](https://user-images.githubusercontent.com/32956424/92942172-73d95880-f47b-11ea-9150-c89318eed572.png)

Chọn **Yes, proceed with the changes**

![Security Onion-2020-09-11-21-37-43](https://user-images.githubusercontent.com/32956424/92942227-85226500-f47b-11ea-8c6d-8c0241526bac.png)


## 3. Squil

Click vào icon Sguil ở Desktop 

![Security Onion-2020-09-11-22-42-40](https://user-images.githubusercontent.com/32956424/92945893-20b5d480-f480-11ea-9688-214708405d3d.png)

Đăng nhập với username và password đã tạo trước đó, giao diện chính của Sguil sẽ hiện ra

![Security Onion-2020-09-11-22-44-18](https://user-images.githubusercontent.com/32956424/92946052-55c22700-f480-11ea-8e45-6b0372317996.png)

Sguil có khá nhiều usecase, trong đó tiêu biểu nhất là **Pcap Forensics**

### Pcap Forensics

Dùng lệnh nmap ở 1 máy khác, tiến hành quét VM Security Onion

![Security Onion-2020-09-12-01-45-52](https://user-images.githubusercontent.com/32956424/92961622-bf9afa80-f499-11ea-8bbd-d0edc7d1cfb6.png)

Sguil lập tức sẽ phát hiện được Real Time Event thông qua các sensor

Click chuột phải vào 1 alert, chọn Wireshark

![Security Onion-2020-09-12-01-51-38](https://user-images.githubusercontent.com/32956424/92962073-94fd7180-f49a-11ea-9642-f6c72bc2668d.png)

Màn hình wireshark sẽ hiện lên cùng với thông tin của alert đã chọn

![Security Onion-2020-09-12-01-53-09](https://user-images.githubusercontent.com/32956424/92962173-c8d89700-f49a-11ea-88e8-295b4ab6f403.png)

Một ví dụ khác là download những file pcap mẫu có sẵn từ https://www.malware-traffic-analysis.net/ để tiến hành phân tích

Sử dụng lệnh tcpreplay 

![Security Onion-2020-09-12-01-59-46](https://user-images.githubusercontent.com/32956424/92963048-0be73a00-f49c-11ea-8c6b-d11edc5112da.png)

Đợi quá trình hoàn tất 

![Security Onion-2020-09-12-02-00-35](https://user-images.githubusercontent.com/32956424/92963109-23bebe00-f49c-11ea-9a35-3c91e73dd309.png)

Login vào squil, sẽ thấy rất nhiều alert từ file pcap trước đó

![Security Onion-2020-09-12-02-01-03](https://user-images.githubusercontent.com/32956424/92963156-389b5180-f49c-11ea-9e43-e039fc4f731c.png)



## 4. Squert
**Squert** là 1 ứng dụng web dùng để truy vấn và xem event data lưu trong database của **Sguil**
Click vào icon Squert ở Desktop, giao diện web của Squert sẽ xuất hiện, đăng nhập với username và password

![Security Onion-2020-09-12-02-12-52](https://user-images.githubusercontent.com/32956424/92964265-038ffe80-f49e-11ea-8fdc-36013b1d58c0.png)

Sau khi login, giao diện chính của Squert sẽ hiện ra

![Security Onion-2020-09-12-02-13-05](https://user-images.githubusercontent.com/32956424/92964306-1571a180-f49e-11ea-8533-1a30b48a751c.png)

Người dùng có thể lọc các **Event** theo địa chỉ IP bằng cách nhập địa chỉ IP muốn lọc vào ô **Filter**

![Security Onion-2020-09-12-02-13-29](https://user-images.githubusercontent.com/32956424/92964386-32a67000-f49e-11ea-818d-3f3b5132ab25.png)

Sau khi lọc Event, người dùng có thể xem chi tiết Event đó

![Security Onion-2020-09-12-02-14-29](https://user-images.githubusercontent.com/32956424/92964422-3fc35f00-f49e-11ea-9668-2557e5093796.png)

