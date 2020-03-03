---
layout: post
title:  "Mouse Move trail Exercise"
date:   2020-03-03 13:42:04 +0000
categories: exercise
---

<style>
  .trail { /* className for the trail elements */
    position: absolute;
    height: 6px; width: 6px;
    border-radius: 3px;
    background: teal;
  }
  body {
    height: 300px;
  }
</style>

<script>
  // Your code here.
  let contador = 0;
  window.addEventListener("mousemove", event => {
    let trail = document.createElement("div");
    trail.className = "trail";
    trail.style.left = (event.pageX - 4) + "px";
    trail.style.top = (event.pageY - 4) + "px";
    document.body.appendChild(trail);
    
    if (contador > 40) {
        document.body.removeChild(document.getElementsByClassName("trail")[0]);
    } else {
        contador++;
    }
  });
</script>
