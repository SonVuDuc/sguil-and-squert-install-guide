# Sguil Install Guide

## 1. Yêu cầu 
  + VM Centos 7 với RAM 2GG và ổ cứng 150GB
  + MySQL server 5.7
  + Tcl 8.5
  + Tclx 8.4
  + TLS 1.6.7
  + mysql-tcl 3.052
  + Snort 2.2.9
## 2. Cài đặt
### Cài đặt MySQL và tạo cơ sở dữ liệu cho sguil
Install mysql-server:
```
sudo yum localinstall https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
sudo yum install mysql-server
```
Đăng nhập vào **root** của MySQL và thay đổi mật khẩu **root**
```
mysql -u root mysql
```
    
    mysql> UPDATE user SET Password=PASSWORD('dbpasswd')
           WHERE user='root';
    mysql> FLUSH PRIVILEGES;
