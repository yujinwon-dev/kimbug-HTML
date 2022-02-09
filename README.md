[toc]

# HTML은 재밌다 강의 정리

## 1.

### HTML이 왜 중요한가요?

- URL을 입력하면

- -> 해당 페이지를 보기 위해 필요한 리소스를 요청하고

- -> 서버가 리소스를 보내줌(HTML, CSS, JS 등등)

  ![image-20220202233855297](README.assets/image-20220202233855297.png)

- 그래서 FE에서 HTML, CSS, JS를 공부하는 것

- 웹 페이지에 보이는 모든 것들은 **기승전 HTML 태그의 결과물**. 그래서 HTML부터 탄탄히 쌓아가야 함!

- **문서의 구조**와 **정보의 위계**가 명확하게 보이는 HTML 코드를 작성하자! (Semantic Markup)

- Semantic하게 작성하면 검색 엔진 최적화(SEO)에도 도움이 됨



### HTML을 시맨틱하게 작성해야 하는 이유

- `<div>` 쳐발쳐발 하지 말자.. 다채로운 태그를 쓰면 나에게도 동료에게도 유익함

- 시맨틱하지 않다면...

  ```html
  <p>제목입니다</p>
  <p>
      <p>리스트 요소1</p>
      <p>리스트 요소2</p>
      <p>리스트 요소3</p>
  </p>
  ```

<br>

## 2.


### 제목과 문단 Headings and Paragraph

- 제목에 해당하는 부분에는 Heading Tag(`<h1>`, `<h2>` 등)
- 문단에 대해서는 `<p>` -> paragrahph



### 강조 Emphasis

- 강조하고자 하는 부분에서 사용. p 태그 내부에서도 가능. 둘 중에 끌리는 걸로 쓰면 됨.
- 글씨가 두껍다 두껍지 않다보다도 브라우저한테 이 부분이 중요하다고 알려줬다는 게 중요

- `<em></em>`: italic
- `<strong></strong>`: bold

+) `<br />`: break 태그



### 링크 Anchor

- 필수 어트리뷰트 href: hypertext reference(문서 주소값)

- href 주소값 표기 방법

  1. 웹 URL(절대/상대)

     ```html
     <a href="https://www.google.com/">Google</a>
     <a href="./index.html">Google</a>
     ```

  2. 페이지 내 이동

     - 이동하고자 하는 곳의 id값을 적어주면 됨

     ```html
     <a href="#hello">To Hello</a>
     ```

  3. 메일 쓰기

     ```html
     <a href="mailto:메일주소"></a>
     ```

     ![image-20220203231747878](C:\Users\multicampus\Desktop\wonyu\works\fun-HTML\README.assets\image-20220203231747878.png)

  4. 전화 걸기

     ```html
     <a href="tel:전화번호"></a>
     ```

- 또다른 어트리뷰트: target

  - 새로운 탭에서 열렸으면 좋겠을 때

  ```html
  <a target="_blank">새 탭에서 열기</a>
  ```




### 이미지 Image

- 필수 어트리뷰트
  - src: 경로 or 주소
  - alt: alternate text - 이미지가 안 뜰 때 대체 텍스트가 있어야 사용자 경험 더 나아짐. 스크린리더를 사용할 때도 해당 값이 사용됨



### 목록 List

- 2가지 종류의 리스트
  - ol: ordered list(순서가 중요한 목록)
  - ul: unordered list(순서가 중요하지 않은 목록)
  - 두 태그의 자식 요소는 **무조건 li만 가능**
  
- 리스트 내부의 항목
  - li: list item

- 리스트 스타일 떼기

  ```html
  <ul style="list-style-type: none;">
    <li>
      웹 개발자
    </li>
    ...
  </ul>
  ```



### 정의 목록 Description List

- 용도

	1. 용어를 정의할 때
	1. key-value로 정보를 제공할 때

- 관련 태그들

  - dl: description list -> ul, ol같은 느낌
  - dt: key값
  - dd: description data -> key값에 대한 data
  - +) dfn: definition -> dt를 좀 더 구체적으로 정의하고 싶을 때

- dl 태그 내에서 하나의 정의 세트를 div로 묶어주는 것도 가능 (**div로만 가능!**)

  ![image-20220205231305704](C:\Users\multicampus\Desktop\wonyu\works\fun-HTML\README.assets\image-20220205231305704.png)

