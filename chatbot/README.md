# Chatbot for Etadi

### Một số lý thuyết cơ bản

* Agents:
	- _Agents là miêu tả cụ thể nhất của NLU ( Hiểu ngôn ngữ tự nhiên )._

	- _Agents có thể được đưa vào: ứng dụng, sản phẩm, dịch vụ của bạn và chuyển đổi yêu cầu người dùng tự nhiên thành dữ liệu có thể thực hiện được._

	- _Sự chuyển đổi đó xuất hiện khi đầu vào của một người dùng phù hợp với một trong những tính năng bên trong tác nhân của bạn._

	- _Intents ( ý định ): là các thành phần được xác định trước hoặc do nhà phát triển xác định của các Agents xử lý yêu cầu của người dùng._

	- _Agents có thể được thiết kế để quản lý luồng hội thoại theo một hướng cụ thể.
	Nó có thể hoàn thành với sự trợ giúp của Contexts ( ngữ cảnh ), độ ưu tiên Intents, slot filling, responsiblilities và fulfillment thông qua webhook_

* Intents: 
	- Intents đại diện giữa những gì người dùng nói và hành động của phần mềm.

	- _Tức là các hành động_

	- Giao diện Intents có các phần sau:
		-  Đào tạo các cụm từ (Training Phrases) (User expression)
		- Hành động (Action)
		- Phản hồi (Response)
		- Bối cảnh (Contexts)

	- Training Phrases: 
		- Mỗi input của người dùng có thể diễn tả một trong 2 mô hình: Mô hình dữ liệu mẫu (Template Mode - @) và mô hình dữ liệu tự nhiên (Example Mode - ")
		
		- Examples: được viết bởi ngôn ngữ tự nhiên và chú thích (annotated) để các giá trị tham số có thể được trích xuất.
		
		- Templates: Chứa các tham chiếu trực tiếp tới các thực thể thay vì chú thích (annotated), nghĩa là tên thực thể được đặt trước bằng ký hiệu @

	- Example Annotation:
		- _Annotation (lời chú giải) là một quá trình (hay kết quả của một quá trình) của liên kết một từ hay một cụm từ trở thành một thực thể._
		- Automatic Annotation (tiến trình tự động): 
			Khi bạn thêm một ví dụ cho "User says" (người dùng nói), chúng sẽ được chú thích tự động. Hệ thống phát hiện sự tương ứng giữa các từ hoặc cụm từ và các thực thể của nhà phát triển và hệ thống hiện tại, làm nổi bật các từ/ cụm từ đó. (Highlight). Nó cũng tự động gán một tên tham số cho mỗi thực thể đã được phát hiện.

		- Editing Automatically Annotated Examples: Chỉnh sửa tự đông
		... [DiaglowFlow](https://dialogflow.com/docs/intents)

	- Action: 
		- _Phần này bao gồm trường tên hành động và bảng thông số (Key-Value)_
		- _Tên hành động (Action name) được định nghĩa thủ công. Nó sẽ là từ kích hoạt cho ứng dụng của bạn để thực hiện một hành động cụ thể._
		- _Parameter (tham số) có thể được điền tự động "User says" examples (trường hợp thực tế) và templates (mẫu), hoặc thêm thủ công._

	- Response: 
		- Trong phần này, bạn có thể định nghĩa phản hồi cuar Agents được cung cấp bởi ứng dụng của bạn khi Intents được kích hoạt. (User says)
		- **Hành động phản hồi**

	- Contexts (Ngữ cảnh)
		- Ngữ cảnh được thiết kế để chuyển thông tin từ các cuộc hội thoại trước đây hoặc các nguồn bên ngoài (Vd: thông tin người dùng, thông tin thiết bị). Ngoài ra chúng có thể được sử dụng để quản lý luồng hội thoại.

		- Các ngữ cảnh đầu vào là một điều kiện tiên quyết cho mục đích (Intent) kết hợp, Intent (ý định) sẽ tham gia vào việc kết hợp chỉ khi tất cả các ngữ cảnh trong trường ngữ cảnh đầu vào đang hoạt động.

	- Độ ưu tiên ý định (Intents priority)
		- Độ ưu tiên ý định cho phép bạn gán trọng lượng nhiều hơn cho một trong những ý định trong trường hợp một cụm từ nhập phù hợp với nhiều ý định. 
* Entites
	- Các thực thể là một công cụ mạnh mẽ được sử dụng để trích xuất các giá trị tham số đầu vào từ ngôn ngữ tự nhiên. Bất kỳ dữ liệu quan trọng nào bạn muốn nhận được  từ yêu cầu của người sử dụng, sẽ có một thực thể tương ứng.

	- Các thực thể được sử dụng trong một Agent cụ thể sẽ phụ thuộc vào các giá trị tham số dự kiến sẽ được trả lại như là kết quả hoạt động của Agent. Nói cách khác, một nhà phát triển không cần phải tạo các thực thể cho mọi khái niệm có thể được đề cập trong tác nhân - chỉ đối với những người cần cho dữ liệu có thể thực hiện được.

	- Có 3 loại thực thể: Hệ thống (định nghĩa bởi Dialogflow), nhà phát triển (định nghĩa bởi lập trình viên), và người dùng (xây dựng dựa trên cá nhân người dùng cuối trong mọi request - yêu cầu). Mỗi trong số này có thể được phân loại như là ánh xạ (có giá trị tham khảo), enum (không có giá trị tham chiếu), hoặc composite(chứa các thực thể khác có bí danh và các giá trị kiểu đối tượng trả về).

	- [Chi tiết](https://dialogflow.com/docs/entities)

* Action and parameters (Cái này của Dialogflow)

* Contexts (Ngữ cảnh)
	- _Contexts đại diện cho bối cảnh hiện tại của yêu cầu người dùng. Điều này hữu ích cho việc phân biệt các cụm từ có thể mơ hồ hoặc có ý nghĩa khác nhau tuỳ vào sở thích, vị trí địa lý, trang hiện tại của ứng dụng hoặc chủ đề của cuộc trò chuyện._

	- Ví dụ, nếu một người sử dụng đang nghe nhạc và tìm kiếm nhóm nhạc phù hợp với sở thích của họ, họ sẽ nói kiểu thế này: "Tôi muốn nghe nhiều về chúng". Là một lập trình viên, bạn có thể bảo gồm tên của nhóm nhạc trong văn cảnh này cùng với yêu cầu của người dùng, vì thế Agent có thể sử dụng chúng trong các Intents khác.

	- Ví dụ khác, bạn là nhà sản xuất thiết bị nhà thông minh, và bạn có một ứng dụng điều khiển đèn và thiết bị gia dụng. Một người dùng nói: "Bật đèn hiên trước nhà", theo sau là "Tắt nó đi". Bởi cài đặt một ngữ cảnh, ứng dụng sẽ hiểu được rằng câu thứ hai có liên quan tới cái bóng đèn ở yêu cầu lần trước. Sau đó, nếu người dùng nói: "Bật máy pha cà phê", và nói "Tắt nó đi", nó sẽ dẫn đến hành động khác hơn so với trước đây, bởi vì đó là một ngữ cảnh mới.

* Dialogs (hộp thoại)
	- Có 2 loại Dialogs đề cập khi xây dựng kịch bản tương tác hội thoại.
		- Linear dialogs (Hộp thoại tuyến tính) - mục tiêu của chúng ta là thu thập thông tin cần thiết để hoàn thành hành động bắt buộc (Ví dụ: Tìm khách sạn gần nhất, bật bóng đèn bên phải, bật bài hát mong muốn.)
		- Non-linear dialogs (Hộp thoại không tuyến tính), có nhiều nhánh, tuỳ thuộc vào câu trả lời của người dùng.

	- Linear Dialog:	
