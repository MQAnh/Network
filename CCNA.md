# Router
_Định tuyến là quá trình thiết lập các tuyến đường mà các gói dữ liệu phải tuân theo để đến được đích. Trong quá trình này, một bảng định tuyến được tạo ra chứa thông tin liên quan đến các tuyến mà các gói dữ liệu đi theo._


- __Bộ định tuyến là gì?__ Bộ định tuyến là một phần cứng mạng chịu trách nhiệm chuyển tiếp các gói đến đích của chúng. Bộ định tuyến kết nối với hai hoặc nhiều mạng IP hoặc mạng con và chuyển các gói dữ liệu giữa chúng nếu cần. Bộ định tuyến được sử dụng trong gia đình và văn phòng để thiết lập kết nối mạng cục bộ. Các bộ định tuyến mạnh hơn hoạt động trên khắp Internet, giúp các gói dữ liệu đến được đích của chúng.
![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/router.jpg)
- __Bảng định tuyến__: là một bảng dữ liệu được lưu trữ trong bộ định tuyến hoặc máy chủ mạng liệt kê các tuyến đường đến các điểm đến mạng cụ thể và trong một số trường hợp, số liệu (khoảng cách) được liên kết với các tuyến đường đó . Bảng định tuyến chứa thông tin về cấu trúc liên kết của mạng ngay lập tức xung quanh nó

## Kỹ thuật định tuyến

### __Định tuyến tĩnh__ 
- Định tuyến tĩnh là một quá trình trong đó chúng ta phải thêm các tuyến đường trong bảng định tuyến một cách thủ công.

![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/static%20router.png)

#### Ưu điểm 

- Sử dụng ít băng thông hơn so với các phương thức định tuyến khác.
- Không tiêu tốn tài nguyên để tính toán và phân tích gói tin định tuyến.
- Dễ dàng triển khai, cấu hình.
- Bổ sung thêm tính bảo mật vì chỉ quản trị viên mới có thể cho phép định tuyến đến các mạng cụ thể. Không sử dụng băng thông giữa các bộ định tuyến.

#### Nhược điểm 
- Không có khả năng tự động cập nhật đường đi.
- Phải cấu hình thủ công khi mạng có sự thay đổi.
- Đối với một mạng lớn, quản trị viên sẽ là một công việc bận rộn khi thêm thủ công từng tuyến đường cho mạng trong bảng định tuyến trên mỗi bộ định tuyến. 
Quản trị viên nên có kiến thức tốt về cấu trúc liên kết. Nếu một quản trị viên mới đến, anh ta phải thêm từng tuyến theo cách thủ công, vì vậy anh ta phải có kiến thức rất tốt về các tuyến của cấu trúc liên kết.
#### Những trường hợp sử dụng định tuyến tĩnh
- Đường truyền có băng thông thấp.
Người quản trị cần kiểm soát các kết nối trong hệ thống.
- Hệ thống có các tuyến kết nối ít.
- Kết nối dùng định tuyến tĩnh là đường dự phòng cho đường kết nối dùng giao thức định tuyến động.

### __Định tuyến mặc định__
_Định tuyến mặc định có thể được coi là một loại định tuyến tĩnh đặc biệt_

- Đây là phương pháp mà bộ định tuyến được cấu hình để gửi tất cả các gói đến một bộ định tuyến duy nhất (bước tiếp theo). Gói tin thuộc về mạng nào không quan trọng, nó được chuyển tiếp đến bộ định tuyến được cấu hình để định tuyến mặc định. Nó thường được sử dụng với các bộ định tuyến sơ khai. Một bộ định tuyến sơ khai là một bộ định tuyến chỉ có một đường để kết nối với tất cả các mạng khác.