- dd, dt를 여러개 쓸 수 있지만 dt - dd - dt 이런 식으로 번갈아 쓸 수는 없음



### 인용 Quotations

- 관련 태그

  - blockquote: 어떤 문단이나 내용 전체가 인용문일 때. q보다 자주 사용됨
  - q: 문장 내에 살짝 들어가는 인용문. 쌍따옴표가 생김

- 예시

  ```html
  <!-- 출처 url: cite 어트리뷰트에 기재 -->
  <blockquote cite="https://www.google.com/">
    우리가 겪을 수 있는 가장 아름다운 체험은 신비다. <br/>
    신비는 모든 참 예술과 과학의 근원이다.
    <!-- 출처: cite 태그 -->
    <cite>
      알버트 아인슈타인
    </cite>
  </blockquote>
  ```




### 흑마법 Div & Span

- 아무런 의미가 없음. css를 하면서 요소를 묶을 때 유용하게 쓰임.
- div: 어디에나 쓸 수 있음
- span: text level에서 어디든.. 텍스트의 일부를 그루핑할 때 많이 쓰임
- 정말 아무리 생각해도 떠오르는 의미 있는 태그가 없을 때 사용하려고 노력



### Form(1) - Form

- 사용자로부터 인풋을 받기 위한 태그
- 문법 주의! 함께 작성해야 할 어트리뷰트
  - action="API 주소"
  - method="GET|POST"



### Form(2) - Input

- 인풋 태그 사용시 type 어트리뷰트 필수

  ```html
  <input type="?" />
  ```

  - text, number, email, password, tel, file, radio..

- 타입 상관 없이 작성 가능한 어트리뷰트

  - `placeholder=""`
  - `minlength/maxlength=""`
  - `required`
  - `disabled`
  - `value=""`: 기본적으로 입력되어 있는 값

- `type="text"`
  - 한 줄 정도 분량의 인풋을 받을 수 있는 기본적인 형태
- `type="email"`
  - 인풋에 `@` 있는지 유효성 검사
- `type="password"`
- `type="url"`
  - url 간단한 유효성 검사
- `type="number"`
  - 문자 입력 안 됨.
  - 어트리뷰트
    - min
    - max
- `type="file"`
  - Choose File
  - 어트리뷰트
    - accept: 허용하고자 하는 파일 확장자 제한 ex)`accept=".png, .jpg"`



### Form(3) - Label

- 인풋에 대한 이름, 즉 라벨을 달아준다는 뜻. 폼 양식에 이름을 붙이는 태그

- for을 작성할 경우 라벨을 클릭하면 인풋에 focus됨. 사용성 up

- 문법 주의

  ```html
  <!-- 해당하는 인풋의 id를 라벨의 for에 적어줌 -->
  <!-- for을 작성하면 라벨을 클릭할 때 인풋에 focus됨. 사용성 up -->
  <label for="username"></label>
  <input type="text" id="username"/>
  ```



### Form(4) - Radio & Checkbox

- radio: 여러 개 중에 하나만 선택

  - 필수 어트리뷰트

    - name
    - value

  - `<input type="radio" />`에서 name attribute 설정해줘야 서로 연관되어 있다는 것을 파악 가능

    ```html
    <input type="radio" name="subscription" id="subscribed">
    <label for="subscribed">구독중</label>
    <input type="radio" name="subscription" id="unsubscribed">
    <label for="unsubscribed">미구독</label>
    ```

  - name, value가 key, value 형태로 서버에 전달됨 (url에서 확인 가능) -> value를 각각 다르게 지정해줘야 서버에서도 어떤 항목이 선택됐는지 확인 가능. 숫자든 문자든 가능.

    ```html
    <form action="" method="GET">
        <input type="radio" name="subscription" value="subscribed" id="subscribed">
        <label for="subscribed">구독중</label>
        <input type="radio" name="subscription" value="unsubscribed" id="unsubscribed">
        <label for="unsubscribed">미구독</label>
        <button>Submit</button>
    </form>
    ```

- checkbox: 여러 개 중에 다중 선택 가능

  ```html
  <form action="" method="GET">
      <input type="checkbox" id="html" name="skills" value="html">
      <label for="html">HTML</label>
      <input type="checkbox" id="css" name="skills" value="css">
      <label for="css">CSS</label>
      <input type="checkbox" id="js" name="skills" value="js">
      <label for="js">JavaScript</label>
      <button>Submit</button>
  </form>
  ```

  