---
layout: null
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.15/lodash.min.js"></script>
<body>
<div id="json"></div>
</body>
<script>
  let params = new URLSearchParams(window.location.search);
  let filename = params.get('filename');
  let canvas = params.get('canvas');
  var content = {{site.data | jsonify }}
  if (canvas) {
    var resources = Object.values(content).filter(elem => elem['on'][0]['full'] == canvas);
    var listannotation = `{"@context":"http://iiif.io/api/presentation/2/context.json",
            "@type": "sc:AnnotationList", "@id": "${window.location.href}", "resources": ${_.escape(JSON.stringify(resources))} }`
    document.getElementById("json").innerHTML = listannotation;
  } else {
    document.getElementById("json").innerHTML = _.escape(JSON.stringify(content[filename]));
  }
</script>
