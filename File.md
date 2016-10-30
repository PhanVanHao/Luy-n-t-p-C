#Đọc - Ghi File trong C
Chương trước đã giải thích về các thiết bị nhập – xuất tiêu chuẩn được xử lý bởi ngôn ngữ C. Ở chương này chúng ta sẽ thấy cách lập trình viên tạo, mở và đóng các file văn bản hoặc file nhị phân với các dữ liệu lưu trữ.

Một file biểu diễn một chuỗi các bytes, không kể đó là file văn bản hay file nhị phân. Ngôn ngữ lập trình C cung cấp các hàm truy cập mức độ cao cũng như thấp (mức hệ điều hành) để thao tác với file trên thiết bị lưu trữ. Chương này sẽ đưa bạn đến những cách gọi hàm quan trọng cho việc quản lý file.
Mở file trong C
Bạn có thể sử dụng hàm fopen() để tạo file mới hoặc để mở các file đã tồn tại. Cách gọi này sẽ khởi tạo đối tượng loại FILE, mà bao gồm thông tin cần thiết để điều khiển luồng. Dưới đây là một cách gọi hàm:
```
FILE *fopen( const char * ten_file, const char * che_do );
```
Ở đây, ten_file là một chuỗi, được coi như tên file và giá trị che_do truy cập có thể là những giá trị dưới đây:
| Mode 	| Miêu tả                                                                                                                                                                      	|
|------	|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| r    	| Mở các file đã tồn tại với mục đích đọc                                                                                                                                      	|
| w    	| Mở các file với mục đích ghi. Nếu các file này chưa tồn tại thi file mới được tạo ra. Ở đây, chương trình bắt đầu ghi nội dung từ phần mở đầu của file                       	|
| a    	| Mở file văn bản cho việc ghi ở chế độ ghi tiếp theo vào cuối, nếu nó chưa tồn tại thì file mới được tạo. Đây là chương trình ghi nội dung với phần cuối của file đã tồn tại. 	|
| r+   	| Mở file văn bản với mục đích đọc và ghi.                                                                                                                                     	|
| w+   	| Mở một file văn bản cho chế độ đọc và ghi. Nó làm trắng file đã tồn tại nếu file này có và tạo mới nếu file này chưa có.                                                     	|
| a+   	| Mở file đã tồn tại với mục đích đọc và ghi. Nó tạo file mới nếu không tồn tại. Việc đọc file sẽ bắt đầu đọc từ đầu nhưng ghi file sẽ chỉ ghi vào cuối file.                  	|