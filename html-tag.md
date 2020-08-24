# 태그 Syntax

<!DOCTYPE html> // html5에 맞게 작성할테니 그에 맞게 랜더링 부탁

Document Type Declaration
= DTD 선언
= 문서 형식 선언

<html> // html 태그안에는 <head>, <body> 두개의 태그만 사용가능
	<head>
		<title>html파일의 대제목</title> // 필수태그
	</head>
	<body></body>
</html>

— head 태그 안의 중요 태그들
	1.	<title> 검색 최적화
	2.	<link> css 파일 첨부 (font도 해당)
	3.	<style> css 직접 조작
	4.	<script> js 파일 첨부 // html body 태그의 마지막에 넣는게 좋다.
	5.	<meta name=“메타데이터의 종류” content=“메타데이터 값”> // name과 content 필수
 	5-1. <meta name=“viewport” content=“width=device-width, initial-scale=1.0”> // 반응형 웹을 위	한 화면사이즈
	5-2. <meta name=“author” content=“최유영”>
	5-3. <meta name=“keywords” content=“최유영 공부”>
	5-4. <meta name=“description” content=“최유영 공부”>


[제목과 문단]
<h1></h1>
<p></p>

[강조]
<strong></strong> // 굵어진다.
<em></em> // 기울어진다.

[링크]
<a></a> // anchor

[리스트]
ul이나 ol의 직접자식은 li만 올 수 있다.

[정의]
// {key : value} 형식으로 데이터를 표현하고 싶을 때
// description list
<dl>
	<dt>최유영</dt> // description term
// 정확한 정의를 나타낼때는 <dt> 안에 <dtn>을 써준다.
	<dd>프런트엔드 개발자</dd> // description data
</dl>

[인용 Quotations]
<blockquote cite=“인용사이트주소”> // 전체인용
	<q>문장 내 간단 인용</q>
	<cite>인용자</cite>
</blockquote>

[form]
<form action=“API주소” method=“GET”>
	<input> // type을 꼭 써줘야한다.
<label for=“input 태그의 id 값”> // 필수는 아님
	<input type=“text” placeholder=“이름을 입력하세요” minlenght=“5” maxlength=“13” required/disabled value=“최유영”/>
<input type=“number” min=“12” max=“80”/>
<input type=“file” accept=“.png, .jpg”/>

// radio type 쓸때는 동일한 name 으로 묶어줘야한다.
<input type=“radio” name=“subscription”  value=“1” id=“subscribed” />
<label for=“subscribed”>구독중</label>
<input type=“radio” name=“subscription” value=“0” id=“unsubscribed” />
<label for=“subscribed”>미구독</label> // submit할때 value값이 넘어가기 때문에 꼭 써줘야한다. 안써주면 그냥 name값=on 으로 넘어가서 뭐가 선택되었는지 알 수 없다.

// 체크박스 다중선택
<input type=“checkbox” name=“skills” value=“html” id=“html”/>
<label for=“html”>html</label>
<input type=“checkbox” name=“skills” value=“css” id=“css”/>
<label for=“css”>css</label>
<input type=“checkbox” name=“skills” value=“js” id=“js”/>
<label for=“js”>js</label>
// 다 선택하면 ?skills=html&skills=css&skills=js 으로 보내진다.

<label for=“skills”>스킬</label>
<select (multiple) name=“skills” id=“skills”>
	<option value=“html”>html</option>
	<option value=“css”>css</option>
	<option value=“js”>js</option>
</select>

<label for=“field”>자기소개:</label>
<textarea id=“field” rows=“” cols=“”> //  여러줄의 텍스트를 받을 수 있다.
</textarea>

// button 태그는 type을 꼭 써줘야한다. (button, submit, reset)
<button type=“submit”>제출하기</button>

</form>

[테이블1]
<table>
	<thead>
		<tr>
			<th>ID</th>
			<th>이름</th>
			<th>직업</th>
			<th>기타</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>001</td>
			<td>최유영</td>
			<td>개발자</td>
			<td></td>
		</tr>
		<tr>
			<td>001</td>
			<td>이지아</td>
			<td>개발자</td>
			<td>경력직</td>
		</tr>
	</tbody>
	<tfoot>
	</tfoot>
</table>

[테이블2]
<table>
	<thead>
		<tr>
			<th></th>
			<th scope=“col”>월</th> // 브라우저에게 th의 성격을 알려준다. table head에만 쓸 수 있는 속성이다.
			<th scope=“col”>화</th>
			<th scope=“col”>수</th>
			<th scope=“col”>목</th>
			<th scope=“col”>금</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th scope=“row”>1교시</th> // 세로 th
			<td rowspan=“2”>국어</td>
			<td>영어</td>
			<td>수학</td>
			<td>국어</td>
			<td>영어</td>
		</tr>
		<tr>
			<th scope=“row”>2교시</th>
			// <td></td>
			<td>영어</td>
			<td>수학</td>
			<td>국어</td>
			<td>영어</td>
		</tr>
		<tr>
			<th scope=“row”>3교시</th>
			<td>국어</td>
			<td>영어</td>
			<td>수학</td>
			<td>국어</td>
			<td>영어</td>
		</tr>
		<tr>
			<th  scope=“row” colspan=“6”>점심시간</th>
		</tr>
	</tbody>
	<tfoot>
	</tfoot>
</table>


[미디어 파일]
<audio src=“./audio/music/cyy.mp3” controls></audio> // 재생버튼이나 음향을 조절하고 싶다면 control 속성 써준다.
// control 보여주고 싶지는 않지만 리로드될때 재생시키고 싶다면 autoplay 또는 loop autoplay

<video src=“”></video>

<iframe width=“” height=“” src=“”></iframe> // html안의 html

[기타]

<abbr title=“Attention Deficit Hyperactivity Disorder”>ADHD</abbr> //abbreviation 약자
// abbr 태그는 title에 약자의 풀네임을 꼭 적어주어야한다.

<address>
	<h1>최유영</h1>
	<a href=“http://youtube.com/c/kimbug”>http://youtube.com/c/kimbug</a>
</address>

<details>
    <summary>오늘의 환율</summary>
    <ul>
        <li>달러($) : 1,135.90</li>
        <li>유로(€) : 1,284.08</li>
        <li>엔(￥) : 1,014.88</li>
    </ul>
</details>
// 사용자가 직접 조작하여 보거나 숨길 수 있는 부가적인 세부사항(additional details)을 명시할 때 사용

<pre></pre> // 포맷전
// reformatted text

<code></code> //code


올바른 Sectioning Elements 사용법

<section>, <nav> 안에는 꼭 <heading> 사용
