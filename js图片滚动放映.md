##用JavaScript做一个简易的滚动图片放映##
- 先把各图片的src放在一个数组对象里
- 在通过document.getElementById找到img标签
- 给img标签设置一个name属性，该属性用来响应点击事件从而找到要展示哪张图片，为方便起见，name可以设置为"image_x"的形式，其中x就表示第几张图片。
- 找到要显示的图片后就可以给img标签重新设置图片了，同时要修改img标签的name属性。
## 图片放映实例 ##
    <!DOCTYPE HTML>
    <html>
      <head>
	<title>图片滚动放映</title>
	<script type="text/javascript" src="ehandler.js"></script>
	<script type="text/javascript">
		var images = ['rollover_first_a.jpg','rollover_first_over.png','rollover_second_a.jpg'];
		function nextImage() {
			var img = document.getElementById("slider");
			var imageName = img.name.split("_");
			var index = imageName[1];
			if(index == images.length -1) {
				index = 0;
			}else {
				index++;
			}
			img.src = images[index];
			img.name = "image_" + index;
		}
	</script>
    </head>
    <body>
	<p><img src="rollover_first_a.jpg" id="slider" name="image_0" alt="Home" width="600" height="800"></p>
	<form>
		<input type="button" id="nextImage" value="Next">
	</form>
	<script type="text/javascript">
		var btn = document.getElementById("nextImage");
		EHandler.add(btn,"click",function(){nextImage();});
	</script>
    </body>
    </html>