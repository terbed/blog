---
layout: page
permalink: /archive
---

{% for collection in site.collections %}
{% if collection.label != "pages" %} <!-- Exclude 'pages' from being listed -->

  <h2>Items from {{ collection.label | capitalize }}</h2>
  <ul>
    {% assign sorted_items = site[collection.label] | sort: 'date' | reverse %}
    {% for item in sorted_items %}
      <li>
        <a href="{{ item.url }}">{{ item.title }}</a>
        {% if item.date %} - {{ item.date | date: "%B %d, %Y" }}{% endif %}
      </li>
    {% endfor %}
  </ul>

{% endif %}
{% endfor %}
