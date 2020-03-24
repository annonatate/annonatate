---
layout: null
---
<p id="json"></p>
<script>
  let params = new URLSearchParams(window.location.search);
  let filename = params.get('filename');
  let canvas = params.get('canvas');
  var content = {{site.data | jsonify }}
  if (canvas) {
    console.log(Object.values(content).filter(elem => elem['on'][0]['full'] == canvas))
  } else {
    document.getElementById("json").innerHTML = JSON.stringify(content[filename]);
  }
</script>
