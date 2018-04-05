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
