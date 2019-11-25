+++
#카테고리
series = [
    "React.js",
    "Tip"
]

#작성자
authors = [
    "",
]

#제목
title = "React Tip 정리 1"

#설명
description = "React 작업 중에 궁금해서 그때끄때 찾았던 내용을 정리해놓은 포스트"

#공개: false / 비공개: true
draft = false

comments = true
date = 2019-11-25T16:59:18+09:00
+++

<!-- 게시글 내용 -->

### 1. 조건에 따라 className 추가
-----------------------------------

{{<highlight React>}}
    <button className={"btn " + (this.state.btnActive ? "active" : "")}> ...</button>
{{</highlight>}}

<br/>

### 2. map 반대로
-------------------

{{<highlight React>}}
    {test.slice(0).reverse.map( data => { ... })}
{{</highlight>}}

<br/>

### 3. setState 완료 후 실행할 Callback 함수 설정 방법
-----------------------------------------------

{{<highlight React>}}
    this.setState({
        test : "test"
        ...
    }, () => { ...something });
{{</highlight>}}

<br/>

### 4. Event에 인자값 넘겨주기
-------------------------------------

{{<highlight React>}}
    <button onClick={ () => this.btnClick(arg1, arg2) }> Click </button>
{{</highlight>}}

<br/>

### 5. render 안에서 Switch Statement 사용
---------------------------------------------

{{<highlight React>}}
    render() {
        return (
            <div>
                {( () => {
                    switch(test) {
                        case 1 : return <Test1 />; break;
                        case 2 : return <Test2 />; break;
                        ...
                    }
                } )}
            </div>
        );
    }
{{</highlight>}}

<br/>

### 6. For Loop를 통해 렌더링
-------------------------------

{{<highlight React>}}
    render() {
        const row = [];
        for(let i=1; i<10; i++) {
            row.push(<li> { i } </li>);
        }
        return (
            <ul>
                { $row }
            </ul>
        );
    }
{{</highlight>}}