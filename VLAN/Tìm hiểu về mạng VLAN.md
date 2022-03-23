# 1. Tổng quan về mạng VLAN
# 1.1 Giới thiệu 

![1](https://user-images.githubusercontent.com/87790053/159643559-3f8cacfa-44b5-47bc-9881-f0dec24ba322.png)

 - VLAN là viết tắt của Virtual Local Area Network hay còn gọi là mạng LAN ảo. Một VLAN được định nghĩa là một nhóm logic các thiết bị mạng và được thiết lập dựa trên các yếu tố như chức năng, bộ phận, ứng dụng… của công ty.
 - Việc đặt các thiết bị vào các VLAN khác nhau có các đặc điểm sau:

   + Cung cấp phân đoạn các nhóm thiết bị khác nhau trên cùng một switch.
   + nCung cấp tổ chức dễ quản lý hơn
   + Broadcast, multicast và unicast được tách biệt trong VLAN riêng lẻ
   + Mỗi VLAN sẽ có dải địa chỉ IP riêng
   + Miền quảng bá nhỏ hơn

# 1.2 Lợi ích của việc sử dụng VLAN
+ VLAN giúp tăng hiệu suất mạng LAN cỡ trung bình và lớn vì nó hạn chế bản tin quảng bá 
+ Tăng tính bảo mật 
+ Giảm chi phí : Một switch  có thể hỗ trợ nhiều nhóm hoặc VLANs khác nhau 
+ Hiệu năng tốt hơn 
+ Quán lí đơn giản hơn 

# 1.3 Phân loại VLAN

- Default VLAN : 

![2](https://user-images.githubusercontent.com/87790053/159647810-4bbab836-98fb-4deb-94fe-987166ca7b08.png)
- Default VLAN 
  - Default NAtive VLAN 
  - Default  Managemant VLAN 
  - Không thể xóa hoặc không thể đổi tên 

- Native VLAN 
  - Chỉ sử dụng cho liên kết trunk
  - Tất cả frame đều được gán nhãn 802.1Q trừ các frame trên Native Vlan
- Data VLAN :
  - Dành riêng cho lưu lượng truy cập của người dùng (email hoặc lướt web)
  - Vlan 1 là default data Vlan bởi vì tất cả các interface đều chỉ định tới với Vlan này
- Management VLAN
  - Được sử dụng cho những traffic VTY telet/ssh và không dùng với traffic end user.
  - Thông thường, Vlan này là SVI cho switch layer 2.

- Voice VLAN : 
![18](https://user-images.githubusercontent.com/87790053/159649891-2f4ed910-64e7-4566-9880-6bb538e0e694.png)

- Cần có 1 Vlan riêng vì Voice Traffic yêu cầu:
  - Băng thông đàm bảo
  - Ưu tiên QoS cao (Quaility of Service)
  - Khả năng tránh tắc nghẽn
  - Trễ ít hơn 150 ms từ nguồn đến đích
  - Toàn bộ mạng phải được thiết kế để hỗ trợ giọng nói

# 2. VLAN là một môi trường Multi Switched 

<img src="/VLAN/image_vlan/4.png">

- Địnhk nghĩa một VLAN trunks
  - Đường trunks là một liên kết  điểm - điểm giwuax hai thiết bị  mạng 
  - Các chức năng chính của Trunk cisco :
    - Cho phép nhiều hơn 1 VLAN 
    - Mở rộng VLAN trên toàn bộ mạng 
    - Thoe mặc định , hỗ trợ tất cả các VLAN 
    - Hỗ trợ 802.1Q trunking 

<img src="/VLAN/image_vlan/5.png">

  - Nếu không cấu hình VLAN , tất cả các thiết bị kết nối với switch sẽ nhật được tất cả các traffic unicast, multicast và brodcast

<img src="/VLAN/image_vlan/6.png">

  - Khi có VLAN , traffic unicast ,multicast and broardcast được giới hạn trong 1 VLAN . Nếu không có thiết bị Layer 3 để kết nối các VLAN với nhau , các thiết bị trong VLAN khác không thể giao tiếp .
- Định nghĩa VLAN với 1 tag 

<img src="/VLAN/image_vlan/7.png">

  - Header IEE 802.1Q có độ dài 4byte được tạo ra  
  -Khi tag được tạo ra , FSC phải được tính toàn lại 
  - Khi gửi tới điểm cuối tag này phải được xóa và FCS được tính toàn lại như lúc ban đầu 
  
| test | dis|
|:---- |:---|



# 3. Cấu hình VLAN
# 4. VLAN Trunk
# 5. Dynamic Trunking Protocol