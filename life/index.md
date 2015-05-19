---
layout: home
---

<div class="index-content col3">
    <div class="section">
        <ul class="artical-cate">
            <li><a href="/"><span>博客</span></a></li>
            <li><a href="/tech"><span>科技</span></a></li>
            <li class="on"><a href="/life"><span>生活</span></a></li>
            <li><a href="/archive.html"><span>时间线</span></a></li>
        </ul>

        <div class="cate-bar"><span id="cateBar"></span></div>

        <ul class="artical-list">
        {% for post in site.categories.life %}
            <li>
                <h2>
                    <a href="{{ post.url }}">{{ post.title }}</a>
                </h2>
                <div class="title-desc">{{ post.description }}</div>
            </li>
        {% endfor %}
        </ul>
    </div>
    <div class="aside">
    </div>
</div>
