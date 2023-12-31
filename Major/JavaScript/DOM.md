

---
## DOM이란?

Document Object Model의 줄임말이다.

- id, class, tag
    
    ### getElementById()
    
    - **getElememtById**는 JS에서 HTML에 있는 태그의 id를 사용해서 가져오는 방식이다.
    
    ```jsx
    const titile = document.getELementById('title');
    ```
    
    위의 코드는 title이라는 id를 가지고 있는 태그를 가져오는 것이다.
    
    ### getElementsByClassName()
    
    - **getElementsByClassName**는 JS에서 HTML에 있는 태그들의 class를 사용해서 가져오는 방식이다.
    
    ```jsx
    const title = document.getElementsByClassName('title_class');
    ```
    
    위의 코드는 title_class라는 class를 가지고 있는 태그들을 가져오는 것이다,
    
    ## getElementsByTagName()
    
    - **getElementsByTagName**는 JS에서 HTML에 있는 태그를 가져오는 것이다.
    
    ```jsx
    const title - document.getElementsByTagName('h2');
    ```
    
    위의 코드는 모든 `<h2>`태그들을 가져오는 것이다.
    
- ### querySelector(), qureySelectorAll()
    
    ## querySelector()
    
    - querySelector()은 getElementId, getElementsClassName, getElementsTagName를 사용할 때
    - id에서 class로 class에서 tag등등으로 넘어갈 경우에 Id나 ClassName이나 TagName으로 바꾸는 귀찮음을 없애주는데 도움을 주는 것이다.
    
    ```jsx
    const title = documentSelector('#title');
    const title = documentSelector('.title_class');
    const title = documentSelector('h2');
    ```
    
    이러면 모든 id나 class나 tag들을 선택을 할 수 있다.
    
    <aside> 💡 단, id는 #을 앞에다가 class는 .을 앞에다가 무조건 찍는다.
    
    </aside>
    
    ### querySelectorAll()
    
    - querySelectorAll()도 querySelector()과 쓰는 방법은 똑같다.
    - 하지만 다른 점은 인자로 지정한 선택자와 일치하는 요소들을 모두 선택을 한다.
    - 그러니까 다수의 요소들을 배열처 가져오기 위해서 사용이 되는 메소드이다.
- HTML 요소의 속성을 변경하는 방법
    
    ```jsx
    const title = documentSelector('#title');
    
    title.innerText = '안녕하세요!!';
    title.style.color = 'blue';
    ```
    
    이런식으로 바꿀 수 있다.
    
- Events
    
    Events란?
    
    마우스를 클릭을 하거나 올려놓은 것등등을 통틀어 말하는 것
    
    event를 listen하는 방법
    
    ```jsx
    const title = document.getElementsByTagName("h1")
    
    function mouseClick() {
        title.style.color = "blue"
    }
    
    title.addEventListener("click", mouseClick)
    
    mouseClick()
    ```