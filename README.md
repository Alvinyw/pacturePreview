# picturePreview: 纯前端的图片预览组件

支持 IE6 ~ IE11、Chrome、Firefox、Safari 和 Opera

## 使用示例：

```html
<input type="file" id="loadPng" accept="image/x-png"/>&nbsp;<button onclick="pv1.reset()">重置</button>
<div class="preview" id="pv1"></div>

<input type="file" id="loadJpg" accept="image/jpg"/>&nbsp;<button onclick="pv2.reset()">重置</button>
<div class="preview" id="pv2"></div>

<script type="text/javascript" src="./picturePreview.min.js"></script>

<script type="text/javascript">
	var get = function(id){
		return document.getElementById(id);
	};
	Preview.defaults.onSuccess = false;
	Preview.defaults.onFailed = true;
	var pv1 = new Preview(get('loadPng'), get('pv1'), {
		onSuccess: function(path, ext, accept){
			alert(this === pv1);
			alert('path:' + path);
			alert('extension:' + ext);
			alert('accept:' + accept);

			return true;
		},
		onFailed: function(){
			alert("Load image Failed!");
			} 
	});
	var pv2 = new Preview(get('pv2'), get('loadJpg'));
</script>
```
## 使用说明：
方法主体：**Preview(arg1, arg2, {})**

### 参数说明：
- arg1：预览图片的容器；
- arg2：type 为 file 的 Button；
- {}：可设置预览图片成功和失败的函数体；

