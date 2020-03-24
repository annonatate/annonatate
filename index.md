---
layout: null
---
{% assign my_array = "" | split: ',' %}
{% for file in site.data %}
{% assign my_array = my_array | push: {{file[1] |jsonify|escape}} %}
{% endfor %}

{{my_array | inspect}}

