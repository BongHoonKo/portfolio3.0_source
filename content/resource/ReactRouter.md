+++
#카테고리
series = [
    "React.js",
    "react-router-dom"
]

#작성자
authors = [
    "",
]

#제목
title = "React 라우터 세팅"

#설명
description = "react-router-dom을 이용한 간단한 라우팅 세팅 방법"

#공개: false / 비공개: true
draft = false

comments = true
date = 2019-11-24T11:12:42+09:00
+++

<!-- 게시글 내용 -->
### 1. Install react-router-dom
---------------------------------------

{{<highlight Batchfile>}}
 > npm install react-router-dom
{{</highlight>}}

<br/>

### 2. HashRouter
------------------------------------------

BrowserRouter, HashRouter 등 Router의 종류가 몇개 있지만, GitHub 페이지에 배포를 하려고하니, HashRouter를 통해 설정을 해야만 페이지가 정상적으로 렌더링 됐음. 

BrowserRouter와 HashRouter의 정확한 사용법에 관해서는 추후에 추가로 공부 예정

<br/>
-App.js-
{{<highlight React>}}
    import React , {Component} from 'react';
    import Main from './Main';

    import { HashRouter as Router } from 'react-router-dom';

    class App extends Component {
        render() {
            return (
                <div className="App">
                    <Router>
                        <Main />
                    </Router>
                </div>
            );
        }
    }
{{</highlight>}}

<br/>
-Main.js-
{{<highlight React>}}
    import React , {Component} from 'react';
    import { Switch, Route } from 'react-router-dom';

    import Home from './Home';
    import Mypage from './Mypage';

    class Main extends Component {
        render() {
            return(
                <div>
                    <Switch>
                        <Route exact path='/' component={Home}></Route>
                        <Route path='/Mypage' component={Mypage}></Route>
                    </Switch>
                </div>
            );
        }
    }
{{</highlight>}}

> **Route 태그에 ```exact``` props가 사용된 이유 :** <br/><br/> React Router는 ```path``` 경로와 현재 브라우저의 URL 경로를 비교하는데,<br/>
현재 URL 경로 값이 Route 태그의 ```path``` 값과 전체가 아닌 앞부분만 일치해도 매치되는 것으로 간주함.<br/>
따라서 ```path```가 ```/``` 일 경우 ```/```로 시작하는 모든 경로가 매치됨.
<br/><br/>
하지만 ```exact```를 붙여주면 URL 경로 값이 ```path```와 완벽히 전체가 일치해야 매치하는 것으로 처리를 해줌으로써, 의도치 않게 Home 컴포넌트가 URL 경로와 상관없이 항상 보여지게 되는 것을 막아준다.

<br/>

### 3. Route 안의 Component에 props 넘겨주는 방법
----------------------------------------------------

{{<highlight React>}}
    <Route exact path="/" render={ props => <Test test={this.props.test} /> }></Route>
{{</highlight>}}


<br/>

### 4. Router + map 으로 상세페이지 라우팅
-------------------------------------------
-Test.js-
{{<highlight React>}}
    class Test extends Component {
        state = {
            "testData" : [
                {
                    "id" : 1,
                    "title" : "test 1",
                    "txt" : "test text 1"
                },
                {
                    "id" : 2,
                    "title" : "test 2",
                    "txt" : "test text 2"
                },
                {
                    "id" : 3,
                    "title" : "test3",
                    "txt" : "test text 3"
                }
            ]
        }
    }

    render() {
        const { testData } = this.state;
        return (
            <div>
                <Switch>
                    {testData.map(testData => {
                        return <Route exact path={'/test/' + testData.id} 
                                render={ props => <TestDetail data={testData}/> }></Route>;
                    })}
                </Switch>
            </div>
        );
    }
{{</highlight>}}

> ```path={'/test/:id'}``` 로 대체가능

<br/>

-TestDetail.js-
{{<highlight React>}}
    class TestDetail extends Component {
        render() {
            const { data } = this.props;
            return (
                <div>
                    // URL이 http://localhost:3000/test/1 이라면
                    <em>{ data.id }</em> // 1
                    <h3>{ data.title }</h3> // test 1
                    <p>{ data.txt }</p> // test text 1
                </div>
            );
        }
    }
{{</highlight>}}

<br/>