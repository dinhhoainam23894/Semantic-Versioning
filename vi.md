### Đặc tả Semantic Versioning (SemVer)
Những từ khóa như “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, và “OPTIONAL” trong tài liệu này đã được giải thích và mô tả trong RFC 2119.

1. Phần mềm sử dụng Semantic Versioning phải khai báo 1 API công khai. API này nên được khai báo ngay trong code của nó hoặc tồn tại chặt chẽ trong tài liệu. Tuy nhiên, cuối cùng, nó nên được tóm lược và bao quát.

2. Một số phiên bản thông thường phải tuân theo dạng X.Y.Z trong đó X, Y, và Z là các số không âm, và phải không bắt đầu bởi các số 0. X là phiên bản chính, Y là phiên bản nhỏ, và Z là phiên bản vá. Mỗi phẩn tử phải là các số tự tăng. Ví dụ: 1.9.0 -> 1.10.0 -> 1.11.0.

3. Khi 1 gói phiên bản được phát hành, nội dung của phiên bản đó không được phép chỉnh sửa. Mọi chỉnh sửa phải được phát hành ở 1 phiên bản mới.

4. Phiên bản lớn số 0 (0.y.z) là cho khởi tạo phát triển. Mọi thứ có thể thay đổi bất cứ lúc nào. Không nên API công khai sẽ ổn định. 

5. Phiên bản 1.0.0 định nghĩa 1 API công khai. Số phiên bản được tăng sau khi xuất bạn này của nó phụ thuộc vào API công khai này và nó thay đổi thế nào.

6. Phiên bản vá Z(x.y.z | x > 0) phải tăng chỉ sau khi 1 bản  sửa lỗi tương thích với cái hiện tại được giới thiệu. Một sửa lỗi được định nghĩa là 1 thay đổi bện trong mà sửa những hành vi không đúng.

7. Phiên bản nhỏ Y (x.Y.z | x > 0) phải được tăng, nếu có 1 chức năng mới nhưng vẫn tương thích được giới thiệu đến API công khai. Nó phải được tăng nếu bất kỳ chức năng APT công khai được đánh dấu yêu cầu. Nó có thể tăng nếu 1 chức năng hay cải tiển mới được giới thiệu bên trong code riêng tư. Nó cũng có thể bao gồm các thay đổi ở mức vá. Phiên bản vá phải được đặt lại về 0 khi 1 phiên bản nhỏ được tăng.

8. Phiên bản to X (X.y.z | X > 0) phải được tăng nếu bất kỳ thay đối tương thích được giới thiệu đến APT công khai. Nó có thể bao gồm các thay đổi mực nhỏ và vá. Phiên bản vá và nhỏ phải được đặt lại về 0 khi phiên bản lớn được tăng.

9. Phiên bản tiền phát hành có thể được chỉ định bằng cách nối các dấu gạch ngang(-) và 1 loạt các dấu chấm chia cách các định danh theo ngay sau phiên bản vá. Các định danh phải bao gồm các ký tự và gạch nối ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Các định danh số không được phép bắt đầu bởi các số 0. Các phiên bản tiền phát hành có  ưu tiên thấp hơn so với phiên bản liên kết bình thường. 1 phiên bản tiền phát hành chỉ định đằng phiên bản không ổn định và có thể không thỏa mãn các yêu cầu tương thích dự định như được biểu thị so với phiên bản bình thường liên quan. Ví dụ: Examples: 1.0.0-alpha, 1.0.0-alpha.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

10. Siêu dữ liệu xây dựng có thể được biểu thị bằng cách thêm các dấu cộng và 1 loạt các dấu chấm chia cách các định danh theo ngay sau phiên bản bản vá hoặc tiền phát hành. Các định danh phải bao gồm chỉ các ký tự và gạch nối ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Siêu dữ liệu xây dựng nên được loại bỏ khi xác định phiên bản ưu tiên. Vì thế 2 phiên bản
chỉ khác nhau siêu dữ liệu xây dựng, có cùng độ ưu tiên. Ví dụ: 1.0.0-alpha+001, 1.0.0+20130313144700, 1.0.0-beta+exp.sha.5114f85.

