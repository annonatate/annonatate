---
layout: null
---
[{% for file in site.data %}{ 
  "filename":"{{file[0]| jsonify | escape}}", 
  "canvas": "{{file[1]['on'][0]['full']}}",
  "json":{{file[1] |jsonify|escape}}
 }{% unless forloop.last %},{% endunless %}{% endfor %}]
