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
   - Tuy nhiên cách thứ 2 sẽ có thêm một số tùy chọn. new Array(params) sẽ có thêm 1 số lựa chọn về tham số. Ta có thể định nghĩa trước được độ dài của array bằng cách
     truyền độ dài vào params. Trường hợp này được sử dụng khi chúng ta muốn tạo ra một array trống, lớn với độ dài được xác định từ trước;
   - Ví dụ:  
      var x = new Array(5); độ dài của array x sẽ là 5;
   - Tuy nhiên chúng ta có thể thực hiện như trên bằng cách thông thường.
     var x = [];
     x.length = 5; - Tóm lại, chúng ta nên sử dụng cách thông thường sử dụng dấu [];
