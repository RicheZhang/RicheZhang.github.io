---
layout:post
title:Javascript basics
---

###Javascript example
~~~
document.write("<h1>this is a test</h1>")
<button type="button" onclick="alert('Hello world')">Click me</button>
x=document.getElementById("demo")
x.innerHTML="Hello javascript"
<script>
function changeImage()
{
    element=document.getElementById('myimage')
    if (element.src.match("bulbon"))
    {
        element.src="/images/pic_bulboff.gif";
    }
    else
    {
        element.src="/images/pic_bulbon.gif";
    }
}
</script>
<img id="myimage" onclick="changeImage()" src="/images/pic_bulboff.gif" width="100" height="180">
~~~

