---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

<h1>{{ site.data.pages_list.pages_list_title }}</h1>
<ul>
  {% for item in site.data.pages_list.pages %}
    <li><a href="{{ item.url }}">{{ item.title }}</a></li>
  {% endfor %}
</ul>
      
test text