![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/csg49-01-default-route-single-exit-point.png)
- Các tuyến đường mặc định rất hữu ích khi xử lý mạng có một điểm thoát duy nhất. Nó cũng hữu ích khi một phần lớn các mạng đích phải được định tuyến đến một thiết bị next-hop duy nhất. Khi thêm một tuyến mặc định, bạn nên đảm bảo rằng thiết bị bước tiếp theo có thể định tuyến gói tin xa hơn, nếu không thiết bị bước tiếp theo sẽ bỏ gói tin. Một điểm khác cần nhớ là khi tồn tại một tuyến đường cụ thể hơn đến đích trong bảng định tuyến, thì bộ định tuyến sẽ sử dụng tuyến đường đó chứ không phải tuyến đường mặc định. Lần duy nhất bộ định tuyến sẽ sử dụng tuyến đường mặc định là khi một tuyến đường cụ thể không tồn tại.
### __Định tuyến động__
- Định tuyến động giúp điều chỉnh tự động các tuyến theo trạng thái hiện tại của tuyến trong bảng định tuyến. Định tuyến động sử dụng các giao thức để khám phá các điểm đến của mạng và các tuyến đường để tiếp cận nó. RIP và OSPF là những ví dụ tốt nhất về giao thức định tuyến động. Điều chỉnh tự động sẽ được thực hiện để đến đích mạng nếu một tuyến đường gặp sự cố.
- Một giao thức động có các tính năng sau: Các bộ định tuyến phải có cùng một giao thức động đang chạy để trao đổi các tuyến đường. Khi một bộ định tuyến tìm thấy sự thay đổi trong cấu trúc liên kết thì bộ định tuyến sẽ quảng cáo nó cho tất cả các bộ định tuyến khác.
#### Ưu điểm 
- Dễ dàng cấu hình. Hiệu quả hơn trong việc chọn tuyến đường tốt nhất đến một mạng từ xa đích và cũng để khám phá mạng từ xa. 
#### Nhược điểm 
- Tốn nhiều băng thông hơn để giao tiếp với các bộ định tuyến khác. Kém an toàn hơn so với định tuyến tĩnh.

## Các lớp giao thức định tuyến
### __Distance vector routing (Giao thức định tuyến theo vectơ khoảng cách)__

- Các giao thức này chọn đường dẫn tốt nhất trên cơ sở số bước nhảy để đến mạng đích theo hướng cụ thể. Giao thức động như RIP là một ví dụ về giao thức định tuyến véc tơ khoảng cách. Số lượng Hop là mỗi bộ định tuyến xuất hiện giữa mạng nguồn và mạng đích. Con đường có số bước nhảy ít nhất sẽ được chọn là con đường tốt nhất. 
- Giao thức định tuyến theo vectơ khoảng cách (DVR) yêu cầu một bộ định tuyến thông báo cho các hàng xóm của nó về các thay đổi cấu trúc liên kết theo định kỳ. Trong lịch sử được gọi là thuật toán định tuyến ARPANET cũ (hoặc được gọi là thuật toán Bellman-Ford).
#### Thuật toán vectơ khoảng cách 
- Một bộ định tuyến truyền vectơ khoảng cách của nó tới từng người hàng xóm của nó trong một gói định tuyến.
![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/DVP1.jpg)

- Mỗi bộ định tuyến nhận và lưu vectơ khoảng cách nhận được gần đây nhất từ mỗi hàng xóm của nó. 
![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/dvp2.jpg)

- Một bộ định tuyến tính toán lại vectơ khoảng cách của nó khi: 
- Nó nhận được một vectơ khoảng cách từ một người hàng xóm có chứa thông tin khác với trước đây. 


![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/dvp3.jpg)


![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/dvp4.jpg)


- Nó phát hiện ra rằng một liên kết đến một người hàng xóm đã bị hỏng.
#### Ưu điểm  
- Cấu hình và bảo trì đơn giản hơn định tuyến trạng thái liên kết. Các bản cập nhật của mạng được trao đổi định kỳ. Cập nhật (thông tin định tuyến) luôn được phát đi. Bảng định tuyến đầy đủ được gửi trong các bản cập nhật. Các bộ định tuyến luôn tin tưởng vào thông tin định tuyến nhận được từ các bộ định tuyến hàng xóm. Đây còn được gọi là định tuyến theo tin đồn. 
#### Nhược điểm của định tuyến theo vectơ khoảng cách 
- Hội tụ chậm hơn so với trạng thái liên kết. 
- Nó có nguy cơ từ vấn đề đếm đến vô cùng. 
- Nó tạo ra nhiều lưu lượng hơn trạng thái liên kết vì sự thay đổi số bước nhảy phải được truyền tới tất cả các bộ định tuyến và được xử lý trên mỗi bộ định tuyến. 
- Cập nhật số lượng Hop diễn ra theo định kỳ, ngay cả khi không có thay đổi nào trong cấu trúc liên kết mạng, do đó, các chương trình phát sóng lãng phí băng thông vẫn xảy ra. 
- Đối với các mạng lớn hơn, định tuyến theo vectơ khoảng cách dẫn đến các bảng định tuyến lớn hơn trạng thái liên kết vì mỗi bộ định tuyến phải biết về tất cả các bộ định tuyến khác. Điều này cũng có thể dẫn đến tắc nghẽn trên các liên kết WAN.

