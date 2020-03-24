---
layout: null
---
<script>
  let params = new URLSearchParams(window.location.search);
  let filename = params.get('filename');
  let canvas = params.get('canvas');
  if (canvas) {
    console.log(canvas)
  } else {
    console.log(filename)
  }
</script>
