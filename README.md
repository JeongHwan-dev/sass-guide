<div align="center">
  <br />
  <img src="./images/sass_logo.png" height="200px" />
  <br />
  <h1>Sass(SCSS) 가이드 (Sass(SCSS) Guide)</h1>
  <br />
</div>
 
 
## 목차
 
1. [개요](#1-개요)
2. [주석](#주석)
3. [중첩](#중첩)
4. [상위 선택자 참조](#상위-선택자-참조)
5. [**중첩된 속성**](#중첩된-속성)

<br />

## 개요

**Sass(SCSS)** 는 CSS의 불폄함을 해결해주는 `CSS 전처리기(Preprocessor)`입니다.  
표준 CSS 보다 훨씬 많은 기능`(선택자의 중첩, 조건문, 반복문, 다양한 단위의 연산 등)`을 사용하여 더 편리하게 작성할 수 있습니다.

<br />

<div>
  <div>
    <img src="./images/imac_icon.png" alt="iMac" height="100px" />
    <img src="./images/sass_logo2.png" alt="Sass" height="80px" />
  </div>
  <div>
    <br />
    <img src="./images/down_arrow_icon.png" alt="Down-Arrow" height="60px" />
    <span>
      <strong>컴파일(Compile)</strong>
    </span>
    <br />
    <br />
  </div>
  <div>
    <img src="./images/chrome_logo.png" alt="Chrome" height="100px" />
    <img src="./images/css_logo.png" alt="CSS" height="90px" />
  </div>
<div>

> 프로젝트에서 Sass 문법을 사용해 코딩을 진행하게 되면 **컴파일(Compile)** 을 통해 표준 CSS로 변환하여 사용자 브라우저에서 동작할 수 있게 합니다.

<br />

### Sass와 SCSS의 차이점은?

**SCSS**는 Sass(Syntactically Awesome Style Sheets)의 3버전에서 새롭게 등장하였습니다.  
**SCSS**는 CSS 구문과 완전히 호환되도록 하여 `CSS와 거의 같은 문법으로 Sass 기능을 지원`합니다.

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

- **CSS**

```css
.container {
  width: 100px;
  height: 100px;
}
.container h1 {
  color: blue;
  font-size: 12px;
}
```

<br />

## 주석

**SCSS**에서는 두 가지 주석 처리 방법이 있습니다.

**첫 번째**, 표준 CSS 주석 처리 형식 `/* comment */`  
**두 번째**, SCSS에서의 주석 처리 형식 `// comment`

> 표준 CSS 주석 처리 형식인 `/* comment */` 사용 시 SCSS에서 CSS로 컴파일된 후에도 주석 라인이 유지됩니다. 하지만 SCSS 주석 처리 형식인 `// comment`을 사용하면 컴파일 후 주석 라인이 사라집니다.

- **SCSS**

```scss
.container {
  h1 {
    background-color: yellow;
    /* color: blue; */
    // font-size: 12px;
  }
}
```

- **CSS** (Compiled to)

```css
.container h1 {
  background-color: yellow;
  /* color: blue; */
}
```

<br />

## 중첩

SCSS는 CSS와는 다르게 중첩 기능을 사용할 수 있습니다.

> 상위 선택자의 반복을 피하고 복잡한 구조를 편리하게 작성할 수 있는 이점이 있습니다.

- **HTML**

```html
<div class="container">
  <ul>
    <li>
      <div class="name">Park Jeong-hwan</div>
    </li>
    <li>
      <div class="email">jeonghwan.dev@gmail.com</div>
    </li>
  </ul>
</div>
```

- **SCSS**

```scss
.container {
  ul {
    li {
      font-size: 20px;
      .name {
        color: blue;
      }
      .email {
        color: orange;
      }
    }
  }
}
```

- **CSS** (Compiled to)

```css
.container ul li {
  font-size: 20px;
}
.container ul li .name {
  color: blue;
}
.container ul li .email {
  color: orange;
}
```

<br />

## 상위 선택자 참조

중첩 안에서의 `&`키워드는 **상위(부모) 선택자를 참조하여 치환**합니다.

- **SCSS**

```scss
.btn {
  font-size: 16px;
  &.active {
    color: blue;
  }
}

.list {
  li {
    &:last-child {
      margin-right: 0;
    }
  }
}
```

- **CSS** (Compiled to)

```css
.btn {
  font-size: 16px;
}
.btn.active {
  color: blue;
}

.list li:last-child {
  margin-right: 0;
}
```

- **SCSS**

```scss
.btn {
  &--blue {
    color: blue;
  }
  &--yellow {
    color: yellow;
  }
  &--green {
    color: green;
  }
}
```

- **CSS** (Complied to)

```css
.btn--blue {
  color: blue;
}
.btn--yellow {
  color: yellow;
}
.btn--green {
  color: green;
}
```

- **SCSS**

```scss
.fs {
  &-small {
    font-size: 12px;
  }
  &-medium {
    font-size: 14px;
  }
  &-large {
    font-size: 16px;
  }
}
```

- **CSS** (Compiled to)

```css
.fs-small {
  font-size: 12px;
}
.fs-medium {
  font-size: 14px;
}
.fs-large {
  font-size: 16px;
}
```

<br />

## 중첩된 속성

`font-`, `margin-`, `padding` 등과 같이 동일한 네임 스페이스를 가지는 속성들을 아래와 같이 **중첩된 속성 형식으로 사용**할 수 있습니다.

- **SCSS**

```scss
.container {
  font: {
    size: 10px;
    weight: bold;
    family: sans-serif;
  }
  margin: {
    top: 10px;
    bottom: 20px;
  }
  padding: {
    top: 10px;
    bottom: 10px;
    left: 20px;
    right: 20px;
  }
}
```

- **CSS** (Compiled to)

```css
.container {
  font-size: 10px;
  font-weight: bold;
  font-family: sans-serif;
  margin-top: 10px;
  margin-bottom: 20px;
  padding-top: 10px;
  padding-bottom: 10px;
  padding-left: 20px;
  padding-right: 20px;
}
```
