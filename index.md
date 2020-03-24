---
layout: null
---
<html>
<body>
 {% assign annotations = site.static_files |  where_exp:"item",
"item.path contains 'annotations'" %}
{% for file in site.static_files %}
   * [{{ file.path }}]({{ site.baseurl }}{{ file.path }})
{% endfor %}
</body>
</html>
