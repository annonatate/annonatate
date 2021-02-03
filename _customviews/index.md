---
layout: null
---
{% assign customviewarray = '' | split: '' %}
{% for customview in site.customviews %}
{% if customview.slug != 'index' %}
{% assign item = customview.url | prepend: site.baseurl | prepend: site.url %}
 {% assign customviewarray = customviewarray | push: item %}
{% endif %}
{% endfor %}
{{customviewarray | jsonify}}
