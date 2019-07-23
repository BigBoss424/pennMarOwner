---
layout: default
title: Lawless Landlord Log
description: A log of unlawful actions taken by 
             the landlord(s). For both the purpose 
             of keeping evidence and 
---

<!-- Section | Description -->
<header>
    <h1>Lawless Log</h1>
</header>

<ul class="posts">
    {% for post in paginator.posts %}
    <li itemscope itemtype="http://schema.org/BlogPosting">
      <a href="{{ site.baseurl }}{{ post.url }}" itemprop="url">
        <div class="p-wrap">
          <article class="inner">
            <time datetime="{{ post.date | date_to_xmlschema }}"
                itemprop="datePublished">
              {{ post.date | date_to_string }}
            </time>
            <p itemprop="name headline">{{ post.title }}</p>
          </article>
        </div>
      </a>
    </li>
    {% endfor %}
  </ul>
</div>

{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.next_page %}
  <a href="{{ site.baseurl }}/page/{{paginator.next_page}}" class="older">Older</a>
  {% else %}
  <span class="next">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
    <a href="{{ site.baseurl }}/" class="newer">Newer</a>
    {% else %}
    <a href="{{ site.baseurl }}/page/{{paginator.previous_page}}" class="newer">Newer</a>
    {% endif %}
  {% else %}
  <span class="previous">Newer</span>
  {% endif %}
</div>
{% endif %}
