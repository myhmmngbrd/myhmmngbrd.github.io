---
title: GitHub Pages 폴더 구조와 설명
categories: [Git, GitHub Pages]
---

<a href="https://docs.github.com/en/pages/quickstart">공식 문서</a>를 따라 블로그를 개설하면, 루트 폴더에 아래와 같은 폴더와 파일들이 생성된다.

<pre class="tcode">
_posts
_site
_config.yml
.gitignore
404.html
about.markdown
gemfile
gemfile.lock
index.markdown
RAEDME.md
</pre>

# 1. _posts 폴더

블로그의 포스트를 수동으로 업로드하는 폴더. 마크다운 문서(.md)로 작성한다.

마크다운 문서의 문법은 html과 유사하다. 헤더 부분에 "---"로 둘러쌓인 메타 정보를 넣는다.

```abc
---
title: GitHub Pages 폴더 구조와 설명
category: "GitHub Pages"
date: 2021-11-11
---
*content*
```
```tcmd
test
```

<pre class="tcmd">> cd \c</pre>

위와 같이 메타 영역에 변수를 선언하면, 포스트 상단에 제목과 작성일이 출력된다. 또는 content 내에서 <span class="tline">page.title</span>, <span class="tline">page.category</span>, <span class="tline">page.date</span>와 같이 page 객체의 변수로 호출해 직접 사용 할 수도 있다.

site, page 등의 내장 객체에 대한 자세한 설명은 [Jekyll 문서](https://jekyllrb.com/docs/variables/)를 참고하자.

content 영역에는 html 태그를 쓸 수도 있지만, 문장 혹은 단어마다 html 태그를 일일히 넣어야 한다면 깃헙 페이지를 굳이 쓸 이유가 없을 것이다.

깃허브에서 지원하는 [마크다운 고유의 문법](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/about-writing-and-formatting-on-github)을 쓰면 효율적으로 포스트를 작성 할 수 있다.

# 2. _site 폴더
렌더링 파일의 결과물을 모아 놓은 폴더. 커맨드 라인에서
<p class="tcmd">> bundle exec jekyll serve</p>
를 입력하면 자동으로 만들어지는 동시에 로컬 서버가 실행된다.

Visit https://github.com



