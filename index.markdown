---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<ul>
  {% for collection in site.collections %}
    {% if collection.label != 'posts' %}
    <li>
      {{ collection.label }}
      <ul>
        {% assign docs = collection.docs | sort: order | reverse %}
        {% for doc in docs %}
            <li>
            <a href="{{ doc.url }}">{{ doc.title }}</a> {{ doc.order }}
            </li>
        {% endfor %}
        </ul>  
    </li>
    {% endif %}
  {% endfor %}
</ul>
