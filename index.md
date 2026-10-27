---
title: 虾夷共和球's Website
---

## 🏳️‍⚧️ Who I Am
Welcome to my personal website! My pseudonym is <ruby>Xiāqiú<rt>虾球</rt></ruby>, which is short for <ruby>Xiāyígònghéqiú<rt>虾夷共和球</rt></ruby>, so please just call me <ruby>Xiāqiú<rt>虾球</rt></ruby>.<br>
I'm a transfeminine student of management with an Accounting Professional Qualification, currently based in Shandong, China. I'm also an Esperantist who is interested in languages and a Minecraft player whose JEID is `XiaYiGongHeQiu` and whose BEID is `XiaYGHQiu`.<br>
I built this site to introduce myself and share my blog posts. Thanks for stopping by!

## 📝 [Blog](/blog.html)
### Recent Articles

<ul>
  {% for post in site.posts limit:3 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## 🧧 <ruby>Spare some change? Buy me a coffee!<rt>如果有闲钱，欢迎请我喝杯赛博咖啡~</rt></ruby>
<img src="/images/weixinzanshangma.png" 
     alt="🦐🍥的微信赞赏码" 
     width="200" 
     style="display: block; margin: 0 auto;">
