## StatusBarControl
这是一个对状态栏可以任意控制的工具，可以添加给给状态栏添加任意颜色的背景，图像，渐变都行

### 加入
在build.gradle文件中加入
```gradle
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

```
在app.gradle文件加入
```gradle
dependencies {
	        implementation 'com.github.ErolC:StatusBarControl:1.0.3'
	}
```
### API
```kotlin
statusBarHeight//状态栏高度
statusBarColor//系统状态栏背景颜色
isShowStatusBar//状态栏是否显示
setStatusBarTextColor()//设置状态栏字体颜色
hideStatusBar()//隐藏状态栏
showStatusBar()//展现状态栏
setStatusBarBackground()//设置状态栏背景，
setStatusBarColor()//设置状态栏背景颜色
immersive()//状态栏背景消失，内容层渗透到状态栏的区域里。
```
## 1.0.1
### 使用
如果是kotlin，你可以直接这样
```kotlin
override fun onCreate(savedInstanceState: Bundle?){
    setStatusBarBackground(R.drawable.status_bar)//设置自定义背景
    val height = statusBarHeight//获取状态栏高度
    //code...
}

```
如果是java
```java
public void onCreate(Bundle savedInstanceState){
    StatusBarKt.setStatusBarBackground(this,R.drawable.status_bar);
    int height = StatusBarKt.getStatusBarHeight(this);
}
```

以上两段代码的效果是一样的。

## 1.0.2
新增kotlin的fragment环境支持，在fragment的回调中也能和在activity的回调中一样使用,也就是在fragment文件中，就无需再通过activity才能操作状态栏了。

新增`StatusBar.java`类，用于仅有java的Android项目,方便java项目的使用。

```java
public void onCreate(Bundle savedInstanceState){
   StatusBar bar = new StatusBar(this);
   bar.setBackground(R.drawable.status_bar);
   bar.getHeight();
}
```