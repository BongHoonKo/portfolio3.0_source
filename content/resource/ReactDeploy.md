+++
#카테고리
series = [
    "React.js",
    "Github Page"
]

#작성자
authors = [
    "",
]

#제목
title = "React App GitHub 페이지 배포하기"

#설명
description = "React 앱을 개인 Github 페이지에 배포하는 방법 정리"

#공개: false / 비공개: true
draft = false

comments = true
date = 2019-11-22T09:50:23+09:00
+++

<!-- 게시글 내용 -->

### 1. package.json 파일 하단에 **"hompage":"http://깃헙주소/저장소"** 추가

--------------------------------

-package.json-

{{<highlight JavaScript>}}
    ...

    "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  },

  "homepage": "https://BongHoonKo.github.io/ReactApp_K"

{{</highlight>}}

<br/><br/>

### 2. yarn add --dev gh-pages

--------------------------------

-cmd-

{{<highlight Batchfile>}}
 > yarn add --dev gh-pages
{{</highlight>}}

<br/><br/>

### 3. **"predeploy":"yarn build" , "deploy":"gh-pages -d build" 추가**

--------------------------------

-package.json-

{{<highlight JavaScript>}}
    ...

    "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",

    "predeploy": "yarn build",
    "deploy": "gh-pages -d build"

  },
{{</highlight>}}

<br/><br/>

### 4. github 연결

--------------------------------

-cmd-

{{<highlight Batchfile>}}
 > git remote add origin https://github.com/BongHoonKo/ReactApp_K.git

 > git push -u origin master
{{</highlight>}}

<br/><br/>

### 5. 배포

--------------------------------

-cmd-

{{<highlight Batchfile>}}
 > yarn run deploy
{{</highlight>}}