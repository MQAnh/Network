# Mạng máy tính là gì?
_Mạng máy tính là một nhóm các máy tính và thiết bị ngoại vi kết nối với nhau thông qua các phương tiện truyền dẫn để truyền dữ liệu cho nhau._
## Các thiết bị cơ bản của một hệ thống mạng
- **User đầu cuối**: máy tính cá nhân, các thiết bị dùng Internet, wifi phục vụ truyền tải dữ liệu cho người dùng.
- **Các đường link kết nối**: connector(cổng mạng), các thiết bị tiếp nhận dữ liệu trên máy tính người dùng chuyển dữ liệu thành các dạng tín hiệu có thể truyền trên đương truyền.
- **Những thiết bị tập trung**: Switch, hub, brigde tập trung dữ liệu từ các end users. Thực hiện chuyển mạch dữ liệu ở layer 2 ethernet.
- **Thiết bị định tuyến đường truyền**: Router thực hiện chức năng định tuyến cho các dữ liệu đã tập trung ở layer 2.
## Các loại mạng
**PAN (_Personal Area Network_)**:
- Là mạng kết nối các máy tính/ thiết bị trong phạm vi cá nhân.
- Tương đối linh hoạt, hiệu quả cao trong phạm vi mạng ngắn.
- Thiết lập dễ dàng, chi phí tương đối thấp, không yêu cầu cài đặt và bảo trì thường xuyên.
- Phạm vi phủ sóng mạng thấp.
- Giới hạn tốc độ dữ liệu tương đối thấp.

**LAN (_Local Area Network_)**:
- Là mạng máy tính nội bộ.
- Băng thông cao nhưng đường truyền ngắn.
- Chỉ cho phép người dùng trao đổi dữ liệu trong một nhóm tổ chức.

**MAN (_Metropolitan area network_)**:
- Là mạng đô thị, được kết nối từ nhiều mạng LAN với nhau thông qua dây cáp, các phương tiện truyền dẫn.
- Phạm vi kết nối là khu vực rộng như trong một thành phố.
- Đối tượng sử dụng là các tổ chức, doanh nghiệp có nhiều chi nhánh hoặc nhiều bộ phận kết nối với nhau.

**WAN (_Wide area network_)**:
+  Là mạng diện rộng, sự kết hợp giữa mạng LAN và WAN nối lại với nhau thông qua vệ tinh, cáp quang, ….
+ Dữ liệu được thiết kế để kết nối giữa các mạng đô thị giữa các khu vực địa lý cách xa nhau
+ Khả năng truyền tín hiệu kết nối rất rộng và không giới hạn và chi phí lắp đặt cao cùng cách thức quản trị mạng phức tạp.
+ Băng thông thấp.

# Mô hình tham chiếu
## **OSI (Open Systems Interconnection)**
_Là một thiết kế dựa vào nguyên lý tầng cấp, lý giải một cách trừu tượng kỹ thuật kết nối truyền thông giữa các máy tính và thiết kế giao thức mạng giữa chúng. Mô hình này được phát triển thành một phần trong kế hoạch Kết nối các hệ thống mở (Open Systems Interconnection) do ISO và IUT-T khởi xướng. Nó còn được gọi là Mô hình bảy tầng của OSI._

_Mô hình OSI sắp xếp một giao thức với chức năng của nó vào một hoặc một nhóm các lớp tương ứng. Mỗi một tầng cấp có một đặc tính là nó chỉ sử dụng chức năng của tầng dưới nó, đồng thời chỉ cho phép tầng trên sử dụng các chức năng của mình_