### __Link State Routing (Giao thức định tuyến trạng thái liên kết)__


Định tuyến trạng thái liên kết là họ giao thức định tuyến thứ hai. Định tuyến trạng thái liên kết sử dụng bộ định tuyến trạng thái liên kết để trao đổi thông báo cho phép mỗi bộ định tuyến tìm hiểu toàn bộ cấu trúc liên kết mạng. Dựa trên cấu trúc liên kết đã học này, mỗi bộ định tuyến sau đó có thể tính toán bảng định tuyến của nó bằng cách sử dụng tính toán đường dẫn ngắn nhất.

#### Giao thức định tuyến trạng thái liên kết duy trì ba bảng cụ thể:

Bảng láng giềng 
- Bảng chỉ chứa thông tin về các láng giềng của bộ định tuyến, tức là, kề cận kề đã được hình thành. 

Bảng cấu trúc liên kết
- Bảng này chứa thông tin về toàn bộ cấu trúc liên kết, tức là chứa cả các tuyến đường dự phòng và tốt nhất đến mạng được quảng cáo cụ thể.


Bảng định tuyến
- Bảng này chứa tất cả các tuyến đường tốt nhất đến mạng được quảng cáo. 


#### Ưu điểm 
- Vì nó duy trì các bảng riêng biệt cho cả tuyến đường tốt nhất và các tuyến đường dự phòng (toàn bộ cấu trúc liên kết) nên nó có nhiều kiến thức về mạng liên mạng hơn bất kỳ giao thức định tuyến véc tơ khoảng cách nào khác. Khái niệm về các bản cập nhật được kích hoạt được sử dụng do đó không còn tiêu thụ băng thông không cần thiết như trong giao thức định tuyến véc tơ khoảng cách. Cập nhật từng phần được kích hoạt khi có thay đổi cấu trúc liên kết, không phải cập nhật đầy đủ như giao thức định tuyến vectơ khoảng cách nơi toàn bộ bảng định tuyến được trao đổi.

#### Các giao thức Link State so với các giao thức Khoảng cách Vector có: 
-	Nó đòi hỏi một lượng lớn bộ nhớ. 
-	Tính toán đường đi ngắn nhất yêu cầu nhiều vòng kết nối CPU. 
-	Nếu một mạng sử dụng ít băng thông; nó nhanh chóng phản ứng với các thay đổi về cấu trúc liên kết Tất cả các mục trong cơ sở dữ liệu phải được gửi đến các hàng xóm để tạo thành các gói trạng thái liên kết. 
- Tất cả các hàng xóm phải được tin cậy trong cấu trúc liên kết. Cơ chế xác thực có thể được sử dụng để tránh sự cố và sự cố không mong muốn.

------------------------
# Transport layer
_Là một lớp end-to-end được sử dụng để gửi thông điệp đến máy chủ._

- Nó được gọi là lớp end-to-end vì nó cung cấp kết nối điểm-điểm thay vì hop-to-hop, giữa máy chủ nguồn và máy chủ đích để cung cấp các dịch vụ một cách đáng tin cậy. 
- Đơn vị đóng gói dữ liệu trong Lớp truyền tải là một phân đoạn. 
- Các giao thức tiêu chuẩn được sử dụng bởi Lớp truyền tải để nâng cao chức năng của nó là TCP (Giao thức điều khiển truyền tải), UDP (Giao thức sơ đồ người dùng), DCCP (Giao thức kiểm soát tắc nghẽn dữ liệu), v.v. 

## Port
_Trong mạng máy tính, một cổng là một điểm cuối giao tiếp._

- Một cổng được xác định cho mỗi giao thức truyền tải và tổ hợp địa chỉ bằng một số không dấu 16 bit, được gọi là số cổng. Các giao thức truyền tải phổ biến nhất sử dụng số cổng là Giao thức điều khiển truyền (TCP) và Giao thức sơ đồ người dùng (UDP). 
- Số cổng luôn được liên kết với địa chỉ IP của máy chủ lưu trữ và loại giao thức truyền tải được sử dụng để liên lạc. Nó hoàn thành địa chỉ mạng đích hoặc nguồn gốc của một tin nhắn. Số cổng cụ thể được dành riêng để xác định các dịch vụ cụ thể để một gói tin đến có thể dễ dàng chuyển tiếp đến một ứng dụng đang chạy. Vì mục đích này, số cổng thấp hơn 1024 xác định các dịch vụ được sử dụng phổ biến nhất trong lịch sử và được gọi là số cổng nổi tiếng. Các cổng được đánh số cao hơn có sẵn để sử dụng chung cho các ứng dụng và được gọi là cổng tạm thời.

