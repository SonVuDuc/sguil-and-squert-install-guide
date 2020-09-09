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
**Lưu ý**: Trong trường hợp đăng nhập MySQL bằng root mà bị gặp lỗi **Access denied** thì do MySQL bắt buộc phải đăng nhập **root** kèm với password
  + Dùng lệnh sau để lấy password root ```sudo grep "temporary password" /var/log/mysqld.log ```
  + Đăng nhập root kèm password bằng lệnh ```mysql -u root -p mysql```
  + Đăng nhập được root thì thay đổi mật khẩu root 

Tạo 1 user mysql tên là **sguil**
```
mysql> GRANT ALL PRIVILEGES ON sguildb.*
           TO sguil@localhost IDENTIFIED BY 'sguilpasswd';
mysql> FLUSH PRIVILEGES;
```
Cd vào thư mục sguil đã git clone trước đó và chạy lệnh:
```
sudo mysql -u sguil -p -e "CREATE DATABASE sguildb"
```
Nhập password của user "**sguil**" đã tạo trước đó và dùng lệnh:
```
sudo mysql -u sguil -p -D sguildb < ./server/sql_scripts/create_sguildb.sql
```
### Cài đặt GUI Server

Tạo user Centos7 là **sguil**
```
sudo adduser sguil
sudo passwd sguil
sudo usermod -aG wheel sguil
```
1. Đăng nhập vào user sguil, tạo thư mục **/etc/sguild**. Cd vào thư mục **~/sguil/server**. Copy các file sguild.access, sguild.user, sguild.conf, sguild.queries và autocat.conf vào **/etc/sguild** 
2. Cài đặt Tcl và Tclx
```
cd ~
sudo yum install tcl
sudo yum install tclx
```
3. Cài đặt mysql-tcl
```
cd ~
wget https://download-ib01.fedoraproject.org/pub/epel/7/x86_64/Packages/t/tcl-mysqltcl-3.052-1.el7.x86_64.rpm
sudo rpm -ivh tcl-mysqltcl-3.052-1.el7.x86_64.rpm
sudo yum install tcl-mysqltcl
```
Để kiểm tra đuợc Tcl và các package đã được cài đặt hay chưa. Dùng lệnh **tclsh** để kiểm tra
![Screenshot from 2020-09-09 20-10-38](https://user-images.githubusercontent.com/32956424/92602691-ac8cfc80-f2d8-11ea-9604-0b801bb4afc2.png)
![Screenshot from 2020-09-09 06-14-06](https://user-images.githubusercontent.com/32956424/92603324-069faa80-f264-11ea-9113-794e9981543d.png)


### Cài đặt OpenSSL



