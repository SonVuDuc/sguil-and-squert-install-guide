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

Git clone repo của sguil bằng lệnh:
```
git clone https://github.com/bammv/sguil.git
```

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
```   
mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'dbpasswd';
mysql> FLUSH PRIVILEGES;
```
Tạo 1 user mysql tên là "sguil"
```
mysql> GRANT ALL PRIVILEGES ON sguildb.*
           TO sguil@localhost IDENTIFIED BY 'sguilpasswd';
mysql> FLUSH PRIVILEGES;
```
Cd vào thư mục sguil đã git clone trước đó và chạy lệnh:
```
sudo mysql -u sguil -p -e "CREATE DATABASE sguildb"
```
Nhập password của user sguil đã tạo trước đó và dùng lệnh:
```
sudo mysql -u sguil -p -D sguildb < ./server/sql_scripts/create_sguildb.sql
```

