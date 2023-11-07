# Profile_statistics
<img src="./Profile_statistics.gif">

## 효과    
포트폴리오에서 경력이랑 프로젝트를 보여줄 때 사용  

## 사용한 라이브러리 
**fontAwesome**    
https://fontawesome.com/

<br>

## 학습  
### 1. css : media query  
사이트에 접속하는 장치에 따라 특정한 CSS 스타일을 사용하는 방법  
미디어 쿼리를 사용하면, <u>접속하는 기기의 화면 크기에 따라 레이아웃이 달라짐</u>  
<u>반응형 디자인</u>을 만드는 가장 일반적인 접근 방식  

기본 구문  
```
@media media-type and (media-feature-rule) {
  /* CSS rules go here */
}
```

### 2. html : 데이터 속성 
HTML5에서는 해당 요소에서 사용자가 임의로 지정한 속성값을 활용할 수 있으며, 이를 Custom Data Attribute라고 부른다.   

**data-`*` 속성의 구성**

- 속성 이름은 대문자를 포함해서는 안되며 "data-"접두어 다음에 적어도 하나 이상의 문자가 있어야 한다.

- 속성 값은 임의의 문자열이 될 수 있다.

웹을 이용하는 사용자가 아무런 제한없이 data-속성을 보고 그 정보들을 해석할 수 있기 때문에 <u>보안관련된 정보들은 담지 않는것이 좋다.</u>

<br>

**javascript로 접근하기**  

값을 읽기 위한 완전한 HTML 이름과 함께 getAttribute()를 사용   
```
<!-- HTML -->
<article
  id="electriccars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
  ...
</article>

<!-- js -->
const article = document.querySelector("#electriccars");
// 아래 코드도 작동합니다.
// const article = document.getElementById("electriccars")

article.dataset.columns; // "3"
article.dataset.indexNumber; // "12314"
article.dataset.parent; // "cars"
```

<br>

**css로 접근하기**   
데이터 속성은 평문 HTML 속성이기 때문에 CSS에서도 접근할 수 있다는 것에 주목하세요. 예를 들어, 부모 데이터를 article에서 보여주려면 attr()함수의 생성된 content 를 사용하면 됩니다.  
```
article::before {
  content: attr(data-parent);
}
```

<br>  

CSS의 속성 선택자도 데이터에 따라 <u>스타일을 변경</u>하는 데 사용할 수 있습니다.  
```
article[data-columns="3"] {
  width: 400px;
}
article[data-columns="4"] {
  width: 600px;
}
```

### 3. js : Math.ceil()
항상 반올림하여 주어진 숫자보다 크거나 같은 가장 작은 정수를 반환
```
console.log(Math.ceil(0.95));
// Expected output: 1

console.log(Math.ceil(4));
// Expected output: 4

console.log(Math.ceil(7.004));
// Expected output: 8

console.log(Math.ceil(-7.004));
// Expected output: -7
```


<br>

## 학습 출처
**유튜브**  
https://www.youtube.com/@JavaScriptKing  


**css**  
https://developer.mozilla.org/  
https://www.w3schools.com/