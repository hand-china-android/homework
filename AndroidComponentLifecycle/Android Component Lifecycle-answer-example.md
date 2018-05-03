##Activity

###onCreate()
	初始化UI元素。
	接收Activity间所传的值。

###onAttachFragment()
	当Fragment被附加到该Activity时，在Fragment的onAttach()之后、onCreate()之前调用。

###onContentChanged()
	当屏幕中的视图发生变化时触发。
	(Android.View.Window.SetContentView()或Android.View.Window.AddContentView())

###onStart()
	在onCreate()之后或onRestart()之后触发。
	给onCreate()初始化的参数赋值。


###onRestoreInstanceState()
	恢复在onSaveInstanceState()中保存的状态。

###onPostCreate()
	在onRestoreInstanceState()后触发。
	目的是让系统类在应用程序代码运行后进行最终初始化。

###onResume()
	可以开始动画，打开设备（相机）等。

###onPostResume()
	让系统类在应用程序恢复代码运行后进行最终设置。

###onAttachToWindow()
	当与Activity关联的主窗口被附加到窗口管理器时触发。

###onCreateOptionsMenu()
	初始化Activity的标准选项菜单。
	在首次显示菜单时调用，每次展示菜单时都要更新菜单。
	在Activity.onOptionItemSelected()处理。

###onPrepareOptionsMenu()
	准备显示标准菜单，在每次显示之前都会调用。
	可以在此处动态的修改内容。
	
###onPause()
	Activity进入后台，但未被killed。
	和onResume()对应。
	用于保存Activity正在编辑的任何持久状态，向用户展示“edit in place”模型，并确保没有足够的资源来启动新活动而不必先杀死该Activity。
	可以停止动画或其他消耗大量CPU的动作。

###onSaveInstanceState()
	保存Activity当前状态，在被kill之前调用。
	在onCreate()或onRestoreInstanceState()中恢复。

###onStop()
	正常时在onRestart()或onDestory()之前触发。
	在内存不足时，永不调用。

###onDestroy()
	释放资源。

-##onRestart()
	在onStop()之后、onStart()之前。

-##onActivityResult()
	startActivityForResult()。

-##onUserInteraction()

-##onUserLeaveHint()




##Fragment

###onInflate()
	
###onAttach()
	Fragment和Activity关联时调用。
	
###onCreate()
	完成Fragment初始化。

###onCreateView()
	创建并返回Fragment关联的视图。

###onViewCreated()
	Fragment的view创建完成。

###onActivityCreated()
	告诉Activity该Fragment已经完成onCreate()。

###onViewStateRestored()
	所保存的视图层次状态被恢复。

###onstart()
	参考Activity。

###onResume()
	参考Activity。

###onCreateOptionsMenu()
	参考Activity。

###onPrepareOptionsMenu()
	参考Activity。

###onPause()
	参考Activity。

###onSaveInstanceState()
	参考Activity。

###onStop()
	参考Activity。

###onDestroyView()
	清理View相关资源。

###onDestroy()
	参考Activity。

###onDetach()
	Activity和Fragment不再关联之前调用。




##Service

###onCreate()
	service创建，只执行一次。

###onStartCommand()：startServie
	onCreate()之后，多次调用。
	直至调用stopService()或stopSelf()后停止。

###onBind()：bindService
	绑定Service。
	必须反回IBinder实例对象。
	Activity和Service通信时使用。

###onUnbind():
	解绑Service。

###onDestroy()
	销毁服务，释放资源。

----startForeground()
	开启前台service。

----stopForeground()
	停止前台service。

----stopSelf()

----stopSelfResult()

----onLowMemory()
	内存不足，减少内存使用时触发。

----onRebind()

----onTaskRemoved()
	服务在运行时删除Service的任务。

----onTrimRemoved()
	在减少应用程序中不使用的内存时调用。

----onConfigurationChanged()
	在组件运行时更改设备配置。










