# imgEditor
图片编辑组件（支持图片移动、缩放、旋转、导出编辑后的图片base64）
demo：[http://test.go.163.com/go/2015/public/team/renke/imgeditor/index.html](http://test.go.163.com/go/2015/public/team/renke/imgeditor/index.html)

> 引用js

> [http://go.163.com/2015/public/team/renke/imgeditor/js/imgeditor.js](http://go.163.com/2015/public/team/renke/imgeditor/js/imgeditor.js)
> 
> [http://go.163.com/2015/public/team/renke/imgeditor/js/gesturer.js](http://go.163.com/2015/public/team/renke/imgeditor/js/gesturer.js)

  	<script>
    	document.addEventListener('body', function (ev) {
    		ev.preventDefault();
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
    
    	gesture.on();
   		imgeditor.setImg('img.jpg');

    	$('#btn').click(function(){
    		$('.img').attr("src", imgeditor.getImg());
    	});
    </script>

