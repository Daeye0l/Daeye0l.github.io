---
layout: post
title:  "포스트에 댓글창 만들기"
description: utterances를 사용해 포스트에 댓글창 만들기
---
깃허브 포스트에 utterances를 사용해 댓글창을 추가하는 과정을 포스팅했다.
<br><br>

## 1. 깃허브에 Utterances App 설치하기
<hr>

- [Utterances GitHub App](https://github.com/apps/utterances)페이지로 이동하여 github 저장소에 Utterances를 설치한다.

## 2. Utterances 사이트에서 원하는 설정 하기
<hr>

- [Utterances](https://utteranc.es/)웹사이트로 이동한다.

- repo: 칸에 owner/repo를 입력한다.
![repo](../../images/repo.png)

- Theme목록중에서 원하는 테마를 선택한다.
![theme](../../images/theme.png)
<br>

## 3. 코드에 적용하기
<hr>

- script코드를 복사해서 _layouts의 post.html에 적용한다.
![script](../../images/script.png)

- post.html에 다음과 같이 disqus설정 코드가 있다면 제거 또는 주석처리 하고 그 자리에 script 코드를 적용한다.
```
{%- if site.texture.disqus_shortname -%}
    <div id="disqus_thread" style="margin-top:25px"></div>
    <script>
        var disqus_config = function () {
        this.page.url = '{{ page.url | absolute_url }}';
        this.page.identifier = '{{ page.url | absolute_url }}';
        };
        (function() {
        var d = document, s = d.createElement('script');
        s.src = 'https://{{ site.texture.disqus_shortname }}.disqus.com/embed.js';
        s.setAttribute('data-timestamp', +new Date());
        (d.head || d.body).appendChild(s);
        })();
    </script>
    <noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript" rel="nofollow">comments powered by Disqus.</a></noscript>
{%- endif -%}-->
```

- 블로그에 댓글창이 생긴것을 확인할 수 있다.
![box](../../images/box.png)