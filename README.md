# Thesis - Đồ án tốt nghiệp
# Đào Nam Tiến - 20182 - HUST

## React-Native: Etadi báo nói & bản đồ giao thông

## Chat bot

### Một số lý thuyết cơ bản

* Agents:
	- _Agents là miêu tả cụ thể nhất của NLU ( Hiểu ngôn ngữ tự nhiên )._

	- _Agents có thể được đưa vào: ứng dụng, sản phẩm, dịch vụ của bạn và chuyển đổi yêu cầu người dùng tự nhiên thành dữ liệu có thể thực hiện được._

	- _Sự chuyển đổi đó xuất hiện khi đầu vào của một người dùng phù hợp với một trong những tính năng bên trong tác nhân của bạn._

	- _Intents ( ý định ): là các thành phần được xác định trước hoặc do nhà phát triển xác định của các Agents xử lý yêu cầu của người dùng._

	- _Agents có thể được thiết kế để quản lý luồng hội thoại theo một hướng cụ thể.
	Nó có thể hoàn thành với sự trợ giúp của Contexts ( ngữ cảnh ), độ ưu tiên Intents, slot filling, responsiblilities và fulfillment thông qua webhook_
	
	![Agents](./img/agents.png)

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
		- Trong phần này, bạn có thể định nghĩa phản hồi của Agents được cung cấp bởi ứng dụng của bạn khi Intents được kích hoạt. (User says)
		- **Hành động phản hồi**

	- Contexts (Ngữ cảnh)
		- Ngữ cảnh được thiết kế để chuyển thông tin từ các cuộc hội thoại trước đây hoặc các nguồn bên ngoài (Vd: thông tin người dùng, thông tin thiết bị). Ngoài ra chúng có thể được sử dụng để quản lý luồng hội thoại.

		- Các ngữ cảnh đầu vào là một điều kiện tiên quyết cho mục đích (Intent) kết hợp, Intent (ý định) sẽ tham gia vào việc kết hợp chỉ khi tất cả các ngữ cảnh trong trường ngữ cảnh đầu vào đang hoạt động.

	- Độ ưu tiên ý định (Intents priority)
		- Độ ưu tiên ý định cho phép bạn gán trọng lượng nhiều hơn cho một trong những ý định trong trường hợp một cụm từ nhập phù hợp với nhiều ý định. 
* Entites
	- Các thực thể là một công cụ mạnh mẽ được sử dụng để trích xuất các giá trị tham số đầu vào từ ngôn ngữ tự nhiên. Mọi dữ liệu quan trọng bạn muốn lấy từ yêu cầu của người sử dụng sẽ có một thực thể 