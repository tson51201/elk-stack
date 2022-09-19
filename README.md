# elk-stack
Hướng dẫn cài đặt và sử dụng elk-stack. 
Hệ điều hành sử dụng: CentOS 7
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
## Bước 1: 
