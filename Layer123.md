# Media Layer
## 1. Tầng mạng (Network layer)
### Mục đích và hoạt động

- Tầng mạng thi hành chức năng định tuyến, điều khiển lưu lượng dữ liệu, phân đoạn, hợp đoạn mạng (network segmentation/desegmentation) và kiểm soát lỗi (error control).

- Đáp ứng các yêu cầu dịch vụ từ tầng giao vận và đưa ra những yêu cầu dịch vụ đối với tầng liên kết dữ liệu.
- Phân phát, định tuyến các gói dữ liệu từ có độ dài đa dạng từ nguồn tới đích, qua một hay nhiều mạng máy tính trong khi vẫn duy trì chất lượng dịch vụ (quality of service) mà tầng giao vận yêu cầu.

### Hoạt động
![](https://raw.githubusercontent.com/MQAnh/Network/main/images/network%20layer.png )
- Quá trình đóng gói: Mỗi phân đoạn của lớp transport được chuyển đến lớp mạng để định địa chỉ mạng (địa chỉ logic) và định tuyến thông qua mạng internet. Ở lớp Mạng, chúng ta gọi dữ liệu (lúc này bao gồm tiêu đề truyền tải và thông tin lớp trên) là một gói. Lớp Mạng thêm IP vào đầu gói tin và sau đó gửi nó đến lớp Datalink.
- Quá trình mở gói: Gói được chuyển từ lớp Data link đến lớp mạng. Tại lớp Mạng, địa chỉ IP được kiểm tra và nếu nó khớp (với địa chỉ IP riêng của máy) thì IP sẽ bị loại bỏ khỏi gói và phần còn lại được chuyển đến lớp trên là tầng giao vận.

### Giao thức

#### __IP__

_Là một giao thức hướng dữ liệu được sử dụng bởi các máy chủ nguồn và đích để truyền dữ liệu trong một liên mạng chuyển mạch gói._

__Đặc điểm__
- Là 1 trong những giao thức quan trọng nhất của bộ giao thức TPC/IP.
- Là giao thức hướng không liên kết (connectionless): dữ liệu của IP được truyền đi ngay lập tức nếu có thể (best effort), không có bất kì cơ chế thiết lập kết nối , không có cơ chế báo nhận hay điều khiển luồng nào được sử dụng với IP, các gói tin IP cũng không được đánh số thứ tự khi trao đổi trên mạng…
- Mỗi gói tin IP được xử lý một cách hoàn toàn độc lập với các gói tin IP khác .
- Giao thức IP sử dụng cơ chế định địa chỉ theo kiểu phân cấp, trong đó phần NetworkId của địa chỉ giống như tên của một con đường và phần hostId của địa chỉ sẽ là số nhà của một căn nhà trên con đường ấy.
- Không có cơ chế khôi phục lại gói tin bị mất trên đường truyền. Việc này được giao lại cho các giao thức tầng trên để đảm bảo độ tin cậy (TCP).
  
_Mỗi máy tính khi kết nối Internet đều có 1 địa chỉ IP duy nhất. Mục đích là để định danh duy nhất cho 1 máy tính bất kỳ trên liên mạng._

__Cấu trúc địa chỉ IP__

_Địa chỉ IP gồm 32 bit nhị phân , chia thành 4 cụm 8 bit (gọi là các octet). Các octet được biểu diễn dưới dạng thập phân và được ngăn cách bằng các dấu chấm._

Địa chỉ IP được chia thành 2 phần : 
- NetworkID (phần địa chỉ mạng)
- HostID (phần địa chỉ máy trạm)
  
![](https://raw.githubusercontent.com/MQAnh/Network/main/images/3c9aa2d6-8ecf-48f6-a811-ba31923abd64.jpg)

__IPv4__

_IPv4 được biểu hiện bằng chuỗi số có 4 phần phân cách bằng 4 dấu chấm. Mỗi phần được gọi là octet và có 8 bit dữ liệu._

__Các lớp địa chỉ IPv4__

![](https://raw.githubusercontent.com/MQAnh/Network/main/images/img/IPv4.png)
Lớp A: 
- Địa chỉ lớp A sử dụng một octet đầu làm phần mạng, ba octet sau làm phần host.
- Bit đầu của một địa chỉ lớp A luôn được giữ là 0.

Lớp B:
- Địa chỉ lớp B sử dụng hai octet đầu làm phần mạng, hai octet sau làm phần host.
- Hai bit đầu của một địa chỉ lớp B luôn được giữ là 1 0.

Lớp C:
- Địa chỉ lớp C sử dụng ba octet đầu làm phần mạng, một octet sau làm phần host.
- Ba bit đầu của một địa chỉ lớp C luôn được giữ là 1 1 0.

Lớp D:
- Gồm các địa chỉ thuộc dải: 224.0.0.0 - 239.255.255.255
•	Được sử dụng làm địa chỉ multicast.

Lớp E:
- Từ 240.0.0.0 trở đi.
- Được dùng cho mục đích dự phòng.

__Hạn chế của IPv4__

- Tài nguyên địa chỉ IPv4 đã gần cạn kiệt
-  Cấu trúc định tuyến không hiệu quả
-  Địa chỉ IPv4 không có cách thức bảo mật nào đi kèm, không cung cấp phương tiện hỗ trợ mã hóa dữ liệu.

Cấu trúc IP Header Version 4
![](https://raw.githubusercontent.com/MQAnh/Network/main/images/img/ipv4%20header.PNG)
__IPv6__

_IPv6 (Internet Protocol version 6) là giao thức mạng mới nhất hiện nay có chức năng truyền dữ liệu trong các gói từ một nguồn đến đích qua các mạng khác nhau. IPv6 được đánh giá là một phiên bản cải tiến của IPv4. Nó hỗ trợ một số lượng node lớn hơn đáng kể so với IPv4._

IPv6 cung cấp một số cải tiến so với IPv4:
- Không gian địa chỉ lớn hơn: Tăng từ 32bit lên 128bit.
- Header của giao thức được cải tiến: Cải thiện hiệu suất chuyển tiếp gói tin.
- Tự động cấu hình không trạng thái: Để các nút tự xác định địa chỉ của riêng mình.
- Multicast: Tăng cường sử dụng truyền thông một chiều hiệu quả.
- Bảo mật lớp mạng: Mã hóa và xác thực truyền thông.
- Khả năng QoS (Quality of service): Đánh dấu QoS cho các gói tin và dán nhãn để giúp xác định những traffic cần được ưu tiên.
- Anycast: Dịch vụ dự phòng sử dụng những địa chỉ không có cấu trúc đặc biệt.
- Tính di động: Dễ dàng hơn khi xử lý với thiết bị di động hay chuyển vùng.
  
Cấu trúc IP Header Version 6

![](https://raw.githubusercontent.com/MQAnh/Network/main/images/ip.gif )

__ARP__

Giao thức mạng được dùng để tìm ra địa chỉ phần cứng (địa chỉ MAC) của thiết bị từ một địa chỉ IP nguồn

#### Cơ chế hoạt động của ARP
Thiết bị nguồn trong một mạng IP có nhu cầu thực hiện gửi một gói tin IP.

ARP xác định được xem địa chỉ IP đích của gói tin có đang nằm cùng trong mạng nội bộ của mình hay không.
- Nếu đúng thì thiết bị sẽ thực hiện gửi trực tiếp gói tin đến thiết bị đích. 
- Nếu địa chỉ IP đích đang  nằm trên mạng khác, thì thiết bị sẽ gửi gói tin đến một trong các router nằm cùng 
ở trên mạng nội bộ để router này làm nhiệm vụ chuyển tiếp gói tin.

## 2. Tầng liên kết dữ liệu (Data – link layer)
Lớp liên kết dữ liệu là lớp thứ hai của Mô hình phân lớp OSI xử lý việc di chuyển dữ liệu vào và ra khỏi một liên kết vật lý trong mạng.

Xử lý các vấn đề xảy ra do lỗi truyền bit.

Đảm bảo dữ liệu lưu chuyển với tốc độ không quá tải các thiết bị gửi và nhận. Cho phép truyền dữ liệu đến Lớp 3, lớp mạng, nơi nó được định địa chỉ và định tuyến.

Data-link layer gồm 2 lớp con:
- Kiểm soát liên kết (LLC): giao tiếp giữa phần mềm của tầng trên và phần cứng của thiết bị tầng dưới. Tầng con LLC chủ yếu quan tâm đến: Ghép kênh (multiplexing) các giao thức được truyền qua tầng MAC (khi truyền) và phân kênh(demultiplexing) chúng (khi nhận).
- Kiểm soát truy cập (MAC): cung cấp các cơ chế đánh địa chỉ và điều khiển truy nhập kênh Tầng con MAC hoạt động với vai trò một giao diện giữa tầng con điều khiển liên kết lôgic LLC và tầng vật lý của mạng.
### Hoạt động:
![](https://raw.githubusercontent.com/MQAnh/Network/main/images/Datalink%20layer.png)
- Quá trình đóng gói:  Nhận các gói được gửi từ lớp mạng, đóng gói mỗi gói trong một khung.  Phần đầu khung chứa địa chỉ phần cứng (MAC) của máy tính nguồn và đích (máy chủ) và thông tin LLC xác định giao thức nào trong lớp ưu tiên (Lớp mạng) mà gói tin sẽ được chuyển khi nó đến đích của nó. Cuối khung được thêm trình tự kiểm tra khung để kiểm tra lỗi. Sau đó chuyển xuống lớp vật lý.
- Quá trình mở gói: Sau khi nhận khung được gửi từ lớp vật lý, lớp liên kết dữ liệu thực hiện kiểm tra lỗi. Nếu kết quả mà nó nhận được khớp với giá trị trình kiểm tra lỗi, thì nó giả định rằng khung đã được nhận mà không có bất kỳ lỗi nào. Tiếp đó, các thông tin được thêm bởi lớp Datalink được loại bỏ và chuyển phần còn lại lên lớp trên (lớp mạng).

### Giao thức
__HDLC (Điều khiển liên kết dữ liệu mức cao)__

Là giao thức truyền thông mục đích chung điểm-điểm hoạt động ở cấp liên kết dữ liệu. 
Cung cấp khả năng phục hồi lỗi trong trường hợp mất gói dữ liệu, lỗi chuỗi và các lỗi khác, do đó nó cung cấp liên lạc đáng tin cậy giữa máy phát và máy thu.
Ba loại trạm 
-  Trạm chính: Có trách nhiệm kiểm soát trao ñổi thông tin trên liên kết  Khung gửi bằng trạm chính gọi là lệnh 
-  Trạm phụ  Hoạt ñộng dưới sự kiểm soát của trạm chính  Khung gửi bằng trạm phụ gọi là trả lời.
-   Trạm hỗn hợp


## 1. Tầng vật lý (Physical layer)

Lớp vật lý trong mô hình OSI đóng vai trò tương tác với phần cứng thực tế và truyền tín hiệu. Lớp vật lý là lớp duy nhất của mô hình mạng OSI thực sự xử lý kết nối vật lý của hai thiết bị khác nhau. Lớp này xác định thiết bị phần cứng, hệ thống cáp, hệ thống dây điện, tần số, xung được sử dụng để biểu diễn, biến đổi tín hiệu nhị phân thành tín hiệu vật lý và ngược lại.

Hoạt động:
#### _Khi dữ liệu được gửi qua phương tiện vật lý, trước tiên nó cần được chuyển đổi thành tín hiệu điện từ. Dữ liệu tự nó có thể là tương tự như giọng nói của con người hoặc kỹ thuật số như tệp trên đĩa. Cả dữ liệu tương tự và kỹ thuật số đều có thể được biểu diễn dưới dạng tín hiệu kỹ thuật số hoặc tương tự._

![](https://raw.githubusercontent.com/MQAnh/Network/main/images/tang-vat-y.png)

Quá trình đóng gói: 

Lớp liên kết dữ liệu chuyển giao các khung cho lớp vật lý. Lớp vật lý chuyển đổi chúng thành các xung điện, đại diện cho dữ liệu nhị phân. Dữ liệu nhị phân sau đó được gửi qua phương tiện có dây hoặc không dây.

Quá trình mở gói: 

Lớp vật lý chuyển tín hiệu vật lý thành dữ liệu nhị phân và gửi lên lớp trên.

__Các loại liên kết vật lý:__
- Kết nối có dây:
Các thiết bị được kết nối trực tiếp bằng dây hoặc dây cáp, thông tin được gửi thông qua đó.
Vd: UTP, STP, cáp đồng trục và cáp quang.  
- Kết nối không dây:
Các thiết bị không được kết nối trực tiếp. Thông tin trao đổi thông qua song vô tuyến.
VD: wifi, Bluetooth,….
 
__Giao thức__

Ethernet là một loạt các công nghệ mạng và hệ thống được sử dụng trong các mạng cục bộ (LAN), nơi các máy tính được kết nối trong một không gian vật lý chính.

Các hệ thống sử dụng giao tiếp Ethernet chia luồng dữ liệu thành các gói, được gọi là các khung. Khung bao gồm thông tin địa chỉ nguồn và đích cũng như các cơ chế được sử dụng để phát hiện lỗi trong dữ liệu được truyền và yêu cầu truyền lại.

Ethernet có dây

![](https://raw.githubusercontent.com/MQAnh/Network/main/images/ethernet-co-day.jpg)

Ethernet không dây 

![](https://raw.githubusercontent.com/MQAnh/Network/main/images/ethernet-khong-day.jpg)

 