![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/Screenshot%202021-10-03%20082810.png)

## Các trách nhiệm khác nhau của lớp truyền tải 

#### __Quy trình xử lý phân phối__ 
- Trong khi Liên kết dữ liệu Lớp yêu cầu địa chỉ MAC (địa chỉ 48 bit chứa bên trong Thẻ giao diện mạng của mọi máy chủ) của các máy chủ nguồn-đích để phân phối chính xác khung và Lớp mạng yêu cầu địa chỉ IP để định tuyến các gói phù hợp, theo cách tương tự Lớp truyền tải yêu cầu Số cổng để phân phối chính xác các phân đoạn dữ liệu đến đúng quy trình trong số nhiều quy trình đang chạy trên một máy chủ cụ thể. Số cổng là địa chỉ 16 bit được sử dụng để xác định duy nhất bất kỳ chương trình máy khách-máy chủ nào.
#### __Kết nối đầu cuối giữa các máy chủ__ 
- Lớp truyền tải cũng chịu trách nhiệm tạo Kết nối đầu cuối giữa các máy chủ mà nó chủ yếu sử dụng TCP và UDP. TCP là một giao thức định hướng kết nối, an toàn sử dụng giao thức bắt tay để thiết lập một kết nối mạnh mẽ giữa hai máy chủ. TCP đảm bảo cung cấp thông điệp một cách đáng tin cậy và được sử dụng trong các ứng dụng khác nhau. Mặt khác, UDP là một giao thức không trạng thái và không đáng tin cậy, đảm bảo phân phối với nỗ lực tốt nhất. Nó phù hợp cho các ứng dụng ít quan tâm đến luồng hoặc kiểm soát lỗi và yêu cầu gửi khối lượng lớn dữ liệu như hội nghị truyền hình. Nó thường được sử dụng trong các giao thức đa hướng. 
#### __Ghép kênh và phân kênh__ 
- Ghép kênh cho phép sử dụng đồng thời các ứng dụng khác nhau qua mạng đang chạy trên máy chủ. Lớp truyền tải cung cấp cơ chế này cho phép chúng tôi gửi các luồng gói từ các ứng dụng khác nhau đồng thời qua mạng. Lớp truyền tải chấp nhận các gói này từ các tiến trình khác nhau được phân biệt bằng số cổng của chúng và chuyển chúng đến lớp mạng sau khi thêm các tiêu đề thích hợp. Tương tự, cần phải phân kênh ở phía thu để lấy dữ liệu từ các quá trình khác nhau. Truyền tải nhận các phân đoạn dữ liệu từ lớp mạng và chuyển nó đến tiến trình thích hợp đang chạy trên máy của người nhận. 
#### __Kiểm soát tắc nghẽn__ 
- Tắc nghẽn là một tình huống trong đó quá nhiều nguồn trên mạng cố gắng gửi dữ liệu và bộ đệm của bộ định tuyến bắt đầu tràn do việc mất gói xảy ra. Kết quả là việc truyền lại các gói tin từ các nguồn làm tăng thêm tắc nghẽn. Trong tình huống này, tầng Giao thông cung cấp Kiểm soát tắc nghẽn theo những cách khác nhau. Nó sử dụng kiểm soát tắc nghẽn vòng mở để ngăn chặn tắc nghẽn và kiểm soát tắc nghẽn vòng kín để loại bỏ tắc nghẽn trong mạng khi nó xảy ra. TCP cung cấp AIMD- phụ gia tăng giảm nhân, kỹ thuật thùng rò rỉ để kiểm soát tắc nghẽn. 
#### __Tính toàn vẹn dữ liệu và sửa lỗi__ 
- Lớp truyền tải kiểm tra lỗi trong các thông báo đến từ lớp ứng dụng bằng cách sử dụng mã phát hiện lỗi, tổng kiểm tra tính toán, nó kiểm tra xem dữ liệu nhận được có bị hỏng hay không và sử dụng các dịch vụ ACK và NACK để thông báo cho người gửi nếu dữ liệu đã đến hay chưa và kiểm tra tính toàn vẹn của dữ liệu. 
#### __Kiểm soát luồng__
- Lớp truyền tải cung cấp cơ chế điều khiển luồng giữa các lớp liền kề của mô hình TCP / IP. TCP cũng ngăn ngừa mất dữ liệu do người gửi nhanh và người nhận chậm bằng cách áp đặt một số kỹ thuật điều khiển luồng. Nó sử dụng phương pháp giao thức cửa sổ trượt được thực hiện bởi người nhận bằng cách gửi lại một cửa sổ cho người gửi thông báo kích thước dữ liệu mà nó có thể nhận được.

