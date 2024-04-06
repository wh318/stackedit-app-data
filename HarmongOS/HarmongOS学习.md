# __HarmongOS学习笔记__
## *一、ArkUI组件*
### 1、Image 图片
- 组件

		Image(src: string|PixelMap|Pesource)
		
		1.string格式,通常用来加载网络图片，需要网络权限：ohos.permission.INTERNET
		Image('https://xxx.png')
		2.PixelMap格式，可以加载像素图直接操作像素，常用在图片编辑中
		Image(PixelMapObject)
		3.Resource格式，加载本地图片资源
		Image($r('app.media.xxx'))  //图片放在media文件夹下
		Image($rawfile('xxx.png'))  //图片放在rawfile文件夹下

 - 属性

		Image($r('app.media.xxx'))
			.width(100)  //宽度
			.height(120)  //高度
			.borderRadius(10)  //边框圆角
			.interpolation(ImageInterpolation.High)  //图片插值，解决图片缩放时的锯齿等问题
			更多参考官方文档
	![代码](/imgs/2024-02-03/SR5WDOkfxGFbCdZL.png =400x300)	![效果](/imgs/2024-02-03/okpymcsSjki92Of5.png =150x300)

### 2、Text 文本
- 组件
	
		Text(content?: string|Resource)
		
		1.string格式，直接填写文本美容
		Text('要在屏幕显示的文本')
		2.Resource格式，加载本地图片资源
		Text($r('app.string.width_label'))

- 属性

		Text('要在屏幕显示的文本')
			.lineHeight(32)  //行高
			.fontsize(20)  //字体大小
			.fontColor('#ffffffff')  //字体颜色
			更多参考官方文档

- 限定词![限定词](/imgs/2024-02-03/MF3mDGG2M7QQbLaN.png)
	
	_使用Text($r('app.string.width_label'))，会以当前所在地区的限定词优先，所有的限定词中没有找到，就会在base目录中查找_


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0NTE4MDY5MF19
-->