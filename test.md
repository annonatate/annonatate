---
layout: null
---

{{site.annotations | inspect }}
{% for annotation in site.annotations %}
{{annotation | inspect }}
{% endfor %}
