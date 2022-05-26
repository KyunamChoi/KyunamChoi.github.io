---
title: "[GitHub Blog] 블로그 포스팅하는 방법"
excerpt: 

categories:
  - Blog
tags:
  - [Blog]

date: 2022-05-26
last_modified_at: 2022-05-26
---

GitHub 블로그의 테마 설정을 완료한 후에 Jekyll의 간편한 블로깅을 사용한 포스팅 방법을 알아본다. 

## 1. Markdown을 지원하는 에디터 실행

나는 사용에 익숙한 `Visual Stuio Code` 에디터를 선택했다. 에디터를 열고 GitHub 블로그의 Jekyll 테마의 파일들이 들어있는 `MYGITHUBID.github.io` 이름의 로컬 폴더를 열어준다.  
<br>

## 2. _posts 폴더를 생성

`MYGITHUBID.github.io` 로컬 폴더 안에 **_posts** 폴더가 존재한다면 넘어가고, 존재하지 않는다면 **_posts** 폴더를 생성한다. 이는 각 Jekyll 테마의 기본 카테고리 구조에 따라 다를 수 있다. 앞으로 GitHub 블로그에 포스팅되는 게시물 md파일들은 **_posts** 안에 위치시켜 포스팅하게 된다.  
<br>

## 3. yyyy-mm-dd-title.md 형식의 파일을 생성

GitHub 블로그 포스트는 _posts 폴더 안에 `md` 파일 확장자를 사용하여 게시한다. **yyyy-mm-dd** 형식의 날짜와 **-title**을 붙여주어 파일명으로 설정한다. 포스트 파일의 title은 영어로 쓰는 것을 추천한다.  
<br>
*ex) 2022-05-26-blog-how-to-post.md*  
<br>

## 4. 머릿말(YAML Front Matter) 작성

YFM(YAML Front Matter)은 md 파일의 최상단에 위치하며 3개의 `-`으로 시작과 끝을 표시한다. YAML은 오픈 소스 프로젝트에서 많이 사용하는 구조화된 데이터 형식이다. YFM은 이 YAML을 사용해 글의 제목, 날짜, 카테고리, 태그, 레이아웃 등을 정의할 수 있다. 

```yaml
---
title: "[GitHub Blog] 블로그 포스팅하는 방법"
excerpt: 

categories:
  - Blog
tags:
  - [Blog]

date: 2022-05-26
last_modified_at: 2022-05-26
---
```
현재 포스트의 머릿말을 이렇게 작성되었다.

**title** : 포스트의 제목을 큰 따옴표로 작성한다. title을 작성하지 않으면 md파일의 파일명에서 사용된 title 부분이 제목으로 업로드되다.  

**excerpt** : 포스트 목록에서 보여지는 블로그 소개글로 들어간다.  

**categories** : 포스트의 카테고리를 의미한다. GitHub 블로그에서 이 카테고리는 페이지, 메뉴바, 사이드바 생성 등 중요한 기능을 하므로 이에 관한 포스트도 별도로 다룰 예정이다.  

**tags** : 태그와 카테고리의 차이점은 카테고리는 sub url이 붙는 페이지가 있지만, 태그는 존재하지 않는다. 카테고리보다 세부적이고, `[]` 대괄호 안에 `,` 콤마로 구분해주어 여러 태그를 지정할 수 있다.  

**date** : 글을 처음 작성한 날짜.  

**last_modified_at** : 글을 마지막으로 수정한 날짜.  


YFM에 관한 페이지 내부에서의 변수 역할, permalink, layout에 대한 오버라이딩 설정 등 자세한 내용은 후에 별도의 포스트에서 다룰 예정이다.  
<br> 

## 5. 포스트 내용을 Markdown 문법으로 작성

머릿말이 `---`로 끝난 이후부터 포스트 본문 영역이다. Jekyll은 블로그 운영을 위해 html 관련 지식이 없어도, 보다 간단한 markdown 파일로 문서를 작성하면 이를 html로 변환해 블로그를 작성할 수 있도록 서비스해준다. markdown 사용법은 정리해서 포스팅할 예정이다.  
<br>


## 6. markdown으로 작성한 포스트 미리 보기

두 가지 방법에 대해 알아본다. 첫번째 방법은 `Visual Studio Code`에서 지원하는 `preview` 기능과 `local server`에서 내가 작성한 md파일이 어떻게 html로 변환되었는지 확인 가능하다.  
<br>

### VS Code - preview

markdown으로 작성한 문서가 html로 어떻게 변환되는지 확장 페이지를 통해 바로 확인이 가능하다. 이를 사이드에 확장시켜 동시에 확인할 수도 있어 markdown문법이 의도한대로 작성되고 있는지 확인하기 편리하다.  
<br>

### Local server에서 확인하기

CMD창에서 `MYGITHUBID.github.io` 이름의 로컬 폴더로 이동한 후 아래 명령어를 실행하면 로컬 환경에서 Jekyll 서버가 작동한다.  

```cmd
> bundle exec jekyll serve
```  
Jekyll 서버가 성공적으로 작동하면 `Server address: http://127.0.0.1:4000/`라는 로컬 서버의 주소가 나오고, 가동 중인 CMD를 켜놓고 `http://127.0.0.1:4000/`에 접속하면 작성된 md파일이 어떻게 html로 변환되어 웹페이지에서 보여지는지 확인할 수 있다. git push 하여 원격 서버에 반영하기 전 GitHub Blog 변경사항을 모두 확인할 수 있으므로, 포스팅 외에도 블로그에 변경사항이 있는 경우 유용한 방법이다.  
<br>

## 7. 작성한 포스트 md파일을 git push 하여 GitHub Pages 서버에 업로드

```cmd
> git add .
> git commit -m "블로그 글 등록"
> git push -u origin master
```
git에 관한 설명은 GitHub Blog에서는 다루지 않으니 git설치 및 사용방법은 공부를 해두는게 좋다. 