11. Độ ưu tiên dùng để so sánh các phiên bản với nhau khi sắp xếp. Độ ưu tiên phải được tính toán bằng cách chia phiên bản thành các định danh lớn, nhỏ, vá và tiền phát hành theo thứ tự. (siêu dữ liệu xây dựng không được tính cho độ ưu tiên)
Độ ưu tiên được xác định bằng sự khác nhau đầu tiên khi so sánh mỗi định dang từ trái qua phải như sau: Các phiên bản lớn, nhỏ và vá luôn được so sánh bằng số. Ví dụ  1.0.0 < 2.0.0 < 2.1.0 < 2.1.1. Khi bản lớn, nhỏ và vá bằng nhau, phiên bản tiền phát hành có độ ưu tiên thấp hơn phiên bản bình thường. Ví dụ 1.0.0-alpha < 1.0.0. Độ ưu tiên cho 2 phiên bản tiền phát hành với cùng phiên bản lớn, nhỏ và vá phải được xác định bằng cách từng dấu chấm chia cách các định danh từ trái quá phải cho đến khi có 1 sự các biệt được tìm thấy như sau : các định danh chỉ bao gồm các chữ số được so sánh số học và các định danh với các chữ và các dấu nối được so sánh theo từ vựng theo thứ tự sắp xếp ASCII. Các định danh số học luôn có độ ưu tiên thấp hơn các định danh không phải số. 1 tập các trường tiền phát hành có độ ưu tiên cao hơn các tập nhỏ, nếu tất cả các định danh phía trước là bằng nhau. Ví dụ : 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta < 1.0.0-beta < 1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0.

### Tại sao phải sử dụng Semantic Versioning?
Đây không phải là 1 ý kiến mới hay đột phá nào cả. Trên thực tế, bạn hẳn là làm điều gì gần giống như vậy rồi. Vấn đề là "gần giống" ở đây không đủ tốt. Nếu không tuân thủ theo 1 tập các đặc điểm kỉ thuật chính thức, các số phiên bản thực chất sẽ vô nghĩa cho việc quản lý sự phụ thuộc. Bằng cách đưa các định nghĩa rõ ràng cho các ý tưởng trên, nó trở nên dễ dàng trong việc liên kết các ý tưởng của bạn tới các người dùng phần mềm. Ngay khi những ý định được rõ ràng, Các đặc điểm kĩ thuật phụ thuốc linh động ( nhưng không quá linh động)  cuối cùng cũng được hình thành.

1 ví dụ đơn giản sẽ mô tả cách Semantic Versioning có thể tạo sự phụ thuộc giữa những thứ kinh khủng trong quá khứ. Xem xét 1 thư viện tên là "Filetruck". Nó yêu cầu 1 gói Semantically Versioned gọi là "Ladder". Tại thời điểm Firetruck được tạo ra, Ladder lúc đó đang ở phiên bản 3.1.0. Từ khi Firetruck sử dụng 1 vài chức năng được giới thiệu lần đầu trong phiên bản 3.1.0, bạn có thể đặc tả 1 cách an toàn các phụ thuộc Ladder tốt hơn hay bằng so với 3.1.0 nhưng tệ hơn so với 4.0.0. Bây giờ khi Ladder ở phiên bản 3.1.1 và 3.2.0 khả dụng, bạn có thể phát hành chúng tới các hệ thống quản lý gói (package) và biết rằng chúng sẽ tương thích với các phụ thuộc phần mềm hiện tại.

Tất nhiên. là 1 lập trình viên tin cậy, bạn sẽ muốn xác thực rằng bất kỳ cập nhật gói nào cũng sẽ có chức năng như quảng cáo. Thế giới thực là 1 nơi lộn xộn, bạn sẽ không thể làm gì về nó nhưng bạn có thể thận trọng. Những gì bạn có thể làm là khiến Semantic Versioning cung cấp cho bạn theo cũng cách trong việc phát hành và cập nhật gói mà không phải chuyển tới 1 phiên bản mới của các gói phụ thuộc, giúp bạn tiết kiệm thời gian và tránh các rắc rối.

Điều này có vẻ nghe như mong muốn, tất cả những gì bạn cần làm là bắt đầu sử dụng Semantic Versioning để khai báo rằng bạn đang làm như thể và sau đó tuân theo các luật. Liên kết trang web này từ README cả bạn để những người khác biết luật và có thể tận dụng chúng.