## Giao thức
### __TCP__
_Giao thức điều khiển truyền tải (TCP) là giao thức lớp truyền tải phổ biến nhất. Nó hoạt động cùng với IP và cung cấp dịch vụ truyền tải đáng tin cậy giữa các tiến trình sử dụng dịch vụ lớp mang do giao thức IP cung cấp_

- TCP là một giao thức đáng tin cậy, hướng kết nối và mọi giao thức hướng kết nối cần thiết lập một kết nối để dự trữ tài nguyên ở cả hai đầu giao tiếp.

- Được dùng để gửi email, chia sẻ tệp, downloading. 

#### __Three-way Handshake__

_Cách TCP truyền dữ liệu_

![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/three-way%20handshake.png)
- Bước 1 (SYN): Trong bước đầu tiên, máy khách muốn thiết lập kết nối với máy chủ, vì vậy nó sẽ gửi một phân đoạn với SYN (Số thứ tự đồng bộ hóa) thông báo cho máy chủ rằng ứng dụng khách có khả năng bắt đầu giao tiếp và nó bắt đầu phân đoạn với số thứ tự nào. với 
- Bước 2 (SYN + ACK): Máy chủ đáp ứng yêu cầu của khách hàng với bộ bit tín hiệu SYN-ACK. Xác nhận (ACK) biểu thị phản hồi của phân đoạn mà nó nhận được và SYN biểu thị bằng số thứ tự mà nó có khả năng bắt đầu các phân đoạn với 
- Bước 3 (ACK): Trong phần cuối cùng, khách hàng thừa nhận phản hồi của máy chủ và cả hai đều thiết lập kết nối đáng tin cậy với mà chúng sẽ bắt đầu truyền dữ liệu thực tế,
- Các bước 1, 2 thiết lập tham số kết nối (số thứ tự) cho một hướng và nó được thừa nhận.
- Các bước 2, 3 thiết lập tham số kết nối (số thứ tự) cho hướng khác và nó được thừa nhận. Với những điều này, một giao tiếp song công được thiết lập.
#### __TCP Segment structure__

-Tiêu đề của một phân đoạn TCP có thể nằm trong khoảng 20-60 byte.
![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/Picture1.png)
 __Các trường tiêu đề:__ 

- __Source Port Address__:
Trường 16 bit chứa địa chỉ cổng của ứng dụng đang gửi phân đoạn dữ liệu. 
- __Destination Port Address__: 
trường 16 bit chứa địa chỉ cổng của ứng dụng trong máy chủ đang nhận phân đoạn dữ liệu. 
- __Sequence Number__: 
Trường 32 bit chứa số thứ tự, tức là số byte của byte đầu tiên được gửi trong phân đoạn cụ thể đó. Nó được sử dụng để tập hợp lại thông điệp ở đầu nhận nếu các phân đoạn được nhận không theo thứ tự. 
- __Acknownledgement Number__:
Trường 32 bit chứa số xác nhận, tức là số byte mà người nhận mong đợi nhận được tiếp theo. Nó là một xác nhận cho các byte trước đó được nhận thành công. 
- __Độ dài tiêu đề (HLEN)__: 
Đây là trường 4 bit cho biết độ dài của tiêu đề TCP theo số từ 4 byte trong tiêu đề, tức là nếu tiêu đề là 20 byte (độ dài tối thiểu của tiêu đề TCP), thì điều này trường sẽ giữ 5 (vì 5 x 4 = 20) và độ dài tối đa: 60 byte, sau đó nó sẽ giữ giá trị 15 (vì 15 x 4 = 60). Do đó, giá trị của trường này luôn nằm trong khoảng từ 5 đến 15. 
- __Cờ điều khiển__:
Đây là 6 bit điều khiển 1-bit điều khiển thiết lập kết nối, kết thúc kết nối, hủy kết nối, điều khiển luồng, chế độ truyền, v.v. Chức năng của chúng là:
- - URG: Con trỏ khẩn cấp là hợp lệ 
- - ACK: Số xác nhận hợp lệ (được sử dụng trong trường hợp báo nhận tích lũy) 
- - PSH: Yêu cầu đẩy 
- - RST: Đặt lại kết nối 
- - SYN: Đồng bộ số thứ tự 
- - FIN: Ngắt kết nối 

