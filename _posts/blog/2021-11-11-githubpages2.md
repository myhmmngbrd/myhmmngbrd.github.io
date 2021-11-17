---
title: GitHub Pages 폴더 구조와 설명
category: blog
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

```markdown
---
title: GitHub Pages 폴더 구조와 설명
category: "GitHub Pages"
date: 2021-11-11
---

본문 영역

```

위와 같이 메타 영역에 변수를 선언하면, 포스트 상단에 제목과 작성일이 출력된다. 또는 content 내에서 <span class="tline">page.title</span>, <span class="tline">page.category</span>, <span class="tline">page.date</span>와 같이 page 객체의 변수로 호출해 직접 사용 할 수도 있다.

site, page 등의 내장 객체에 대한 자세한 설명은 [Jekyll 문서](https://jekyllrb.com/docs/variables/)를 참고하자.

content 영역에는 html 태그를 쓸 수도 있지만, 문장 혹은 단어마다 html 태그를 일일히 넣어야 한다면 깃헙 페이지를 굳이 쓸 이유가 없을 것이다.

깃허브에서 지원하는 [마크다운 고유의 문법](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/about-writing-and-formatting-on-github)을 쓰면 효율적으로 포스트를 작성 할 수 있다.

# 2. _site 폴더
렌더링 파일의 결과물을 모아 놓은 폴더. 커맨드 라인에서
<pre class="tcmd">> bundle exec jekyll serve</pre>
를 입력하면 자동으로 만들어지는 동시에 로컬 서버가 실행된다.



# _includes 폴더
# _layouts 폴더

유저에게 보여줄 레이아웃 문서가 저장된 폴더다.

깃허브 블로그의 레이아웃을 이해하려면,

yaml 머리말의 layout 태그와 url에 대해 알고 있어야 한다.

블로그이름.github.io로 접속 했을 때 불러오는 파일은 루트 폴더의 index.md 파일이다.

블로그이름.github.io/path로 접속 했을 때 불러오는 파일은 해당 path에 맞는 파일이 있다면 불러오고, 아니라면 루트 폴더의 404.html 파일을 불러온다.

이때 불러오는 문서의 머리말에 layout 변수가 정의되어 있다면, _layout 문서 내의 해당 파일을 먼저 불러온다.

예컨대 유저가 myhmmngbrd.github.io/hello 경로로 접속했다고 가정해보자.

1. 일단 hello.html 혹은 hello.md 파일이 존재하는지 확인한다.
- 존재하지 않는다면, 404.html 파일을 출력한다.
2. 존재한다면, 파일을 불러온다. 다음은 hello.md 파일의 내용이다.

```
---
layout: mylayout
---
반가워
```

3. yaml 머리말에 layout 요소가 정의되어 있는지 확인한다.
- 정의되어 있지 않다면, 디폴트 레이아웃인 _layout/page.html을 불러와 출력한다.

4. _layout/mylayout.html 파일을 불러온다. 다음은 mylayout.html 파일의 내용이다.
- 해당 파일이 존재하지 않는다면, hello.md를 출력한다.

``` {% raw %}
<p>안녕</p>
{{ content }}
{% endraw %}```

5. 결과는 다음과 같다.

```
안녕
반가워
```


> default.html
