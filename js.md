# 1.	Đặc tính
-	Thay đổi , chỉnh sửa html attribute , css,…
-	Xử lý các event
-	Sử dụng thẻ <script></script> , external js sử dụng file.js
# 2.	Nội dung
-	Display data bằng cách: innerHTML(trong html element), document.write(),window.alert(), console.log().
-	Access an HTML element using document.getElementById() method.
-	javaScript code blocks: để nhóm lại các khối code blocks, trong dấu ngoặc nhọn, để chúng chạy cùng nhau.
-	Khai báo biến bằng var: global scope; let: block scope; const: giá trị mặc định.
-	Code after double slashes // or between /* */ is treated as a comment.
-	Javascript phân biệt chữ hoa với chữ thường. = là gán, == so sánh giá trị ko phân biệt loại giữ liệu, === bằng mọi thứ.
-	các loại data types: number, string, boolean, object, function.
6 types of object: object,Date,array, string, number, boolean. Underfined : biến không có giá trị , hoặc giá trị là underfined; null là vô giá trị .
# 3.	object
-	bao gồm method, property: value.
-	this keyword in function refer to the “owner” of the function; đại diện  cho object; in an event this refers to the element that reveived the event.
```
document.getElementById('demo').innerHTML = "hello \
DOlly!";
```
dùng \ khi muốn xuống dòng trong lúc viết string.
- có thể chuyển object sang array bằng object.values(); sẽ hiện ra toàn bộ value trong object hoặc có thể sử dụng loop (in).
```
<script>
var person = {name:"John", age:50, city:"New York"};
var myArray = Object.values(person);
document.getElementById("demo").innerHTML = myArray;
</script>
```
- có thể đổi object sang string. 
```
var person = {age : 50, name : "truong"}
var myString = JSON.stringify(person);
// sau đó sẽ in ra JSON.
```
- nhưng đối với function thì sẽ không đổi được cách khắc phục là convert function sang string bằng toString();
```
<script>
var person = {name:"John", age:function () {return 30;}};
person.age = person.age.toString();

var myString = JSON.stringify(person);
document.getElementById("demo").innerHTML = myString;
</script>
```
- JSON.stringify() là chuyển đổi dữ liệu sang dạng json.

# 4.	Method in js

-	indexOf() thứ tự của phần tử tính từ đầu. lastIndexOf() tương tự nhưng từ cuối.
-	Search() tìm kiếm vị trí phần tử. 
```
var pos = str.search("locate");
```
-slice() lấy một đoạn string từ vị trí bao nhiêu đến bao nhiêu
```
var str = "Apple, Banana, Kiwi";
var res = str.slice(7, 13);
```
- substring() tương tự nhưng không chấp nhận số âm.
- replace() đổi vị trí. nhưng chỉ đổi vị trí của CỤM TỪ ĐẦU TIÊN. và cũng nhạy cảm về loại chữ hoa hoặc thường => khắc phục sử dụng `/..../i` nếu muốn thay toàn bộ sử dụng thêm (`/.../g`). insensitive.
```
str = "Please visit Microsoft!";
var n = str.replace("Microsoft", "W3Schools");
``` 
- để convert to upper and lower case thì
```
var text1 = "Hello World!";    
var text2 = text1.toUpperCase();
```
```
var text1 = "Hello World!";    
var text2 = text1.toLowerCase();
```
- dùng concat() để nối các string , array, ... với nhau.
```
var text1 = "Hello";
var text2 = "World";
var text3 = text1.concat(" ", text2);
var text1 = "Hello";
var text2 = "World";
var text3 = text1.concat(" ", text2);
```
- trim() để xóa khoảng trắng ở 2 bên
```
var str = "       Hello World!        ";
alert(str.trim());

```
- The charAt() Method để lấy ra kí tự bằng vị trí
```
var str = "HELLO WORLD";
str.charAt(0);  return "H"
```
- còn charCodeAt() là mã hóa nó.
- Converting a String to an Array, chuyển string sang array.
```
var txt = "a,b,c,d,e";   // String
txt.split(",");          // Split on commas
txt.split(" ");          // Split on spaces
txt.split("|");          // Split on pipe
```
- NAN not a number là 1 loại số nhưng ko là số gì. infinity or -infinity là giá trị vô cực.
- toString() đổi number ra string.
- The toFixed() Method xác định số chữ số cố định sau dấu phảy. thường dùng để viết money.
```
var x = 9.656;
x.toFixed(0);           // returns 10
x.toFixed(2);           // returns 9.66
x.toFixed(4);           // returns 9.6560
x.toFixed(6);           // returns 9.656000
```
- The toPrecision() Method  dùng để làm tròn.
```
var x = 9.656;
x.toPrecision();        // returns 9.656
x.toPrecision(2);       // returns 9.7
x.toPrecision(4);       // returns 9.656
x.toPrecision(6);       // returns 9.65600
```
- Converting Variables to Numbers có 3 cách:
     +) Number() method
     +) parseInt() method
     +) parseFloat() method

