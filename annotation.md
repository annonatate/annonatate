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
    var resources = Object.values(content).filter(elem => elem['on'][0]['full'] == canvas);
    var listannotation = `{"@context":"http://iiif.io/api/presentation/2/context.json",
            "@type": "sc:AnnotationList", "@id": "${window.location.href}", "resources": ${escape(JSON.stringify(resources))} }`
    document.getElementById("json").innerHTML = listannotation;
  } else {
    document.getElementById("json").innerHTML = escape(JSON.stringify(content[filename]));
  }
</script>
