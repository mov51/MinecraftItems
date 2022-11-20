---
layout: default
---
<article class="post h-entry" itemscope itemtype="http://schema.org/BlogPosting">

  <header class="post-header">
    <h1 class="post-title p-name" itemprop="name headline"><img src="/data/images/{{ page.item_image }}" alt="{{ page.item_name }}" class="ImageHeader" />{{ page.item_name | escape }}</h1>
    <p class="post-meta version">
        Added in <span>{{ page.added }}</span> > <span>{{ page.added_snapshot }}</span>
    </p>
    <p class="post-meta version">
        Last modified in <span>{{ page.last_modified }}</span> > <span>{{ page.last_modified_snapshot }}</span>
    </p>
    <div class="tags">
    <p class="post-meta version">
      <a href="{{ page.wiki }}" target="_blank" class="wiki_link">Wiki</a>
      {% assign sortedCategories = page.categories | sort %}
      {% for category in sortedCategories %}
        <a href="/category/{{ category }}" class="item_category">#{{ category }}</a>
      {% endfor %}
    </p>
    </div>
    <div>
    {% if page.farmable %}
      <p class="post-meta">
        Farmable: <span class="farmable">{{ page.farmable }}</span>
      </p>
    {% endif %}
    {% if page.farming_requires_player %}
      <p class="post-meta">
        Farming requires player: <span class="farmable">{{ page.farming_requires_player }}</span>
      </p>
    {% endif %}
    </div>
  </header>

  <div class="post-content e-content" itemprop="articleBody">
    {{ content }}
  </div>

  <a class="u-url" href="{{ page.url | relative_url }}" hidden></a>
</article>