// array method.

- Converting Arrays to Strings sử dụng join();
```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
document.getElementById("demo").innerHTML = fruits.join(" * ");
```
- Splicing an Array nối , thêm vào bên trong array. nghĩa là ở chuỗi thứ 2 loại bỏ 0 chuỗi thêm  "Lemon", "Kiwi" vào.
```
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```
- Slicing an Array : cắt 1 đoạn trong array ra làm array mới. từ sau chuỗi số 1 tạo thành array mới.
```
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1);
```
- map(),forEach() : tạo mảng mới cho các phần tử.
- filter() dùng để lọc phần tử.
- every() mọi phần tử thỏa mãn trả về true
- some() một phần tử thỏa mãn cũng trả về true
- indexOf() trả về vị trí của phần tử trong Array.
```
var fruits = ["Apple", "Orange", "Apple", "Mango"];
var a = fruits.lastIndexOf("Apple");
```
- Array.find() trả về phần tử đầu tiên thỏa mãn.
- findIndex() trả về vị trí phần tử đầu tiên thỏa mãn.

// number method.

- Math.round() làm tròn.
- Math.abs() giá trị tuyệt đối
- Math.ceil() làm tròn lên.
- Math.float() làm tròn xuống.
- Math.random().
```
Math.floor(Math.random()* 10);
```
# 5. statement condition,loop
- if() else if() {} else{}.
- switch biểu diễn kết quả khác nhau với điều kiện khác nhau.
```
<script>
var day;
switch (new Date().getDay()) {
  case 0:
    day = "Sunday";
    break;
  case 1:
    day = "Monday";
    break;
  case 2:
    day = "Tuesday";
    break;
  case 3:
    day = "Wednesday";
    break;
  case 4:
    day = "Thursday";
    break;
  case 5:
    day = "Friday";
    break;
  case  6:
    day = "Saturday";
}
document.getElementById("demo").innerHTML = "Today is " + day;
</script>
```
```
switch (new Date().getDay()) {
  case 4:
  case 5:
    text = "Soon it is Weekend";
    break;
  case 0:
  case 6:
    text = "It is Weekend";
    break;
  default:
    text = "Looking forward to the Weekend";
}
```
- loop for, while: 
- for in : trong object, for of trong array
- sự khác biệt là vòng lặp for được sử dụng khi số lần lặp được biết đến còn while thì chưa .
- js break , nếu nó thỏa mãn điều kiện thì dừng.
```
for (i = 0; i < 10; i++) {
  if (i === 3) { break; }
  text += "The number is " + i + "<br>";
}
```
- js continue , nếu đúng điều kiện bỏ qua nó vẫn tiếp tục.
```
for (i = 0; i < 10; i++) {
  if (i === 3) { continue; }
  text += "The number is " + i + "<br>";
}
```    
- dùng try catch để bắt lỗi:
```
<script>
try {
  adddlert("Welcome guest!");
}
catch(err) {
  document.getElementById("demo").innerHTML = err.message;
}
</script>
```
- dùng khi với vai trò như HTML validation . throw dùng với if . finally dùng khi try catch hoàn thành. bất kể kết quả là gì
```
<script>
function myFunction() {
  var message, x;
  message = document.getElementById("p01");
  message.innerHTML = "";
  x = document.getElementById("demo").value;
  try {
    if(x == "") throw "empty";
    if(isNaN(x)) throw "not a number";
    x = Number(x);
    if(x < 5) throw "too low";
    if(x > 10) throw "too high";
  }
  catch(err) {
    message.innerHTML = "Input is " + err;
  }
}
</script>
```
- strict mode dùng để đảm bảo cho js, đã khai báo đầy đủ chưa.
- Arrow Function syntax để viết rút gọn function
```
hello = function() {
  return "Hello World!";
}
```
```
hello = function() {
  return "Hello World!";
}
```
```
hello = () => "Hello World!";
```
```
hello = val => "Hello " + val;
```
### class syntax
- sử dụng để tạo class, luôn thêm phương thức constructor(). 
# 6. prototypes
- tất cả các object đều kế thừa thuộc tính và phương thức từ prototypes.
- không thể thêm 1 thuộc tính vào existing object constructor.
- để add a new property to a constructor, you must add it to the constructor function. 
```
function Person(first, last, age, eye) {
  this.firstName = first;
  this.lastName = last;
  this.age = age;
  this.eyeColor = eye;
  this.nationality = "English";// dòng này là thêm thuộc tính vào .
}
Person.property = "hi" // sẽ không chạy.
```
- Prototype Inheritance: kế thừa nguyên mẫu. object.prototype. dùng để thêm new methods or properties.
```
Person.prototype.nationality = "English";
```
# 7.function
- involk self-invoking Functions là hàm tự gọi:
```
<script>
(function () {
  document.getElementById("demo").innerHTML = "Hello! I called myself";
})();
</script>
```
- call() 
```
person.fullName.call(person1, "Oslo", "Norway");
```
- apply()
```
person.fullName.apply(person1, ["Oslo", "Norway"]);
```
# 8.JavaScript Closures
```
<script>
var add = (function () {
  var counter = 0;
  return function () {counter += 1; return counter;}
})();

function myFunction(){
  document.getElementById("demo").innerHTML = add();
}
</script>
```
# 9.JavaScript Class Inheritance
- kế thừa sử dụng `extend` keyword. và `super` keyword.
```
class Car {
  constructor(brand) {
    this.carname = brand;
  }
  present() {
    return 'I have a ' + this.carname;
  }
}

class Model extends Car {
  constructor(brand, mod) {
    super(brand);
    this.model = mod;
  }
  show() {
    return this.present() + ', it is a ' + this.model;
  }
}

let my"no-bok">Car = new Model("Ford", "Mustang");
document.getElementById("demo").innerHTML = my"no-bok">Car.show();
```
- static dùng để gọi tên class khi sử dùng hàm thay vì gọi biến.
```
<script>
class Car {
  constructor(name) {
    this.name = name;
  }
  static hello(x) {
    return "Hello " + x.name;
  }
}

let myCar = new Car("Ford");
document.getElementById("demo").innerHTML = Car.hello(myCar);
</script>
```
- JavaScript Callback Functions call back gọi lại hàm trong hàm. call back thường sử dụng thời gian. `setTimeout(myFunction, 4000);` sau bao thời gian thì làm;
.
```
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}
function myCalculator(num1, num2, callback) {
  let sum = num1 + num2;
  callback(sum);
}
myCalculator(5, 5, myDisplayer);
```
- `setInterval(mỳfunction, 1000);` xác định thời gian lặp lại
```
setInterval(myFunction, 1000);

function myFunction() {
  let d = new Date();
  document.getElementById("demo").innerHTML=
  d.getHours() + ":" +
  d.getMinutes() + ":" +
  d.getSeconds();
}
```
# 10.JavaScript HTML DOM
- khi web page load thì browser tạo ra DOM của pages.
- The HTML elements as objects;
The properties of all HTML elements;
The methods to access all HTML elements;
The events for all HTML elements.
- events.
- đã học.
- navigation 
- The HTMLCollection Object.
The getElementsByTagName() method returns an HTMLCollection object. An HTMLCollection is NOT an array!.
An HTMLCollection may look like an array, but it is not.
You can loop through the list and refer to the elements with a number (just like an array).
However, you cannot use array methods like valueOf(), pop(), push(), or join() on an HTMLCollection.
- NodeList là danh sách các nốt lấy từ document. nó gần tương tự như HTMLCollection object. querySelectorAll() là truy vấn toàn bộ node nào đó.
# 11. The Browser Object Model (BOM)
- đã học
-  Window Methods: window.open() - open a new window
window.close() - close the current window
window.moveTo() - move the current window
window.resizeTo() - resize the current window
- window.location dia chi cau link.
- JavaScript Window History. lich su trinh duyet. 
- JavaScript Window Navigator: thong tin lien quan den browser cua nguoi dung.
- JavaScript Popup Boxes: thong bao day len man hinh. window.alert() - window.confirm() - Prompt Box.
- JavaScript Timing Events: setTimeout(function, milliseconds) - setInterval(function, milliseconds) 
```
<button onclick="setTimeout(myFunction, 3000)">Try it</button>

<script>
function myFunction() {
  alert('Hello');
}
</script>
```
- JavaScript Cookies: chứa lượng dữ liệu nhỏ của người dùng trong máy tính.
- AJAX Introduction: đọc data từ web server sau khi pagge được tải, updates mà ko cần reload, gửi data lên websever.
```
function loadDoc() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
     document.getElementById("demo").innerHTML = this.responseText;
    }
  };
  xhttp.open("GET", "ajax_info.txt", true);
  xhttp.send();
}
```
- để gửi yêu cầu đến server ajax sử dụng open() , send().
```
xhttp.open("GET", "ajax_info.txt", true);
xhttp.send();
```
- GET or POST? được sử dụng trong nhiệm vụ lấy dữ liệu.
- JSON là công thức để lưu trữ và chuyển đổi dữ liệu. json là văn bản viết bằng những kí hiệu của javascript.
- loại dữ liệu của json là a string
a number,an object (JSON object)
an array,a boolean,null. luôn được viết trong dấu ngoặc kép ` { "name":"John" } `.
- xml vai trò như json nhưng được viết dưới dạng tựa như html. nhưng json nhanh hơn.
```
<employees>
  <employee>
    <firstName>John</firstName> <lastName>Doe</lastName>
  </employee>
  <employee>
    <firstName>Anna</firstName> <lastName>Smith</lastName>
  </employee>
  <employee>
    <firstName>Peter</firstName> <lastName>Jones</lastName>
  </employee>
</employees>
```
- Arrays as JSON Objects
```
[ "Ford", "BMW", "Fiat" ]
```
- Web APIs là application programming interface. nó ko được tích hợp sẵn muốn sử dụng phải tải về.




```

```