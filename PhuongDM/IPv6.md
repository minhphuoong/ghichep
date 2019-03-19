# Tìm hiểu IPv6 #

----------
## I. Thông tin về hiện trạng tài nguyên toàn cầu (IPv4, IPv6). ##

### 1. Hạn chế của IPv4 ###
#### 1.1 Sự cạn kiệt IPv4 ####
- Không gian địa chỉ IPv4 đã được sử dụng > 60%.
- Những công nghệ góp phần giảm nhu cầu địa chỉ IP như NAT (công nghệ biên dịch để có thể sử dụng địa chỉ IP private), DHCP (cấp địa chỉ tạm thời) được sử dụng rộng rãi.
-  Internet phát triển tại những khu vực dân cư đông đảo như Trung Quốc, Ấn Độ.
-  Những dạng dịch vụ mới đòi hỏi không gian địa chỉ IP cố định (tỉ lệ sử dụng địa chỉ/khách hàng là 1:1) và kết nối dạng đầu cuối – đầu cuối: dịch vụ DSL, cung cấp dịch vụ Internet qua đường cáp truyền hình, việc phát triển các mạng giáo dục, game trực tuyến, thiết bị di động tham gia vào mạng Internet, truyền tải thoại, audio, video trên mạng…

	
#### 1.2 Hạn chế về công nghệ và nhược điểm của IPv4 ####
- Cấu trúc định tuyến không hiệu quả: Địa chỉ IPv4 có cấu trúc định tuyến vừa phân cấp, vừa không phân cấp. Mỗi router phải duy trì bảng thông tin định tuyến lớn, đòi hỏi router phải có dung lượng bộ nhớ lớn. IPv4 cũng yêu cầu router phải can thiệp xử lý nhiều đối với gói tin IPv4, ví dụ thực hiện phân mảnh, điều này tiêu tốn CPU của router và ảnh hưởng đến hiệu quả xử lý (gây trễ, hỏng gói tin).

- Hạn chế về tính bảo mật và kết nối đầu cuối – đầu cuối: IPv4 không cung cấp phương tiện hỗ trợ mã hóa dữ liệu. Nếu áp dụng IPSec là một phương thức bảo mật phổ biến tại tầng IP, mô hình bảo mật chủ yếu là bảo mật lưu lượng giữa các mạng, việc bảo mật lưu lượng đầu cuối – đầu cuối được sử dụng rất hạn chế.

Để giảm nhu cầu tiêu dùng địa chỉ, hoạt động mạng IPv4 sử dụng phổ biến công nghệ biên dịch NAT (Network Address Translator). Trong đó, máy chủ biên dịch địa chỉ (NAT) can thiệp vào gói tin truyền tải và thay thế trường địa chỉ để các máy tính gắn địa chỉ Private có thể kết nối vào mạng Internet.



Mô hình sử dụng NAT của địa chỉ IPv4 có nhiều nhược điểm:

- Không có kết nối điểm – điểm và gây trễ: Làm khó khăn và ảnh hưởng tới nhiều dạng dịch vụ (VPN, dịch vụ thời gian thực). Thậm chí đối với nhiều dạng dịch vụ cần xác thực port nguồn/ đích, sử dụng NAT là không thể được. Trong khi đó, các ứng dụng mới hiện nay, đặc biệt các ứng dụng client-server ngày càng đòi hỏi kết nối trực tiếp end-to-end.

- Việc gói tin không được giữ nguyên tình trạng từ nguồn tới đích, có những điểm trên đường truyền tải tại đó gói tin bị can thiệp, như vậy tồn tại những lỗ hổng về bảo mật.

Nguy cơ thiếu hụt không gian địa chỉ, cùng những hạn chế của IPv4 thúc đẩy sự đầu tư nghiên cứu một giao thức internet mới, khắc phục những hạn chế của giao thức IPv4 và đem lại những đặc tính mới cần thiết cho dịch vụ và cho hoạt động mạng thế hệ tiếp theo. Giao thức Internet IETF đã đưa ra, quyết định thúc đẩy thay thế cho IPv4 là IPv6 (Internet Protocol Version 6), giao thức Internet phiên bản 6, còn được gọi là giao thức IP thế hệ mới (IP Next Generation – IPng). Địa chỉ Internet phiên bản 6 có chiều dài gấp 4 lần chiều dài địa chỉ IPv4, bao gồm 128 bít.

