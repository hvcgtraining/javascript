# javascript

1. Hàm ẩn danh

Hàm ẩn danh (anonymous function) là hàm không tên, được sinh ra đúng vào thời điểm chạy của chương trình. Tức là thông thường khi khai báo một hàm,
trình biên dịch sẽ lưu lại trong bộ nhớ nên có thể gọi trên hay dưới vị trí khai báo hàm đều được, còn với hàm ẩn danh thì nó chỉ được sinh ra khi
trình biên dịch xử lý tại vị trí của nó nên nó chỉ có thể gọi sau khi được khai báo và được gọi bằng cách sử dụng tên biến gán cho nó .

Hàm ẩn danh thường được khai báo bằng cách sử dụng toán tử thay vì sử dụng cú pháp định nghĩa thông thường. Ví dụ:
var anonymous = function() {
console.log('Hello');
};
anonymous();
Chúng ta có thể thực hiện gọi hàm ngay sau khi báo bằng cách sử dụng IIFE (Immediately-invoked Function Expression). Ví dụ:
var anonymous = (function() {
console.log('Hello');
})();

Cách sử dụng: - Một trong những cách sử dụng phổ biến của anonymous function là được sử dụng như một tham số trong một function khác (hay còn gọi là callback function)
Ví dụ:
button.addEventListener('click', function(){
console.log('Hello');
}
); - Ta có thể sử dụng anonymous function trong closure:
Ví dụ: function first() {
var a = 1;
return function() {
console.log(a);
}
}; - Anonymous function được khai báo báo inline (hàm nội tuyến) cho nên nó có lợi thế là chạy nhanh hơn và chúng có thể truy cập tại các biến của parent scope. - Code sẽ khép kín và dễ đọc hơn.

2. Khác nhau giữa Array và [] trong tạo array:
   - Có 2 cách khởi tạo array, cách thông thường là sử dụng dấu [], cách còn lại là sử dụng từ khóa new Array();
   - Cách thông thường sẽ rõ ràng, dễ đọc dễ hiểu và khả năng thực thi nhanh hơn cách sử dụng từ khóa new Array().
   - Tuy nhiên cách thứ 2 sẽ có thêm một số tùy chọn. new Array(params) sẽ có thêm 1 số lựa chọn về tham số. Ta có thể định nghĩa trước được dài của array bằng cách
     truyền độ dài vào params. Trường hợp này được sử dụng khi chúng ta muốn tạo ra một array trống, lớn với độ dài được xác định từ trước;
   - Ví dụ:  
      var x = new Array(5); độ dài của array x sẽ là 5;
   - Tuy nhiên chúng ta có thể thực hiện như trên bằng cách thông thường.
     var x = [];
     x.length = 5; - Tóm lại, chúng ta nên sử dụng cách thông thường sử dụng dấu [];





// strict mode + event handlers

strict mode trong javascript là gì?

Strict mode được ra đời từ javascript phiên bản 1.8.5 , strict mode sẽ làm code javascript có nhiều quy tắc khắc khe,quản lý nghiêm ngặt hơn về cú pháp, nhằm giải quyết tính thiếu an toàn của javascript.
Để sử dụng strict mode ta dùng từ khóa “use strict” và đặt vào nơi muốn sử dụng, strict mode có 2 phạm vi sử dụng đó là toàn cục và cục bộ,nếu đặt “use strict” ở đầu file thì nó sẽ có phạm vi toàn cục, còn khi đặt trong hàm thì nó có phạm vi chỉ trong hàm đó.

 

Biến b chưa được khởi tạo
 
Khi ở bình thường thì nó vẫn chạy:        

Nhưng khi ở strict mode thì sẽ bị lỗi:
 

 

Bình thường sử dụng được delete:
 

 

Khi ở strict mode thì không được:
 

 

Các tham số của hàm không được trùng nhau:
ở chế độ thường
 
 
Strict mode sẽ báo lỗi:
 
 

Khai báo biến number kiểu nhị phân ở strict mode sẽ bị lỗi
 

 
Khai báo tên biến trùng với key ở bình thường sẽ không sao,nhưng ở strict mode sẽ bị lỗi
 
 

Ngoài ra bạn không thể sư dụng tên biến với các từ khóa sau:
•	implements
•	interface
•	package
•	private
•	protected
•	public
•	static
•	yield



event handlers
Event handlers trong javascript là một hoặc nhiều hàm xử lý sự kiện được gắn kết với event khi nó được kích hoạt. Các functions này phản hồi lại các tương tác cho người dùng các kết quả được lập trinh sẵn theo ý định của lập trình viên.

Gán trực tiếp event handlers qua thuộc tính của phần tử bằng chỉ thị html:
 
 
 
 
Gán event handlers thông qua thuộc tính đối tượng
 
 



//
sub mit form

Để submit trong javascript thì đơn giản nhất là ta cho button cho type="submit" thì nó đã có nghĩa là submit cho cái form or cái gì đó rồi.

VD: <form id="form1" name="formdata">
        <input type="text" name="username" placeholder="Nhập Username"><br>
        <input type="password" name="password" placeholder="Nhập Password"><br>
        <input type="email" name="email" placeholder="Nhập Email"><br>
        <input type="text" name="phone" placeholder="Nhập số điện thoại"><br>
        <button type="submit" > Submit form </button>
    </form>
1 Vài cách khác để lấy submit  , mình minh hoạ bằng hình ảnh nhé
Ta tạo 1 function rồi onclick nó vào button or input type="button" 
 
 

hoặc chúng ta viết trực tiếp dưới js để lấy value thì khỏi cần onclick trên button 
 

Chúng ta còn có 1 cách khác là viết hàm onsubmit để lấy submit thẳng từ trên thẻ form or div bao value của nó
 
Kết quả trả về tương tự
 






