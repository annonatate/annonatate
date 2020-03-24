---
layout: null
---
{
{% for file in site.data %}
   {{file[0]}} : {{file[1] | jsonify | escape}}
{% endfor %}{% unless forloop.last %},{% endunless %}
}
