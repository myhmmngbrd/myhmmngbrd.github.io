---
title: GitHub Pages 기초 정보
categories: [Git, GitHub Pages]
---
1. 튜토리얼 사이트
- <a href="https://docs.github.com/en/pages">GitHub Pages 문서</a> 
<br>
서버와 도메인을 제공하는 사이트
- <a href="https://jekyllrb.com/docs/">Jekyll 문서</a> 
<br>
정적 html 파일을 출력해주는 ruby 프레임워크
- <a href="https://shopify.github.io/liquid/">Liquid 문서</a> 
<br>
html 문서에서 변수를 사용하기 위한 대체 문법
<br>
<br>
2. 공식 문서에서 제공되지 않는 정보
- 2021-11-10 기준, GitHub Pages 공식 문서의 튜토리얼을 따라하다 보면 webrick 라이브러리가 자동으로 설치되지 않아서 오류가 발생한다. jekyll을 실행한 폴더의 커맨드라인에서 bundle add webrick을 입력해 주면 해결됨.
<br>
<br>
3. 기본 폴더 구조
- _posts
<br>
작성한 포스트를 업로드하는 폴더
- _site
<br>
출력될 결과물이 임시 저장되는 폴더. 로컬에서 생성된 _site 폴더는 디버깅 용이므로 수정해도 서버에선 변화가 없다.
- _config.yml
<br>
전역 변수들이 저장되는 파일. \{\{ site.변수이름 \}\} 으로 접근이 가능하다. 
