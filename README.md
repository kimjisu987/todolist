<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=300&section=header&text=Todo%20List&fontSize=90" />    

# ✨ 프로젝트 주제
투두리스트 개인 작업
<br/><br/>
# 👩 역할
기획, 디자인, 구현
<br/><br/>
# 🚩 기여도
 단독 작업 `100%`
<br/><br/>
# 🕑 기간
 2024.09.15 - 2024.09.19
<br/><br/>
# 💻 개발도구
`VS Code` `GitHub` `Illustrator`
<br/><br/>
# ⌨ 기술스택
<img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=white"/> <img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=CSS3&logoColor=white"/> <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=JavaScript&logoColor=white"/>
<br/><br/>
# 📝 리뷰
 해당 프로젝트는 학원 수업의 일환으로 리액트를 사용하여 구현한 투두 리스트 애플리케이션입니다. 이전에 자바스크립트, PHP, 제이쿼리를 활용하여 개발한 기존 시스템을 **리액트 문법으로 재구성**하였으며, 이를 통해 컴포넌트를 개별적으로 관리하는 방식으로 전환했습니다.
 디자인 과정은 구상 단계에서부터 구현까지 전적으로 담당하였으며, 사용자 경험을 고려하여 **라이트 모드와 다크 모드**를 주요 기능으로 설정하였습니다. 또한, 박스 섀도우를 효과적으로 활용하여 시각적으로 매력적인 인터페이스를 구현하였습니다.
 이 프로젝트는 **리액트의 컴포넌트 기반 구조**를 통해 코드의 재사용성과 유지보수성을 높이는 한편, 사용자 친화적인 디자인을 통해 사용자의 편의성을 극대화하고자 하였습니다.
 이와 같은 경험은 리액트의 생태계에 대한 깊은 이해를 바탕으로, 웹 애플리케이션 개발에 있어 실질적인 역량을 향상시키는 데 기여하였습니다.
<br/><br/>
# 📁 컴포넌트 관리
> ### 📁 Colortoggle.jsx
> 라이트모드 / 다크모드를 관리 하기 위한 파일

> ### 📁 Form.jsx
> 리스트 입력을 위한 Form 파일

> ### 📁 TodoItem.jsx
> 리스트 체크/삭제 관리 하기 위한 파일

> ### 📁 TodoItemList.jsx
> 리스트를 표시하기 위한 파일

> ### 📁 TodoItemTemplate.jsx
> 전체적인 템플릿을 관리하기 위한 파일

<br/><br/>
# `</>` 레이아웃 구성 코드
+ 전체 코드를 불러오기 위한 템플릿 파일
```jsx
<main className="todo_list_template">
  <div className="title">
    <div className="date">{titleDate}</div>
    <Colortoggle />
  </div>      
  <section className="form_wrapper">
    {form}
  </section>
  <section className="todos_wrapper">
    {children}
  </section>
</main>
```
<br/><br/>
# `</>` 다크/라이트 모드 구현 코드
+ `useState`를 활용하여 상태관리
+ 테마 변경시 `setAttribute` 함수를 활용하여 속성 변경
### jsx
```jsx
<div>
  <div id="color_toggle">
    <input
      type="checkbox"
      id="switch"
      name="mode"
      checked={isDarkMode} 
      onChange={handleToggle}
      />
    <label for="switch">&nbsp;</label>
  </div>
</div>
```
### JavaScript
```javascript
const [isDarkMode, setIsDarkMode] = useState(() => {
  // 초기값을 localStorage에서 가져오거나 기본값 설정
  return localStorage.getItem('color_toggle') === 'dark';
});

useEffect(() => {
  // 테마 변경 시 HTML의 color_toggle 속성 업데이트
  document.documentElement.setAttribute('color_toggle', isDarkMode ? 'dark' : 'light');
  // localStorage에 현재 테마 저장
  localStorage.setItem('color_toggle', isDarkMode ? 'dark' : 'light');
}, [isDarkMode]);

const handleToggle = () => {
  setIsDarkMode(prevMode => !prevMode);
};
```