![OSI Model](https://vsudo.net/blog/wp-content/uploads/2020/03/mo-hinh-osi-800x639.jpg)
### **Các tầng cấp của mô hình OSI**
**Application layer**

Là tầng giao diện chính để người dùng tương tác với chương trình ứng dụng.

Cung cấp phương tiện cho người dùng truy cập các thông tin và dữ liệu trên mạng thông qua chương trình úng dụng


**Presentation layer**

Giải quyết các vấn đề liên quan đến các cú pháp và ngữ nghĩa của thông tin được truyền. Biểu diễn thông tin người sử dụng phù hợp với thông tin làm việc của mạng và ngược lại

Lớp thể hiện thực hiện các chức năng sau:
- Dịch các mã kí tự từ ASCII sang EBCDIC.
- Chuyển đổi dữ liệu.
- Nén dữ liệu để giảm lượng dữ liệu truyền trên mạng.
- Mã hoá và giải mã dữ liệu để đảm bảo sự bảo mật trên mạng.
 
**Session layer**

Thiết lập “các giao dịch” giữa các thực thể đầu cuối, quản lý và hết thúc các kết nối giữa các trình ứng dụng đại phương và trình ứng dụng từ xa.
Cung cấp một liên kết giữa 2 đầu cuối sử dụng dịch vụ phiên sao cho trao đổi dữ liệu một cách đồng bộ và khi kết thúc thì giải phóng liên kết


**Transport layer**

Là tầng cao nhất liên có liên quan đến các giao thức trao đổi dữ liệu giữa các hệ thống mở, kiểm soát việc truyền dữ liệu từ nút tới nút (End-to-End) .

Chia các gói tin lớn thành các gói tin nhỏ hơn trước khi gửi đi và đánh số các gói tin và đảm bảo chúng chuyển theo đúng thứ tự. Là tầng cuối cùng chịu trách nhiệm về mức độ an toàn trong truyền dữ liệu nên giao thức tầng vận chuyển phụ thuộc nhiều vào bản chất của tầng mạng 


**Network layer**

Định tuyến đường truyền. Tìm ra đường đi tối ưu nhất cho các gói tin nguồn tới đích có thể trong cùng một mạng hoặc khác mạng nha. Đường có thể được cố định, cũng có thể được định nghĩa khi bắt đầu hội thoại và có thể đường đi là động (Dynamic) có thể thay đổi với từng gói tin tùy theo trạng thái tải tức thời của mạng.

Một chức năng quan trọng khác của tầng mạng là chức năng điều khiển tắc nghẽn (Congestion Control). Nếu có quá nhiều gói tin cùng lưu chuyển trên cùng một đường thì có thể xảy ra tình trạng tắc nghẽn. Thực hiện chức năng giao tiếp giữa các mạng khi các gói tin đi từ mạng này sang mạng khác để tới đích. Địa chỉ IP được sử dụng phổ biến của tầng 3 (Logical address).
ROUTER là thiết bị đặc trưng hoạt động ở tầng này.


**Data-link layer**

Thực hiện thiết lập các liên kết, duy trì và hủy bỏ các liên kết dữ liệu. Kiểm soát lỗi và kiểm soát lưu lượng. 

Chia thông tin thành các khung thông tin (Frame), truyền các khung tuần tự và xử lý các thông điệp xác nhận (Acknowledgement Frame) từ bên máy thu gửi về. Tháo gỡ các khung thành chuỗi bit không cấu trúc chuyển xuống tầng vật lý và ngược lại. 

Đường truyền vật lý có thể gây ra lỗi, nên tầng liên kết dữ liệu phải giải quyết vấn đề kiểm soát lỗi, kiểm soát luồng, kiểm soát lưu lượng.
Sử dụng địa chỉ MAC (MAC address - Physical address) là địa chỉ đặc trung trên tầng này. 
SWITCH là thiết bị hoạt động ở tầng Data link.


**Physical layer**

Tầng vật lý xác định các chức năng, thủ tục về điện, cơ, quang để kích hoạt, duy trì và giải phóng các kết nối vật lý giữa các hệ thống mạng. 
Điều biến (modulation), biến đổi giữa dữ liệu số của các thiết bị người dùng và các tín hiệu tương ứng được truyền qua kênh truyền thông (tí hiệu vật lý).


***

## **TCP/IP**
_Tên gọi TCP/IP đến từ hai giao thức nền tảng của bộ giao thức là TCP (Tranmission Control Protocol) và IP (Internet Protocol)_

_Bộ giao thức TCP/IP có thể được coi là một tập hợp các tầng, mỗi tầng giải quyết một tập các vấn đề có liên quan đến việc truyền dữ liệu, và cung cấp cho các giao thức tầng cấp trên một dịch vụ được định nghĩa rõ ràng dựa trên việc sử dụng các dịch vụ của các tầng thấp hơn_

_Mô hình này cũng được sử dụng khá rộng rãi, độ phổ biến tương đương mô hình OSI, khác với mô hình OSI. TCP/IP tổ chức dữ liệu theo sơ đồ 4 tầng:_

![TCP/IP](https://giaiphapmangh3t.com/wp-content/uploads/2019/08/mo-hinh-mang-TCPIP.png)

**Application Layer**

Cung cấp giao tiếp đến người dùng.
Cung cấp các ứng dụng cho phép người dùng trao đổi dữ liệu ứng dụng thông qua các dịch vụ mạng khác nhau (như duyệt web, chat, gửi email,...).

Dữ liệu khi đến đây sẽ được định dạng theo kiểu byte nối byte, cùng với đó là các thông tin định tuyến giúp xác định đường đi đúng của một gói tin.

**Transport Layer**

Chịu trách nhiệm duy trì thông tin liên lạc end-to-end trên toàn mạng.

Xử lý vấn đề giao tiếp giữa các máy chủ trong cùng một mạng hoặc khác mạng được kết nối với nhau thông qua bộ định tuyến và cung cấp khả năng kiểm soát luồng, ghép kênh, độ tin cậy và sửa lỗi.

Trong tầng này còn bao gồm 2 giao thức cốt lõi là TCP và UDP. Trong đó, TCP đảm bảo chất lượng gói tin nhưng tiêu tốn thời gian khá lâu để kiểm tra đầy đủ thông tin từ thứ tự dữ liệu cho đến việc kiểm soát vấn đề tắc nghẽn lưu lượng dữ liệu. Trái với điều đó, UDP cho thấy tốc độ truyền tải nhanh hơn nhưng lại không đảm bảo được chất lượng dữ liệu được gửi đi.

**Internet Layer**

Được định nghĩa là một giao thức chịu trách nhiệm truyền tải dữ liệu một cách logic trong mạng.

Các phân đoạn dữ liệu sẽ được đóng gói (Packets) với kích thước mỗi gói phù hợp với mạng chuyển mạch mà nó dùng để truyền dữ liệu. 

Các gói tin được chèn thêm phần Header chứa thông tin của tầng mạng và tiếp tục được chuyển đến tầng tiếp theo. 

Các giao thức chính trong tầng là IP, TCMP và ARP.

**Network Acess**

Là tầng thấp nhất trong mô hình TCP/IP.

Chịu trách nhiệm truyền dữ liệu giữa các thiết bị trong cùng một mạng. Tại đây, các gói dữ liệu được đóng vào khung (Frame) và được định tuyến đi đến đích được chỉ định ban đầu.

Bao gồm: lớp vật lý, MAC (Media Access Control), Logical Link Control
- Lớp vật lý: Biến đổi dòng bit logic thành tín hiệu vật lý phù hợp với đường truyền vật lý và ngược lại.
- MAC (lớp điều khiển truy cập): 
Quy định việc đánh địa chỉ MAC cho các thiết bị mạng. Đưa ra cơ chế chia sẻ môi trường vật lý kết nối nhiều máy tính. Phỏng tạo kênh truyền song công (duplex channel), đa điểm (multipoint)
- LLC (lớp điều khiển kênh logic): 
Ghép kênh, điều khiển luồng. Cho phép các giao thức lớp trên được truyền trên cùng một cơ sở hạ tầng mạng vật lý.

# Protocol (giao thức) là gì?
_Tập hợp tất cả các quy tắc, quy ước để đảm bảo cho các máy tính trên mạng có thể giao tiếp với nhau gọi là giao thức._
## Một vài giao thức của từng lớp
## OSI
**Application layer** 

- **HTTP**: Giao thức truyền tải siêu văn bản 
- **FTP (File Transfer Protocol)**: Giao thức truyền tập tin
- **SMTP (Simple Mail Transfer Protocol)**: Giao thức dùng để phân phối thư điện tử.
- **Telnet**  là một giao thức mạng (network protocol) được dùng trên các kết nối với Internet hoặc các kết nối tại mạng máy tính cục bộ LAN.

**Presentation layer**
- **JPEG(Joint Photographic Experts Group)** là một trong những phương pháp nén ảnh hiệu quả.
- **MP3(MPEG-1 Audio Layer 3)** là một dạng file đã được nén bằng cách nén dữ liệu có tổn hao (lossy). Nó là một dạng âm thanh được mã hóa PCM pulse-code modulation và có dung lượng nhỏ hơn rất nhiều so với dữ liệu ban đầu do nó bỏ đi những phần âm thanh được cho là không quan trọng trong khoảng nghe được của con người.
- **MPEG (Moving Picture Experts Group)** là một nhóm các quy tắc hoạt động được thành lập bởi ISO và IEC để thiết lập các tiêu chuẩn cho việc truyền tải âm thanh và video.

**Session layer**
- **NFS (Network File System)** hệ thống giao thức chia sẻ file cho phép một người dùng trên một máy tính khách truy cập tới hệ thống file chia sẻ thông qua một mạng máy tính giống như truy cập trực tiếp trên ổ cứng.
- **X-Windown System** cung ứng một bộ các công cụ và giao thức cho phép người dùng xây dựng các giao diện đồ họa (GUI) trong hệ điều hành Unix, Tương tự Unix, và OpenVMS.

**Transport layer**
- **TCP (Transmisson Control Protocol)** đảm bảo chất lượng truyền gửi gói tin, nhưng tốn khá nhiều thời gian để kiểm tra đầy đủ thông tin từ thứ tự dữ liệu cho đến việc kiểm soát vấn đề tắc nghẽn lưu lượng dữ liệu.
- **UDP (User Datagram Protocol)** có tốc độ truyền tải nhanh hơn nhưng lại không đảm bảo được chất lượng dữ liệu được gửi đi (tức là nó không quan tâm dữ liệu có đến được đích hay không).
- **SPX (Sequenced Packet Exchange)** là một giao thức trình tự cho các gói mạng được sử dụng với Novell NetWare. SPX cung cấp các dịch vụ tầng truyền tải tương đương với TCP.

**Network layer**
- **IP (Internet Protocol)** là một giao thức hướng dữ liệu được sử dụng bởi các máy chủ nguồn và đích để truyền dữ liệu trong một liên mạng chuyển mạch gói.
- **ICMP (Internet Control Message Protocol)** là một giao thức được các thiết bị mạng như router dùng để gửi đi các thông báo lỗi chỉ ra một dịch vụ có tồn tại hay không, hoặc một địa chỉ host hay router có tồn tại hay không. ICMP cũng có thể được sử dụng để chuyển tiếp các thông điệp truy vấn
- **RIP (Routing Information Protocol)** là một giao thức định tuyến miền trong được sử dụng cho các hệ thống tự trị.

**Data-link & Physical layer (Network Acess - TCP/IP)**: 
- **FDDI (Fiber Distributed Data Interface - FDDI)** là một tiêu chuẩn để truyền dữ liệu trong mạng cục bộ. Nó sử dụng sợi quang làm môi trường vật lý cơ bản tiêu chuẩn của nó, mặc dù sau đó nó cũng được chỉ định sử dụng cáp đồng.
- **Chuẩn IEEE 802.11**  mô tả một giao tiếp "truyền qua không khí" (over-the-air) sử dụng sóng vô tuyến để truyền nhận tín hiệu giữa một thiết bị không dây và tổng đài hoặc điểm truy cập (access point), hoặc giữa 2 hay nhiều thiết bị không dây với nhau.
- **HDLC (High-Level Data Link Control)** là giao thức truyền thông mục đích chung điểm-điểm hoạt động ở cấp liên kết dữ liệu.  Nó cung cấp khả năng phục hồi lỗi trong trường hợp mất gói dữ liệu, lỗi chuỗi và các lỗi khác, do đó nó cung cấp liên lạc đáng tin cậy giữa máy phát và máy thu.
- **Ethernet** là một dạng công nghệ truyền thống dùng để kết nối các mạng LAN cục bộ, cho phép các thiết bị có thể giao tiếp với nhau thông qua một giao thức - một bộ quy tắc hoặc ngôn ngữ mạng chung. 
- **ARP (Address Resolution Protocol)** là một giao thức truyền thông được sử dụng để chuyển địa chỉ từ tầng mạng (Internet layer) sang tầng liên kết dữ liệu theo mô hình OSI

# Tương tác giữa các tầng, giữa 1 layer giữa 2 end devices
![](https://1.bp.blogspot.com/_mAJDMuyu_WI/SjflV44wkOI/AAAAAAAABmw/MstS1fm8QtA/s640/osipdusdu.png 'Tương tác giữa các tầng')
## Tương tác giữa các tầng
_Dữ liệu truyền qua các tầng gọi là đơn vị dữ liệu dịch vụ (Service Data Unit - SDU)_



- SDU là một đơn vị dữ liệu chưa được đóng gói nhận được từ tầng trên. 

- Tầng trên hiểu được cấu trúc dữ liệu trong SDU, tầng dưới thì không và coi SDU là **tải trọng** và sẽ đưa nó đến cùng một giao diện đích.

- Mỗi đơn vị dữ liệu mà lớp (N + 1) cung cấp cho lớp (N) bên dưới được đóng gói dưới dạng một lớp (N) SDU. SDU của lớp N là đơn vị dữ liệu giao thức (PDU) của lớp (N + 1) ở trên. SDU sau khi thêm Header (hoặc trailer) được đóng gói vào PDU của lớp và chuyển xuống lớp thấp hơn.

- SDU được gửi tuần tự từ lớp trên xuống lớp thấp hơn đến lớp thấp nhất mô hình.
- Nếu độ dài SDU lớn hơn độ dài quy định, có thể SDU ra nhiều gói nhỏ có độ dài quy định và thêm thông tin điều khiển vào mỗi gói.

## Tương tác giữa 1 layer giữa 2 end devices
_Cùng một tầng giữa 2 thiết bị tương tác với nhau qua đơn vị dữ liệu giao thức (Protocol Data Unit  - PDU)._

- PDU Là một đơn vị thông tin đơn lẻ được truyền giữa các thực thể ngang hàng của mạng máy tính.
- PDU bao gồm Header (phần thông tin quản lý gói tin của các lớp) và SDU. Các giao thức đặc trưng của mỗi lớp sẽ quy định cách đóng gói tin PDU. PDU chỉ định dữ liệu sẽ được gửi đến lớp giao thức ngang hàng ở đầu nhận
- Khi các gói tin PDU đi từ lớp Application xuống lớp Physical. PDU lớp trên sẽ được đóng gói thành SDU lớp dưới. Việc bổ sung thêm header (hoặc cả phần trailer ở lớp data link) một SDU để tạo thành một PDU và việc truyền PDU đó đến lớp thấp hơn tiếp theo dưới dạng SDU lặp lại cho đến khi đạt đến lớp thấp nhất và dữ liệu đi qua một số phương tiện dưới dạng tín hiệu vật lý.
- Tại đầu nhận quá trình mở gói sẽ bắt đầu một chiều ngược lại từ lớp Physical lên lớp Application, cứ mỗi khi lên 1 lớp header của PDU được các thực thể đồng lớp nhận dạng sau đó gỡ bỏ để trả lại SDU chứa gói tin dữ liệu PDU của lớp trên và đưa lên lớp trên. Đến lớp Application dữ liệu sẽ được mở gói hoàn toàn. 


Đơn vị dữ liệu (PDU) của gói tin trên các tầng:
- Application, Presentation, Session: Data
- Transport: Segment
- Network: Packet
- Data Link: Frame
- Physical: Bit

# Đóng gói 1 gói tin 
## OSI
![](https://cache.digistar.vn/wp-content/uploads/2016/11/ois-sent-300x202.jpg?x72252 'Đóng gói 1 gói tin')
- Ở tầng Application (tầng 7), người dùng tiến hành đưa thông tin cần gửi vào máy tính. Các thông tin này thường có dạng như: hình ảnh, văn bản,…
- Sau đó thông tin dữ liệu này được chuyển xuống tầng Presentation (tầng 6) để chuyển các dữ liệu thành một dạng chung để mã hóa dữ liệu và nén dữ liệu.
- Dữ liệu tiếp tục được chuyển xuống tầng Session (Tầng 5). Tầng này là tầng phiên có chức năng bổ sung các thông tin cần thiết cho phiên giao dịch (gửi- nhận) này. 
- Sau khi tầng Session thực hiện xong nhiệm vụ, nó sẽ tiếp tục chuyển dữ liệu này xuống tầng Transport (Tầng 4). Tại tầng này, dữ liệu được cắt ra thành nhiều Segment và cũng làm nhiệm vụ bổ sung thêm các thông tin về phương thức vận chuyển dữ liệu để đảm bảo tính bảo mật, tin cậy khi truyền trong mô hình mạng.
- Tiếp đó, dữ liệu sẽ được chuyển xuống tầng Network (Tầng 3). Ở tầng này, các segment lại tiếp tục được cắt ra thành nhiều gói Package khác nhau và bổ sung thông tin định tuyến. Tầng Network này chức năng chính của nó là định tuyến đường đi cho gói tin chứa dữ liệu.
- Dữ liệu tiếp tục được chuyển xuống tầng Data Link (tầng 2). Tại tầng này, mỗi Package sẽ được băm nhỏ ra thành nhiều Frame và bổ sung thêm các thông tin kiểm tra gói tin chứa dữ liệu để kiểm tra ở máy nhận.
- Cuối cùng, các Frame này khi chuyển xuống tầng Physical (Tầng 1) sẽ được chuyển thành một chuỗi các bit nhị phân (0 1….) và được đưa lên cũng như phá tín hiệu trên các phương tiện truyền dẫn (dây cáp đồng, cáp quang,…) để truyền dữ liệu đến máy nhận.
- Mỗi gói tin dữ liệu khi được đưa xuống các tầng thì được gắn các header của tầng đó, riêng ở tầng 2 (Data Link), gói tin được gắn thêm FCS.

## TCP/IP
**Application** 
- Là lớp gần nhất với người dùng, từ đây, dữ liệu, yêu cầu từ người dùng sẽ được sử dụng để tạo thành một khối Data lớn theo khuôn dạng nhất định.

**Transport** 
- Dữ liệu sẽ được chia nhỏ thành các khối dữ liệu có kích thước phù hợp, sau đó được đóng gói lại, một Header được thêm vào nhằm theo dõi luồng dữ liệu và tập hợp dữ liệu tại máy đích. Những gói tin nhỏ này gọi là các Segment.
- Có rất nhiều ứng dụng, dịch vụ chạy trên mỗi host, nên để chuyển chính xác dữ liệu cho các ứng dụng dịch vụ, lớp Transport gán cho mỗi application một định danh gọi là port number. Mọi ứng dụng muốn truy cập mạng đều được gán port number, port number này là độc nhất trên host đó. 
- Tùy theo ứng dụng khác nhau, yêu cầu độ tin cậy khác nhau, lớp Transport sử dụng giao thức TCP hay UDP cho phù hợp:
•	TCP: là giao thức tin cậy, đảm bảo cho tất vả dữ liệu đều được chuyển tới đích đúng và đủ.
•	UDP: là giao thức đơn giản, không cung cấp bất kỳ sự tin cậy nào.

**Internet**
- Tại đây, các Segment sẽ được gắn thêm một header gọi là IP Header, bao gồm hai thông tin chính là địa chỉ Source IP và Destination IP. Các gói tin bây giờ được gọi là Datagram.

**Network Acess**
- Để một gói tin có thể gửi tới đích, chúng ta cần thêm một loại địa chỉ nữa đó là địa chỉ MAC hay địa chỉ vật lý. Địa chỉ này là độc nhất cho mọi thiết bị. Một header lại được thêm vào Datagram, hai thông tin chính là Source MAC và Destination MAC. Các gói tin bây giờ được gọi là Frame.
- Sau khi xác định đầy đủ địa chỉ Source MAC và Destination MAC, các Frame bây giờ sẽ được đưa xuống lớp Physical, được mã hóa và chuyển đổi thành các tín hiệu vật lý thích hợp, để đưa lên đường truyền.


