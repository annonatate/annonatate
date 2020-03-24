---
layout: null
---

{% assign test = site.data | group_by:
[{% for file in site.data %} { {{file[1]['on'][0]['full']| jsonify | escape}}: {{file[1] |jsonify|escape}} }{% unless forloop.last %},{% endunless %}{% endfor %}]
