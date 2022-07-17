# Javascript 1
``` javascript
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>Javascript 1일차</title>
<script>
	var a ="홍길동";
	console.log(a);
	var b = 50; //숫자 50
	console.log(b);
	var c = "50"; //문자 50, 외따옴표 쌍따옴표 둘 다 가능
	var d = b+c;
	console.log(d);

	var z = a + "님 환영합니다.";
	console.log(z);
</script>
</head>
<body> </body>
</html>
```
script 태그 안에 javascript 언어를 사용하게 됩니다.
var : 변수를 선언하는 명령어입니다. 단, 문자와 숫자를 별도로 구분하진 않습니다. ""만 검토합니다.

# Javascript 1 - console 활용
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 1일차 if문</title>
<script>
	var a = "홍길동";
	var b = 10;
	var z;
	var c = a * z;
	console.log(c);
	var name = "이순신"
	if(name!="이순신"){
		console.log("해당 사용자는 가입되지 않았습니다.");
	} else{
		console.log("반갑습니다.");
	}
	var num = 116;
	if(num%2==0){
		console.log("짝수입니다.");
	} else {
		console.log("홀수입니다.");
	}
</script>
</head>
<body> </body>
</html>
```
**NaN** : Not a Number
**undefined** : 값이 없는 변수값을 의미합니다.
참고로 javascript에는 method, class는 없지만 **함수** 는 존재합니다.

# Javascript 2 - 반복문
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 반복문</title>
<script>
	//for문
	var a;
	for (a = 1; a < 10; a++) {
		//console.log(a);
	}
	//while문
	var w = 1;
	while (w < 10) {
		//console.log(w);
		w++;
	}
	//do~while문
	var z = 1;
	do {
		//console.log(z);
		z++;
	} while (z < 10);
	//더블 반복문 (for문만 사용)
	var f,ff;
	for(f=2; f<10;f++){
		for(ff=1; ff<10;ff++){
			var k =f*ff;
			console.log(f+"*"+ff+"="+k);
		}
	}
	//do~while,while문을 이용한 이중 반복문
	var i,j;
	do{
		while (j<10) {
			console.log(i+"*"+j+"="+i*j);
			j++;
		}
		i++;
	} while (i<10);
</script>
</head>
<body> </body>
</html>
```
# Javascript 2 - switch문
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 switch문</title>
<script>
	var a = 6;
	var msg;
	switch (a) {
	case 1:
		msg="신용카드";
		break;
	case 2:
		msg="계좌이체";
		break;
	case 3:
		msg="무통장 입금";
		break;
	default:
		msg="결제취소";
		break;
	} console.log(msg);
</script>
</head>
<body> </body>
</html>
```
# Javascript 2 - 함수(function)
```javascript
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Javascript 2일차 함수(function)</title>
<script>
	function a() { //일반함수
		console.log("홍길동");
	}
	// java와의 다른점  : java는 어디있든 선언을 하면 끌고 내려올수 있었는데 javascript는 위에서 선언을 하지않으면 사용 불가.
	a(); //함수를 실행한다. 단, function보다 아래에 있어야 합니다.
	//당연하지! 위에서 선언 안 하면 못 쓴다는게 Javascript의 가장 큰 특징이라며
	function b(num) { //일반함수
		console.log(num);
	}
	var z = 10; //변수 z
	b(z);	// b함수에 숫자 인수값을 적용하여 호출

	function z() { //함수 z
		zz(); // 외부 zz라는 함수로 호출함
	}
	function zz() { //함수 zz
		console.log("환영합니다.");
	} z();
	// 이거 충돌나는 이유 : 변수 z를 선언하는건지 함수 z를 선언하는건지 생성자가 중복되어서 컴퓨터가 판단 x
	// setter,getter(java) => call 함수, return 함수
	function setter(n) {
		var result = getter(n); // result 변수로 return된 값을 받습니다.
		console.log(result);	// 결과 출력
	} function getter(nn) {	// setter 함수에서 전달 받음
		var cal = nn + 20; //전달받은 값과 추가 값을 계산
		return cal; // 결과값을 return 시킴
	}
	settter(5);
