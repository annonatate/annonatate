---
layout: null
---
<script>
  let params = new URLSearchParams(window.location.search);
  let filename = params.get('filename');
  let canvas = params.get('canvas');
  var test2 = {{site.data[filename] | jsonify}}
  var test = {{site.data | where_exp: 'item', 'item[0] contains filename' | jsonify }}
  if (canvas) {
    console.log(canvas)
  } else {
    console.log(filename)
    console.log(test)
    console.log(test2)
  }
</script>