### 2. Mục tiêu trong thiết kế IPv6 ###

- Không gian địa chỉ lớn hơn và dễ dàng quản lý không gian địa chỉ.

- Hỗ trợ kết nối đầu cuối-đầu cuối và loại bỏ hoàn toàn công nghệ NAT.

- Quản trị TCP/IP dễ dàng hơn: DHCP được sử dụng trong IPv4 nhằm giảm cấu hình thủ công TCP/IP cho host. IPv6 được thiết kế với khả năng tự động cấu hình, không cần sử dụng máy chủ DHCP, hỗ trợ hơn nữa trong việc giảm cấu hình thủ công.

- Cấu trúc định tuyến tốt hơn: Định tuyến IPv6 được thiết kế hoàn toàn phân cấp.

- Hỗ trợ tốt hơn Multicast: Multicast là một tùy chọn của địa chỉ IPv4, tuy nhiên khả năng hỗ trợ và tính phổ dụng chưa cao.

- Hỗ trợ bảo mật tốt hơn: IPv4 được thiết kế tại thời điểm chỉ có các mạng nhỏ, biết rõ nhau kết nối với nhau. Do vậy bảo mật chưa phải là một vấn đề được quan tâm. Song hiện nay, bảo mật mạng internet trở thành một vấn đề rất lớn, là mối quan tâm hàng đầu.

- Hỗ trợ tốt hơn cho di động: Thời điểm IPv4 được thiết kế, chưa tồn tại khái niệm về thiết bị IP di động. Trong thế hệ mạng mới, dạng thiết bị này ngày càng phát triển, đòi hỏi cấu trúc giao thức Internet có sự hỗ trợ tốt hơn.

## II.Cấu trúc thế hệ địa chỉ IPv6 ##

### 1. Lý thuyết về địa chỉ IPv6 ###

#### 1.1 Cách biểu diễn ####

- Địa chỉ IPv6 được viết dưới dạng hexa decimal. Địa chỉ IPV6 có độ dài 128 bít nhị phân. 128 bit nhị phân này được chia thành các nhóm 4 bit, chuyển đổi viết theo dạng số hexa decimal và nhóm 4 số hexa thành một nhóm phân cách bởi dấu “:” như trên. Kết quả, địa chỉ ipv6 được biểu diễn thành một dãy số gồm 8 nhóm số hexa cách nhau bằng dấu “:”, mỗi nhóm gồm 4 chữ số hexa.

#### 1.2 Các dạng địa chỉ IPv6 ####

- **Địa chỉ unicast:** Địa chỉ unicast xác định một giao diện duy nhất trong phạm vi tương ứng. Trong mô hình định tuyến, các gói tin có địa chỉ đích là địa chỉ unicast chỉ được gửi tới một giao diện duy nhất.  Địa chỉ unicast được sử dụng trong giao tiếp một – một.

- **Địa chỉ multicast:** Địa chỉ multicast định danh nhiều giao diện. Gói tin có địa chỉ đích là địa chỉ multicast sẽ được gửi tới tất cả các giao diện trong nhóm được gắn địa chỉ đó. Địa chỉ multicast được sử dụng trong giao tiếp một – nhiều.

Trong địa chỉ ipv6 không còn tồn tại khái niệm địa chỉ broadcast. Mọi chức năng của địa chỉ broadcast trong ipv4 được đảm nhiệm thay thế bởi địa chỉ ipv6 multicast. Ví dụ chức năng broadcast trong một subnet của địa chỉ ipv4 được đảm nhiệm bằng một loại địa chỉ ipv6 là địa chỉ multicast mọi node phạm vi link (link-local scope all-nodes multicast address FF02::1)

- **Địa chỉ anycast:** Địa chỉ anycast cũng xác định tập hợp nhiều giao diện. Tuy nhiên, trong mô hình định tuyến, gói tin có địa chỉ đích anycast chỉ được gửi tới một giao diện duy nhất trong tập hợp. Giao diện đó là giao diện “gần nhất” theo khái niệm của thủ tục định tuyến.

#### 1.3 Cấu trúc của địa chỉ IPv6 ####


#### 1.4 Những thay đổi so với địa chỉ IPv4 ####

### 2. Phân chia mạng con và cách phân hoạch vùng địa chỉ IPv6 ###

## III. Cách thức hoạt động của giao thức IPv6, so sánh với IPv4 ##