</script>
</head>
<body> </body>
</html>
```
# Javascript 2 - function & return +응용문제
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 함수(function) +return 함수</title>
<script src="경로 상세주소"> </script>
<script>
function return1(k) {
	//해당 함수값을 받는 역할(상대방이 보낸 통신값)
	var msg;
	if(k%2==0){
		msg = "짝수입니다.";
	} else{
		msg = "홀수입니다.";
	}
	return msg; //결과를 상대방 서버에 재 호출
} call1(); //상대방 서버에 있는 함수 호출
</script>
</head>
<body> </body>
</html>
```
[받는 상대의 js 파일 -> call1()]
```Javascript
function call1() {
	var aa;
	var bb = 0;

	for (aa = 1; aa < 11; aa++) {
		bb += aa;
	}
	var result = return1(bb);
	console.log(result);
	console.log("해당 값을 받았습니다.");
}
```
## 응용문제 1
위의 코드를 이용하여 결과값을 return 받는 코드를 작성하시오. 숫자 20과 30을 함수로 전달하여 return 받는 결과값이 600이어야 합니다.
```javascript
<!DOCTYPE html>
<html >
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 연습문제</title>
<script>
function setter(a, b) {
	var result = getter(a, b);
	console.log(result);
}
function getter(a, b) {
	var muitl = a * b;
	return muitl;
} setter(20, 30);
</script>
<body> </body>
</html>
```

## 응용문제 2
***
setter A  
	 구구단 5단에 대한 결과값을 모두 더하여 getter로 전송

setter B  
	20~40까지 함을 모두 더하여 getter로 전송


getter 결과 A  
	해당 결과값을 받아서 3으로 나누어서 최종 계산된 값을 setter a로 전송

getter 결과 B  
	해당 결과값을 받아서 다음 문자와 함께 setter b로 전송
	"홍길동님 최종 결제 금액은 xxx 입니다."
***

setter A js파일
```Javascript
function call1(){
	var i;
	var j=5;
	var total=0;
	for(i=1;i<10;i++){
		var k=i*j;
		total+=k;
	}
	var result = return1(total);
	console.log(result);
}
```
setter B js파일
```Javascript
function call2(){
   var k=20;
   var to=0;
   while(k<=40){
      to += k;
      k++;
   }
   var l = return2(to);
   console.log(l);
}
```
getter A,B html파일
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 외부 api js 연결</title>
<script src="경로상세주소"></script> <!-- 문제 1번 -->
<script src="경로상세주소"></script> <!-- 문제 2번 -->
<script>
	function return1(ca) {
		var total1 = ca / 3;
		return total1;
	}
	function return2(cb) {
		var msg = "홍길동님 최종 결제 금액은 " + cb + "원입니다.";
		return msg;
	}
	call1();
	call2();
</script>
</head>
<body> </body>
</html>
```
# Javascript 2 - 배열
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Javascript 2일차 배열</title>
<script>
var data = [ 1, 2, 3, 4, 5 ];		// 숫자 배열
console.log(data[0]); 	// 배열[인덱스번호]
var data2 = [ "홍길동", "이순신", "강감찬" ];  // 문자배열
console.log(data2[1]);

var w = 0;
while (w < data2.lenght ) {
	console.log(data2[w]);
	w++;
}
</script>
</head>
<body> </body>
</html>
```
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Javascript 2일차 배열(응용편)</title>
<script>
function aaa() {
	var result= bbb();
	console.log(result[0]); // bbb()에서 받은 리턴값의 배열 중 0번째 것 뽑기
}
function bbb() {
	var a=1;
	var b=2;
	return[a,b]; //return 1개 이상 전달할때
}
aaa();
</script>
</head>
<body> </body>
</html>
```

# 응용문제 2

***
응용문제 setter, getter
 data_a ["hong","park","kim","jang"] - setter (getter에 보내야 함): B
 data_b [2500,3400,1000,6200] : A  
 data_c ["S","V","S","N","N"] 실버,VIP,일반 : C (getter역할만함)

 kim일 경우 [결과출력]
 kim님 적립금은 1000 이며, 일반회원 입니다.

 결과출력은 data_a를 가지고 있는 분(B)이 최종 출력

 data_b에서 출발 시 var user_id 변수 선언, user_id="jang";
 1. data_b - user_id="jang" => data_a에게 전송 (비는 해당되는 아이디 있는지 없는 지 확인)
 2. data_a는 해당 값이 있는지 없는지 파악,
    없을 경우 => "해당 사용자는 가입되지 않았습니다."
    있을 경우 data_a => 인덱스 값 보내기
    해당 인덱스를 받은 data_b는 해당 적립금 금액을 리턴 해줌
 3. data_a는 해당 값을 받음
 4. 2번에서 data_a에게 받은 인덱스 값을 data_c에게 보냄
    data_c는 index값을 받아서 해당 배열의 회원 레벨을 리턴
    data_b는 data_c에게 받은 레벨 값을 data_a에게 리턴하게 됨
 5. data_a는 아이디, 적립금, 레벨 리턴값을 결과값처럼 출력
***

1) data_a.js
```Javascript

```
2) data_b.html
```Javascript

```
3) data_c.js
```Javascript

