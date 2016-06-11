스프링 시큐리티 메뉴얼
====================

## 문서생성을 위한 사전요구사항
* 루비RUBY 설치되어 있어야 함
* [bundler](http://bundler.io/) 설치되어 있어야 함

## 문서빌드
```
$ bundle install
$ ./build.sh
```

## 아스키독 작성법 간단한 설명
* [AsciiDoc Syntax Quick Reference](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/)

### 문서 헤더와 속성
```
= My Document's Title
Doc Writer <doc.writer@asciidoctor.org>
v1.0, 2014-01-01
:toc:
:imagesdir: assets/images
:homepage: http://asciidoctor.org

My document provides...
```

### 머릿말(헤더,header) 표현
```
= Header1 // <h1> 마크다운 # 과 동일
== Header2 // <h2> 마크다운 ## 과 동일
=== Header3 // <h3> 마크다운 ### 과 동일
==== Header4 // <h4> 마크다운 #### 과 동일
===== Header5 // <h5> 마크다운 ##### 과 동일
====== Header6 // <h6> 마크다운 ###### 과 동일
```

### 텍스트 포멧
```
글자 중간에 사용할 때는 이중표현식으로 사용

_italic phrase_  // 이탤릭

__i__talic le__tt__ers // 부분 이텔릭

*bold phrase* // 굵게

**b**old le**tt**ers // 부분 굵게

*_bold italic phrase_*

**__b__**old italic le**__tt__**ers

`monospace phrase` and le``tt``ers  // 코드 표현: 코드표현

`_monospace italic phrase_` and le``__tt__``ers

`*monospace bold phrase*` and le``**tt**``ers

`*_monospace bold italic phrase_*` and le``**__tt__**``ers
```

### 위첨자, 아래첨자
```
^super^script phrase // 위첨자

~sub~script phrase // 아래첨자
```

### 큰따옴표, 작은따옴표 표현
```
'`single curved quotes`'

"`double curved quotes`"

Olaf`'s desk was a mess.
```

### 문서 내에서 다른 문서 포함
```
= Reference Documentation
Lead Developer

This is documentation for project X.

include::basics.adoc[]

include::installation.adoc[]

include::example.adoc[]
```

### 페이지 나눔
```
<<<
```

### 목록 표현
```
* Edgar Allen Poe
* Sheri S. Tepper
* Bill Bryson
```

> 목록의 앞뒤로 빈줄이 필요함

### 목록의 깊이 표현
```
* level 1
** level 2
*** level 3
**** level 4
***** level 5
* level 1
```

### 체크리스트
```
- [*] checked
- [x] also checked
- [ ] not checked
-     normal list item
```

### 순서 목록
```
. Step 1
. Step 2
. Step 3
```

### 순서목록 깊이 표현
```
. level 1
.. level 2
... level 3
.... level 4
..... level 5
. level 1
```

### 링크
```
link:url[표시글자]
link:http://example.org/?q=%5Ba%20b%5D[URL with special characters]
```

### 이메일과 IRC
```
devel@discuss.arquillian.org

mailto:devel@discuss.arquillian.org[Discuss Arquillian]

mailto:devel-join@discuss.arquillian.org[Subscribe, Subscribe me, I want to join!]

irc://irc.freenode.org/#asciidoctor
```


### 이미지
```
image::sunset.jpg[]

image::sunset.jpg[Sunset]

[[img-sunset]]
image::sunset.jpg[caption="Figure 1: ", title="A mountain sunset", alt="Sunset", width="300", height="200", link="http://www.flickr.com/photos/javh/5448336655"]

image::http://asciidoctor.org/images/octocat.jpg[GitHub mascot]
```

### 앵커
```
[[bookmark-a]]Inline anchors make arbitrary content referenceable.

anchor:bookmark-b[]Use a cross reference to link to this location.

[[bookmark-c,last paragraph]]The xreflabel attribute will be used as link text in the cross-reference link.
```

### 앵커로 이동
```
See <<paragraphs>> to learn how to write paragraphs.

Learn how to organize the document into <<section-titles,sections>>.
```

### 코드, 코드 문법하이라이트 없음
```
.Gemfile.lock
----
GEM
  remote: https://rubygems.org/
  specs:
    asciidoctor (0.1.4)

PLATFORMS
  ruby

DEPENDENCIES
  asciidoctor (~> 0.1.4)
----
```

### 코드, 코드 문법하이라이트 있음
```
[[app-listing]]
[source,ruby]
.app.rb
----
require 'sinatra'

get '/hi' do
  "Hello World!"
end
----
```


### 노트
```
[NOTE]
====
An admonition block may contain complex content.

.A list
- one
- two
- three

Another paragraph.
====
```

### 인용
```
[quote, Abraham Lincoln, Address delivered at the dedication of the Cemetery at Gettysburg]
____
Four score and seven years ago our fathers brought forth
on this continent a new nation...
____
```

### 주석
```
// 한줄 주석


//// 여러줄 주석
A multi-line comment.

Notice it's a delimited block.

영어 번역시 원문을 여러 줄 주석으로 처리 후 번역
////
여러줄 주석
```

### 테이블
```
.Table Title
|===
|Name of Column 1 |Name of Column 2 |Name of Column 3   // 테이블 헤더

|Cell in column 1, row 1
|Cell in column 2, row 1
|Cell in column 3, row 1

|Cell in column 1, row 2
|Cell in column 2, row 2
|Cell in column 3, row 2
|===
```
