# elk-stack
Hướng dẫn cài đặt và sử dụng elk-stack trên CentOS 7
# Giới thiệu
ELK Stack là tập hợp 3 phần mềm phối hợp với nhau phục vụ cho công việc logging. Chúng lần lượt là:  
- Elasticsearch(E): cơ sở dữ liệu để lưu trữ, tìm kiếm và query log.  
- Logstash(L): Tiếp nhận log từ nhiều nguồn, sau đó xử lý log và ghi dữ liệu vào Elasticsearch  
- Kibana(K): Cung cấp giao diện để quản lý, thống kê log  
- Tác nhân phụ Beats: thu thập nhiều loại dữ liệu khác nhau để chuyển tiếp vào ngăn xếp, ví dụ như filebeat thu thập log files, packetbeat dùng để phân tích lưu lượng mạng…  
Cơ chế hoạt động của ELK Stack có thể mô tả qua hình dưới:
![Cơ chế hoạt động ELK Stack](https://user-images.githubusercontent.com/112193377/191057122-3722be59-152a-47bf-bea6-c89e09da9a0e.png)
# Cài đặt ELK Stack
Phần này sẽ hướng dẫn cài ELK Stack phiên bản 7.
## Trước khi cài đặt: 
- Update hệ thống:
>sudo yum update -y
- Cài đặt Java 1.8.0 (Lưu ý rằng phiên bản ELK khác có thể sẽ tương thích với phiên bản Java khác):
>sudo yum install  java-1.8.0-openjdk-devel –y
- Tạo repo:
>echo '[elasticsearch-7.x] name=Elasticsearch repository for 7.x packages baseurl=https://artifacts.elastic.co/packages/7.x/yum gpgcheck=1 gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch enabled=1 autorefresh=1 type=rpm-md ' > /etc/yum.repos.d/elasticsearch.repo
- Sau khi hoàn thành các bước trên sử dụng lệnh
>yum install (component) -y
    
với (component) thay bằng tên thành phần cần cài đặt. Ở đây ta sẽ cài filebeat, metricbeat, packetbeat, logstash, elasticsearch, kibana.
