# imgEditor
图片编辑组件（支持图片移动、缩放、旋转、导出编辑后的图片base64）
demo：[http://go.163.com/2015/public/team/renke/imgeditor/index.html](http://test.go.163.com/go/2015/public/team/renke/imgeditor/index.html)

![](http://i.imgur.com/xQweJRi.png)

> 引用js

> [http://go.163.com/2015/public/team/renke/imgeditor/js/imgeditor.js](http://go.163.com/2015/public/team/renke/imgeditor/js/imgeditor.js)
> 
> [http://go.163.com/2015/public/team/renke/imgeditor/js/gesturer.js](http://go.163.com/2015/public/team/renke/imgeditor/js/gesturer.js)

    <script>
   		document.addEventListener('touchmove', function (event) {
    		event.preventDefault();
    	});
    	var imgeditor = new ImgEditor({
    		el: document.getElementById('canvas'),
   			color: 'transparent'
    	});
    
    	var gesture = new Gesturer({
    		el: document.getElementById('canvas'),
    			onPressMove: function (evt) {
    			imgeditor.onMove(evt);
    		},
    		onPinch: function (evt) {
    			imgeditor.onPinch(evt);
    		},
    		onRotate: function (evt) {
    			imgeditor.onRotate(evt);
    		},
    	});
		gesture.on();  // 开启手势事件
    	imgeditor.setImg('img.jpg');  //绘制图片
    
    	$('.btn').click(function(){
    		$('.img').attr("src",imgeditor.getImg()); // imgeditor.getImg() 返回图片base64
    	});
    </script>
    
    
