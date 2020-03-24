---
layout: null
---
<script>
  let params = new URLSearchParams(window.location.search);
  let filename = params.get('filename');
  let canvas = params.get('canvas');
  var content = {{site.data | jsonify }}
  console.log(content)
  
  var test = content.filter(elem => elem['@id'].indexOf(filename) != -1)
  if (canvas) {
    console.log(canvas)
  } else {
    console.log(filename)
    console.log(test)
  }
</script>
