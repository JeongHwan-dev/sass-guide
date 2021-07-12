<div align="center">
  <br />
  <img src="./images/sass_logo.png" height="200px" />
  <br />
  <br />
  <h1>:art: Sass(SCSS) 가이드 (Sass(SCSS) Guide)</h1>
</div>
 
<br />
 
## 목차
 
1. **[개요](#개요)**

<br />

## 개요

**Sass(SCSS)** 는 CSS의 불폄함을 해결해주는 `CSS 전처리기(Preprocessor)`이다.  
표준 CSS 보다 훨씬 많은 기능`(선택자의 중첩, 조건문, 반복문, 다양한 단위의 연산 등)`을 사용하여 더 편리하게 작성할 수 있다.

### Sass와 SCSS의 차이점은?

**SCSS**는 Sass(Syntactically Awesome Style Sheets)의 3버전에서 새롭게 등장하였다.  
**SCSS**는 CSS 구문과 완전히 호환되도록 하여 `CSS와 거의 같은 문법으로 Sass 기능을 지원`한다.

|        구분        |   Sass   |     SCSS     |
| :----------------: | :------: | :----------: |
|  선택자 유효범위   | 들여쓰기 | `{}`(중괄호) |
| `;`(새미콜론) 유무 |    O     |      X       |

- **Sass**

```sass
.container
  width: 100px
  height: 100px
  h1
    color: blue
    font-size: 12px
```

- **SCSS**

```scss
.container {
  width: 100px;
  height: 100px;
  h1 {
    color: blue;
    font-size: 12px;
  }
}
```

<div>
  <div>
    <img src="./images/imac_icon.png" height="100px" />
    <img src="./images/sass_logo2.png" height="80px" />
  </div>
  <div>
    <br />
    <img src="./images/down_arrow_icon.png" height="60px" />
    <span>
      <strong>컴파일(Compile)</strong>
    </span>
    <br />
    <br />
  </div>
  <div>
    <img src="./images/chrome_logo.png" height="100px" />
    <img src="./images/css_logo.png" height="100px" />
  </div>
<div>
