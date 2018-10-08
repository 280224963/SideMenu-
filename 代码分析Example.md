# Example部分代码分析

![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_.png)

主要调用了SideMenu提供接口的类：MainViewController

该类主要控制了如下场景，是该示例中调节菜单各种显示模式的一个设置界面。

![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_1.png)





     
       
## 变量
* presentModeSegmentedControl 对应下图分段控制按钮
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_2.png)
* blurSegmentControl 对应下图分段控制按钮
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_3.png)
* darknessSlider 对应下图滑块控制条
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_4.png)
* shadowOpacitySlider 对应下图滑块控制条
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_5.png)
* screenWidthSlider 对应下图滑块控制条
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_6.png)
* shrinkFactorSlider 对应下图滑块控制条
![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_7.png)
* blackOutStatusBar 对应下图开关

![kbelogo1](https://github.com/280224963/SideMenu-/blob/master/picture/Example_8.png)



        

## 函数：
* viewDidLoad()

     初始化视图


* setupSideMenu()
     载入场景

     · 为导航栏加入了左侧菜单和右侧菜单

     · 加入了手势

     · 设置了一个背景


* setDefaults()
     把设置页面各控制项的默认值设为了SideMenuManager提供的默认值


* changeSegment(_ segmentControl: UISegmentedControl)
     为分段控制按钮添加功能

     主要是利用SideMenuManager提供的接口设置了菜单显示的四个参数

     · 点击Mune Present Mode按钮，把菜单显示的默认值设为选中的模式，有menuSlideIn, viewSlideOut, viewSlideInOut, menuDissolveIn四种样式

     · 点击Menu Blur Style按钮，把菜单模糊化的方式默认值设为选中的模式，有none, dark, light, extraLight四种模式


* changeSlider(_ slider: UISlider)
     为滑块控制条添加功能

     主要是利用SideMenuManager提供的接口设置了菜单显示的四个参数。

     · darknessSlider：对应Menu Fade Strength，调节菜单显示的亮度。

     · shadowOpacitySlider：对应Menu Shadow Opacity，调节菜单阴影的透明度。

     · screenWidthSlider：对应Menu Screen Width，调节菜单显示的宽度。

     · shrinkFactorSlider：对应Menu Transform Scale Factor，调节菜单显示的缩放度。


* changeSwitch(_ switchControl: UISwitch)
     设置menuFadeStatusBar的初始值为打开
