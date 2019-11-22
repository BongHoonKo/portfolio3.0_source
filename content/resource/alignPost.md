+++
#카테고리
series = [
    "test",
    "series Test"
]

#작성자
authors = [
    "",
]

#제목
title = "Align Post"

#설명
description = "Blog에서 이용한 블로그 포스트 정렬 코드 정리"

#공개: false / 비공개: true
draft = false

#썸네일 이미지 URL
image = ""

comments = true
date = 2019-10-29T17:51:54+09:00
+++

<!-- 게시글 내용 -->
<style>
    .box-align__list {
        width: 100%;
        position: relative;
        text-align: center;
    }

    .box-align__list > li {
        position: absolute;
        top: 0;
        -webkit-transition-duration: 0.3s;
        transition-duration: 0.3s;
        padding-bottom: 30px;
    }

    .box-align__list > li:first-child .box-align__content {
        height: 180px;
    }
    .box-align__list > li:nth-child(2) .box-align__content {
        height: 300px;
    }
    .box-align__list > li:nth-child(3) .box-align__content {
        height: 250px;
    }
    .box-align__list > li:nth-child(4) .box-align__content {
        height: 400px;
    }
    .box-align__list > li:nth-child(5) .box-align__content {
        height: 250px;
    }
    .box-align__list > li:last-child .box-align__content {
        height: 200px;
    }

    .box-align__list > li .box-align__content {
        display: flex;
        align-items: center;
        justify-content: center;
        border: 1px solid #333;
        background-color: #eaeaea;
    }

    @media all and (min-width: 1200px) {
        .box-align__list > li:nth-of-type(3n+1) {
            clear: both;
        }
        .box-align__list > li:nth-of-type(3n+2) {
            left: 33.333%;
        }
        .box-align__list > li:nth-of-type(3n) {
            right: 0;
        }
    }

    @media all and (max-width: 1199px) {
        .box-align__list > li:nth-of-type(2n) {
            right: 0;
        }
        .box-align__list > li:nth-of-type(2n+1) {
            left: 0;
        }
    }

    @media all and (max-width: 767px) {
        .box-align__list {
            height: auto !important;
        }
        .box-align__list > li {
            position: static !important;
        }
    }
</style>

<article class="box-align">
        <ul class="box-align__list row">
            <li class="col-lg-4 col-sm-6"> 
                <div class="box-align__content">CONTENT 1</div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content">CONTENT 2</div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content">CONTENT 3</div>
            </li>
            <li class="col-lg-4 col-sm-6"> 
                <div class="box-align__content">CONTENT 4</div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content">CONTENT 5</div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content">CONTENT 6</div>
            </li>
        </ul>
</article>

### HTML
{{<highlight html>}}
    <article class="box-align container">
        <ul class="box-align__list row">
            <li class="col-lg-4 col-sm-6"> 
                <div class="box-align__content"> CONTENT 1 </div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content"> CONTENT 2 </div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content"> CONTENT 3 </div>
            </li>
            <li class="col-lg-4 col-sm-6"> 
                <div class="box-align__content"> CONTENT 4 </div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content"> CONTENT 5 </div>
            </li>
            <li class="col-lg-4 col-sm-6">
                <div class="box-align__content"> CONTENT 6 </div>
            </li>
        </ul>
    </article>
{{</highlight>}}

<br/>

### CSS
{{<highlight css>}}
    .box-align__list {
        width: 100%;
        position: relative;
        text-align: center;
    }

    .box-align__list > li {
        position: absolute;
        top: 0;
        -webkit-transition-duration: 0.3s;
        transition-duration: 0.3s;
        padding-bottom: 30px;
    }

    .box-align__list > li:first-child .box-align__content {
        height: 180px;
    }
    .box-align__list > li:nth-child(2) .box-align__content {
        height: 300px;
    }
    .box-align__list > li:nth-child(3) .box-align__content {
        height: 250px;
    }
    .box-align__list > li:nth-child(4) .box-align__content {
        height: 400px;
    }
    .box-align__list > li:nth-child(5) .box-align__content {
        height: 250px;
    }
    .box-align__list > li:last-child .box-align__content {
        height: 200px;
    }

    .box-align__list > li .box-align__content {
        display: flex;
        align-items: center;
        justify-content: center;
        border: 1px solid #333;
        background-color: #eaeaea;
    }

    @media all and (min-width: 1200px) {
        .box-align__list > li:nth-of-type(3n+1) {
            clear: both;
        }
        .box-align__list > li:nth-of-type(3n+2) {
            left: 33.333%;
        }
        .box-align__list > li:nth-of-type(3n) {
            right: 0;
        }
    }

    @media all and (max-width: 1199px) {
        .box-align__list > li:nth-of-type(2n) {
            right: 0;
        }
        .box-align__list > li:nth-of-type(2n+1) {
            left: 0;
        }
    }

    @media all and (max-width: 767px) {
        .box-align__list {
            height: auto !important;
        }
        .box-align__list > li {
            position: static !important;
        }
    }
{{</highlight>}}

<br/>

### JS
{{<highlight javascript>}}
    $(window).on("load resize", () => {
        let widWidth = window.innerWidth;
        if(widWidth <= 1199) {
            setTimeout(function(){
                postAlign(2);
            },200);
        }
        else {
            setTimeout(function(){
                postAlign(3);
            },200);
        }
    });

    function postAlign(num) {
        let heightArray = [];
        let $targetElm = ".box-align__list > li:nth-of-type(";
        for (let i = 0; i < num ; i++) {
            let $box = $($targetElm + num + "n+" + i + ")");
            let boxTarget = $targetElm + num + "n+" + i + ")";
            if( i === 0 ) {
                $box = $($targetElm + num + "n)");
                boxTarget = $targetElm + num + "n)";
            }
            let boxHeight = $box.eq(0).outerHeight();
            for (let n = 1; n < $box.length; n++) {
                    let prevHeight = 0;
                    $box.eq(n).prevAll(boxTarget).each(function () {
                    prevHeight += $(this).outerHeight();
                });
                $box.eq(n).css("top", prevHeight + "px");
                boxHeight += $box.eq(n).outerHeight();
            }
            $box.eq(0).css("top", 0);
            heightArray.push(boxHeight);
        }
        let maxHeight = Math.max.apply(null, heightArray);
        $(".box-align__list").css("height", maxHeight + 20 + "px");
    }
{{</highlight>}}