```
# Javascript 2 - 단어 찾기 (equals/indexOf/===)
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="EUC-KR">
<title>Javascript 2일차 단어찾기</title>
<script>
	// 자바 스크립트에서는 'equals'라는 단어가 없음
	var a = "홍길동";
	var b = "홍길동";
	if (a == b) {
		console.log("해당 값이 같습니다.");
	} else {
		console.log("해당 값이 같지 않음");
	}
	var c = 10;
	var d = "10";
	console.log(typeof(d));
	//typeof() : 해당 객체의 자료형이 무엇인지 알려주는 함수입니다.
	if (c === d) {
	/* ==(문자든 숫자든 값이 같으면 -> Equal Operator) / ===(값은 같지만 type까지 확인 -> Strict Equal Operator) */
		console.log("해당 값 같음");
	} else {
		console.log("서로 다름");
	}

	//indexOf() : java의 indexOf와 동일합니다.
	var word = "홍길동님 환영합니다.";
	console.log(word.indexOf("길동"));
</script>
</head>
<body> </body>
</html>
```

# 응용문제 3
***
 js9.html
 사용자 아이디와 패스워드를 전송
 var mid="hong";
 var mpw = "1234";
 a파트에 전송
 A파트 js9.js (아이디 및 패스워드)
 ['hong','park','kim','jang','lee']
 ['ahong','bpark','kkim123','jang1234','lee0909']
 제대로 넣었을 경우 인덱스값을 b파트에 보냄
 B파트 js9.js  (연락처 및 이메일) (나)
 ['Y','N','Y','Y','Y];
 ['01012345678','01055994411','01035370132','01078015457','01031374882']
 ['hong@naver.com','park@nate.com','kim_001@gmail.com','jang_go@gmail.com','lee09@naver.com'];
 n은 탈퇴회원(a에게 탈퇴회원이라고 보냄)
y면 전화번호,이메일을 다시 a에게

 js9.html에서 아이디와 패스워드를 A파트에게 전달을 하며
 A파트 사용자는 아이디와 패스워드가 맞을 경우
 B파트 사용자에게 index값을 전달 합니다.
 B사용자는 index값을 받아서 연락처 및 이메일을 전달 하게 됩니다.
 단 B사용자는 회원탈퇴(N)일 경우 연락처와 이메일을 전달하지 않으며,
 탈퇴 회원이라고 A파트 사용자에게 전달 합니다.
 A파트 사용자는 B사용자에게 탈퇴회원 값을 받을 경우
 즉시, console에 탈퇴회원 입니다. 라고 메세지를 처리합니다.
***
```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Javascript 2일차 </title>
<script src = "http://192.168.100.204:8080/html2/js9_1.js"> </script>
<script src = "http://192.168.100.205:8080/html2/js9.js"> </script>
<script>

var id = "hong";
var pass = "ahong";

var i = partA(id,pass); //회원인덱스=> okk값 출력
bb (PartB(i)[0],PartB(i)[1],PartB(i)[2]);
</script>
</head>
<body> </body>
</html>
```
```Javascript
function partA(a, b) {
	var id = ["hong", "park", "kim", "jang", "lee"];
	var mpass = ["ahong", "bpark", "kkim123", "jang1234", "lee0909"];
	var f;
	var ck = 0;
	var okk;

	for (f = 0; f < id.length; f++) {
		if (a == id[f] && b == mpass[f]) {
			ck++;
			okk = f;
			break;
			}
		}
		if(ck==0) {
			console.log("회원정보를 확인해 주세요.")
		}
	return okk;
}
function bb(PartBt, PartBe, PartBm) {
	if (PartBm != null) {
		console.log("탈퇴회원입니다");
	}
}
```
```Javascript
function PartB(index){
	var mem =  ['Y','N','Y','Y','Y'];
	var tel = ['01012345678','01055994411','01035370132','01078015457','01031374882'];
 	var email = ['hong@naver.com','park@nate.com','kim_001@gmail.com','jang_go@gmail.com','lee09@naver.com'];

 	var restel;
 	var resemail;
 	var msg=null;
 	if(mem[index]=='Y'){
		restel = tel[index];
		resemail = email[index];
	}else if(mem[index]==='N'){
		msg = "탈퇴회원";
	}

	//console.log("partb");
	return [restel,resemail,msg];

}

function aa2(nm,pw){
	 var names = ['hong','park','kim','jang','lee'];
 	var pws = ['ahong','bpark','kkim123','jang1234','lee0909'];
	var w=0;
	var al = names.length;
	var ck=false;
	var res=null;
	while(w<al){
		if(names[w]==nm && pws[w]==pw){
			//console.log("있음");
			ck=true;
			break;
		}
		w++;
	}
	if(ck==true){
		res = w;
	}
	return res;

}

function bb2(PartBt,PartBe,PartBm){
	 if( PartBm!=null){
	 //console.log( PartBm);
	 console.log("탈퇴회원입니다다다");
 }else{
	 console.log( PartBt);
	 console.log( PartBe);
	 console.log("회원입니다다다");
 }
}
```