- __Kích thước cửa sổ__:
Trường này cho biết kích thước cửa sổ gửi TCP tính bằng byte. 

- __Checksum__ 
Trường này giữ tổng kiểm tra để kiểm soát lỗi. Nó là bắt buộc trong TCP trái ngược với UDP. 

- __Con trỏ khẩn cấp__: 
Trường này (chỉ hợp lệ nếu cờ điều khiển URG được đặt) được sử dụng để trỏ đến dữ liệu được yêu cầu khẩn cấp cần đạt được quy trình nhận sớm nhất. Giá trị của trường này được thêm vào số thứ tự để lấy số byte của byte khẩn cấp cuối cùng.

### __UDP__
_Giao thức Dữ liệu Người dùng (UDP) là một giao thức Lớp truyền tải._

- UDP là một phần của bộ Giao thức Internet, được gọi là bộ UDP / IP. - Không giống như TCP, nó là một giao thức không đáng tin cậy và không có kết nối. Vì vậy, không cần thiết lập kết nối trước khi truyền dữ liệu.
- UDP xuất hiện trong hình ảnh. Đối với các dịch vụ thời gian thực như chơi game trên máy tính, giao tiếp thoại hoặc video, hội nghị trực tiếp; chúng ta cần UDP. Vì cần có hiệu suất cao, UDP cho phép loại bỏ các gói thay vì xử lý các gói bị trễ. Không có lỗi kiểm tra trong UDP, vì vậy nó cũng tiết kiệm băng thông. Giao thức dữ liệu người dùng (UDP) hiệu quả hơn về cả độ trễ và băng thông.

### Tiêu đề UDP 

- Tiêu đề UDP là tiêu đề cố định và đơn giản 8 byte, trong khi đối với TCP, nó có thể thay đổi từ 20 byte đến 60 byte. 8 byte đầu tiên chứa tất cả thông tin tiêu đề cần thiết và phần còn lại bao gồm dữ liệu. Mỗi trường số cổng UDP dài 16 bit, do đó phạm vi cho các số cổng được xác định từ 0 đến 65535; cổng số 0 được dành riêng. Số cổng giúp phân biệt các yêu cầu hoặc quy trình khác nhau của người dùng.

