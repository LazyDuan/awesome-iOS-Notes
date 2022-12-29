### 一、应用程序的状态

* Not running（未运行）：程序未启动
* Inactive（未激活）：其他两个状态切换时出现的短暂状态。唯一在此状态停留时间比较长的情况是：当用户锁屏时或者系统提示用户去响应Alert窗口(如来电、信息)时
* Active（激活）：在屏幕上显示的正常运行状态，该状态下可以接收用户输入并更新显示
* Background（后台）：程序在后台且能执行代码。用户按下Home键不久后进入此状态(先进入了Inactive状态，再进入Background状态)，然后会迅速进入挂起状态(Suspended)。有的程序经过特殊的请求后可以长期处于Background状态
* Suspended（挂起）：程序在后台不能执行代码。普通程序在进入Background状态不久后就会进入此状态。当挂起时，程序还是停留在内存中的，当系统内存低时，系统就把挂起的程序清除掉，为前台程序提供更多的内存

### 二、UIApplicationDelegate

1. - (void)applicationWillResignActive:(UIApplication*)application
`说明：当应用程序将要进入非活动状态执行，在此期间，应用程序不接收消息或事件，比如来电话了。`
2. -(void)applicationDidBecomeActive:(UIApplication *)application
`说明：当应用程序进入活动状态执行，这个刚好和上面的那个方法相反`
3. -(void)applicationDidEnterBackground:(UIApplication*)application
`说明：当程序被推送到后台的时候调用。所以要设置后台继续运行，则在这个函数里面设置即可。`
4. -(void)applicationWillEnterForeground:(UIAppliaction*)application
`说明：当程序从后台将要重新回到前台时候调用，这个刚好跟上面的那个方法相反。`
5. -(void)applicationWillTerminate:(UIApplication *)application
`说明：当程序将要退出时调用，通常是用来保存数据和一些推出前的清理工作。这个需要设置UIApplicationExitsOnSuspend的键值。`
6. -(void)applicationDidReceiveMemoryWarning:(UIApplication *)application
`说明：iPhone设置只有有限的内存，如果为应用程序分配了太多的内存操作系统会终止应用程序的运行，在终止前会执行这个方法，通常可以在这里进行内存清理工作防止程序被终止`
7. -(void)applicationSignificantTimeChange:(UIApplication*)application
`说明：当系统时间发生改变时执行`
8. -(void)applicationDidFinishLaunching:(UIApplication*)application
`说明：当程序载入后执行`
9. -(void)application:(UIApplication *)application willChangeStatusBarFrame:(CGRect)newStatusBarFrame
`说明：当StatusBar将要改变时执行`
10. -(void)application:(UIApplication *)application willChangeStatusBarOrientation:(UIInterfaceOrientation)newStatusBarOrientation duration:(NSTimeInterval)duration
`说明：当StatusBar框方向将要变化时执行`
11. -(void)application:(UIApplication *)application handleOpenURL:(NSURL *)url
`说明：当通过URL执行`
12. -(void)application:(UIApplication *)application didChangeStatusBarOrientation:(UIInterfaceOrientation)oldStatusBarOrientation
`说明：当StatusBar框方向变化完成后执行`
13. -(void)application:(UIApplication *)application didChangeSetStatusBarFrame:(CGRect)oldStatusBarFrame
`说明：当StatusBar框变化完成后执行`