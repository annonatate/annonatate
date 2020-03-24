---
layout: null
---
{% for annotation in site.annotations %}
{{annotation | inspect }}
{% endfor %}