![](https://github.com/MQAnh/Network/blob/main/imgs/Picture2.png)

- Cổng nguồn: Cổng nguồn là trường dài 2 Byte được sử dụng để xác định số cổng của nguồn. Cổng đích: Là trường dài 2 Byte, được sử dụng để xác định cổng của gói định mệnh. Độ dài: Độ dài là độ dài của UDP bao gồm tiêu đề và dữ liệu. Nó là trường 16-bit. 
- Checksum: Checksum là trường dài 2 Byte. Nó là phần bổ sung 16-bit của tổng phần bổ sung của tiêu đề UDP, tiêu đề giả của thông tin từ tiêu đề IP và dữ liệu, được đệm bằng 0 octet ở cuối (nếu cần) để tạo thành bội số của hai octet.


### Các ứng dụng của UDP: 

Được sử dụng cho giao tiếp đáp ứng yêu cầu đơn giản khi kích thước dữ liệu nhỏ hơn và do đó ít quan tâm hơn đến luồng và kiểm soát lỗi. 

Đây là giao thức thích hợp cho đa hướng vì UDP hỗ trợ chuyển mạch gói. 

UDP được sử dụng cho một số giao thức cập nhật định tuyến như RIP (Routing Information Protocol). 

Thường được sử dụng cho các ứng dụng thời gian thực không thể chịu được độ trễ không đồng đều giữa các phần của tin nhắn đã nhận. 

Các triển khai sau sử dụng UDP làm giao thức lớp truyền tải: 
- NTP (Giao thức thời gian mạng) 
- DNS (Dịch vụ tên miền) 
- BOOTP, DHCP. 
- NNP (Network News Protocol) 
- Trích dẫn giao thức ngày 
- TFTP, RTSP, RIP. 
Lớp ứng dụng có thể thực hiện một số tác vụ thông qua UDP- 
- Trace Route 
- Record Route 
- Con dấu thời gian 
- UDP lấy datagram từ Network Layer, đính kèm tiêu đề của nó và gửi cho người dùng. Vì vậy, nó hoạt động nhanh chóng. 
Trên thực tế UDP là giao thức null nếu bạn loại bỏ trường tổng kiểm tra. 
- Giảm yêu cầu tài nguyên máy tính.
Khi sử dụng Multicast hoặc Broadcast để truyền. 
- Việc truyền các gói thời gian thực, chủ yếu trong các ứng dụng đa phương tiện.

# Application Layer
_Là tầng gần nhất với người sử dụng, được dùng để trao đổi dữ liệu giữa chương trình chạy  trên máy nguồn và máy chủ đích_

## Giao thức
1. TELNET: Telnet là viết tắt của TELecomunications NETwork. Nó giúp mô phỏng thiết bị đầu cuối. Nó cho phép máy khách Telnet truy cập tài nguyên của máy chủ Telnet. Nó được sử dụng để quản lý các tập tin trên internet. Nó được sử dụng để thiết lập ban đầu các thiết bị như công tắc. Lệnh telnet là lệnh sử dụng giao thức Telnet để giao tiếp với một thiết bị hoặc hệ thống từ xa. Số cổng của telnet là 23.

2. FTP: FTP là viết tắt của giao thức truyền tệp. Đây là giao thức thực sự cho phép chúng ta truyền tệp, nó có thể tạo điều kiện thuận lợi cho việc này giữa bất kỳ máy nào sử dụng nó. Nhưng FTP không chỉ là một giao thức mà nó còn là một chương trình. Số cổng cho FTP là 20 cho dữ liệu và 21 cho điều khiển.

3. TFTP: Giao thức truyền tệp tầm thường (TFTP) là phiên bản gốc của FTP, nhưng đó là giao thức được lựa chọn nếu bạn biết chính xác mình muốn gì và tìm nó ở đâu. Đó là công nghệ truyền tệp giữa các thiết bị mạng và là phiên bản đơn giản hóa của FTP. Số cổng cho TFTP là 69.

4. NFS: Nó là viết tắt của hệ thống tệp mạng, cho phép các máy chủ từ xa gắn hệ thống tệp qua mạng và tương tác với các hệ thống tệp đó như thể chúng được gắn cục bộ. Điều này cho phép quản trị viên hệ thống hợp nhất tài nguyên vào các máy chủ tập trung trên mạng. Số cổng cho NFS là 2049.

5. SMTP: Nó là viết tắt của Simple Mail Transfer Protocol. Nó là một phần của giao thức TCP / IP. Sử dụng quy trình có tên "lưu trữ và chuyển tiếp", SMTP di chuyển email của bạn trên và trên các mạng. Nó hoạt động chặt chẽ với một thứ gọi là Tác nhân chuyển thư (MTA) để gửi thông tin liên lạc của bạn đến đúng máy tính và hộp thư đến. Số cổng cho SMTP là 25.

9. DNS: Nó là viết tắt của Domain Name System. Do đó, mỗi khi bạn sử dụng tên miền, dịch vụ DNS phải dịch tên đó thành địa chỉ IP tương ứng. Ví dụ: tên miền www.abc.com có thể dịch thành 198.105.232.4. Số cổng cho DNS là 53.

10. DHCP: Nó là viết tắt của Dynamic Host Configuration Protocol (DHCP), cung cấp địa chỉ IP cho các máy chủ. Có rất nhiều thông tin mà máy chủ DHCP có thể cung cấp cho máy chủ khi máy chủ đăng ký địa chỉ IP với máy chủ DHCP. Số cổng cho DHCP là 67, 68.
11.HTTP: là giao thức tập hợp các quy tắc để trao đổi văn bản, hình ảnh, âm thanh, video và các tệp phương tiện khác World wide web. Số cổng cho HTTP là 80, 8080.


## Mô hình Client-Sever
Mô hình client-server là một mô hình nổi tiếng trong mạng máy tính, được áp dụng rất rộng rãi và là mô hình của mọi trang web hiện có. 

![](https://raw.githubusercontent.com/MQAnh/Network/main/imgs/mo-hinh-client-sever.png)

Ý tưởng của mô hình này là máy con (đóng vài trò là máy khách) gửi một yêu cầu (request) để máy chủ (đóng vai trò người cung ứng dịch vụ), máy chủ sẽ xử lý và trả kết quả về cho máy khách.

Trong mô hình này, chương trình ứng dụng được chia thành 2 thành phần: Server và Client. Client hay còn gọi là máy khách, nó bao gồm máy tính và các thiết bị điện tử nói chung. Server hay còn gọi là máy chủ, là nơi cài đặt các chương trình dịch vụ và lưu trữ tài nguyên.

Việc yêu cầu của máy khách, đáp ứng, xử lý, và phản hồi của máy chủ tạo thành một dịch vụ. Dịch vụ này hoạt động trên nền web nên nó được gọi là dịch vụ web (hay web service).
Ngoài ra, việc giao tiếp giữa Client với Server phải dựa trên các giao thức chuẩn. Các giao thức chuẩn được sử dụng phổ biến nhất hiện nay là : giao thức TCP/IP, giao thức SNA của IBM, OSI, ISDN, X.25 hay giao thức LAN-to-LAN NetBIOS.

Dữ liệu và tài nguyên được tập trung lại và tăng tính toàn vẹn của các dữ liệu.
Sự linh động trong việc mở rộng được hệ thống mạng.
Không phụ thuộc vào cùng một nền tảng, chỉ cần chung một định dạng giao tiếp (protocol) là có thể hoạt động được.
Chỉ có điều nhược điểm của mô hình này là tính an toàn và bảo mật các thông tin trên mạng. Do phải trao đổi các dữ liệu giữa hai máy ở hai khu vực khác nhau nên dễ dàng xảy ra hiện tượng thông tin trên mạng bị mất bí mật và từ đó vai trò của quản trị mạng trở nên quan trọng lên rất nhiều.


## Mô hình peer – to – peer.
Mạng ngang hàng (P2P) được tạo khi hai hoặc nhiều PC được kết nối và chia sẻ tài nguyên mà không cần thông qua một máy chủ riêng biệt.

![](https://congnghe102.com/uploads/102tech/images/p2p_la_gi_mang_ngang_hang_p2p.png)

Một mục đích quan trọng của mạng đồng đẳng là trong mạng tất cả các máy tham gia đều đóng góp tài nguyên, bao gồm băng thông, lưu trữ, và khả năng tính toán. Do đó khi càng có nhiều máy tham gia mạng thì khả năng tổng thể của hệ thống mạng càng lớn. 

Ngược lại, trong cấu trúc máy chủ-máy khách, nếu số lượng máy chủ là cố định, thì khi số lượng máy khách tăng lên khả năng chuyển dữ liệu cho mỗi máy khách sẽ giảm xuống.
Tính chất phân tán của mạng đồng đẳng cũng giúp cho mạng hoạt động tốt khi một số máy gặp sự cố. Đối với cấu trúc tập trung, chỉ cần máy chủ gặp sự cố thì cả hệ thống sẽ ngưng trệ.


Do cấu trúc của nó, mạng P2P có thể mang lại nhiều lợi thế cho người dùng, bao gồm: 
- Chia sẻ tệp dễ dàng: Một mạng P2P tiên tiến có thể chia sẻ tệp nhanh chóng trên khoảng cách lớn. 
- Giảm chi phí: Không cần đầu tư vào một máy tính riêng cho một máy chủ khi thiết lập mạng P2P. 
- Khả năng thích ứng: Mạng P2P mở rộng để bao gồm các khách hàng mới một cách dễ dàng. Lợi ích này làm cho các mạng này linh hoạt hơn so với mạng máy khách-máy chủ. 
- Độ tin cậy: Không giống như mạng máy khách-máy chủ, có thể bị lỗi nếu máy chủ trung tâm gặp sự cố, mạng P2P có thể sẽ vẫn hoạt động ngay cả khi máy chủ trung tâm gặp sự cố. 
- Hiệu suất cao: Trong khi mạng máy khách-máy chủ hoạt động kém hiệu quả hơn khi có nhiều máy khách tham gia vào mạng, mạng P2P có thể cải thiện hiệu suất của nó khi có nhiều máy khách tham gia. Điều này là do mỗi máy khách trong mạng P2P cũng là một máy chủ đóng góp tài nguyên cho mạng. 
- Hiệu quả: Các mạng P2P mới nổi cho phép cộng tác giữa các thiết bị có các tài nguyên khác nhau có thể mang lại lợi ích cho toàn mạng.


















