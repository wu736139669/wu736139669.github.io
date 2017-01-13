#调试修改第三方sdk内容

###背景：
经常在使用第三方sdk的时候发现有页面长的不好看，或者说有什么特别需要修改的地方，于是乎就有这么一篇文章了。

最近在搞京东开普勒项目，就那他们的sdk做例子吧。

po [UIViewController _printHierarchy]

<UINavigationController 0x7fd3ba000e00>, state: appeared, view: <UILayoutContainerView 0x7fd3b8708cb0>
   | <ViewController 0x7fd3b8708460>, state: disappeared, view: <UIView 0x7fd3b8612d90> not in the window
   | <KPWebViewController 0x7fd3b8723b60>, state: appeared, view: <UIView 0x7fd3b8410260>
   
   