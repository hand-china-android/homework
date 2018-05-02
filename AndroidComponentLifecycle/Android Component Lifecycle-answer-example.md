## Activity

<!--  每个模块的回调需要按照调用顺序排列  -->
### onCreate（）
	一般初始化UI元素,创建视图,将数据绑定到列表.系统向此方法传递一个Bundle对象,包含了Activity的上一状态(前提是保存了之前的状态)
	
### onRestart()
在Activity 已经停止并即将再次启动前调用
	
### onStart()
在Activity 即将对用户可见前调用.如果Activity 转入前台,则后接onResume(),如果Activity 转入隐藏状态,则后接onStop()

### onResume()
在Activity即将与用户交互前调用.此时Activity 处于Activity 堆栈的顶层.并具有用户输入焦点

### onPause()
当开启另一个 Activity 时调用。 此方法通常用于确认对持久性数据的未保存更改、停止动画以及其他可能消耗 CPU 的内容，诸如此类。 它应该非常迅速地执行所需操作，因为它返回后，下一个 Activity 才能继续执行。
如果 Activity 返回前台，则后接 onResume()，如果 Activity 转入对用户不可见状态，则后接 onStop()。
### onStop()
在 Activity 对用户不再可见时调用。如果 Activity 被销毁，或另一个 Activity（一个现有 Activity 或新 Activity）继续执行并将其覆盖，就可能发生这种情况。
如果 Activity 恢复与用户的交互，则后接 onRestart()，如果 Activity 被销毁，则后接 onDestroy()。

### onDestory
在 Activity 被销毁前调用。这是 Activity 将收到的最后调用。

## Fragment

### onAttach()
当Fragment 与Activity 关联时候调用
### onCreate()

### onCreateView()
Fragment 视图创建的时候

### onActivityCreated()
当Activity onCreate() 方法返回的时候调用
### onStart
参考所依附的Activity生命周期回调方法
### onResume()
参考所依附的Activity生命周期回调方法
### onPause()
参考所依附的Activity生命周期回调方法
### onStop()
参考所依附的Activity生命周期回调方法
### onDestroyView()
当Fragment 视图被移除的时候调用
### onDestroy()
### onDetach()
当Fragment 与Activity 分离开时候调用



## Service

### onCreate()
首次创建服务时调用,如果服务已经在运行,则不会调用次方法
### onStartCommand()
启动模式下的回调,当另一个组件（如 Activity）通过调用 startService() 请求启动服务时，系统将调用此方法。一旦执行此方法，服务即会启动并可在后台无限期运行。 则在服务工作完成后，可以通过调用 stopSelf() 或 stopService() 来停止服务。
### onBind()
绑定模式下的回调,当另一个组件想通过调用 bindService() 与服务绑定时，系统将调用此方法。在此方法的实现中，必须通过返回 IBinder 提供一个接口，供客户端用来与服务进行通信。请务必实现此方法，但如果并不希望允许绑定，则应返回 null。
### onDestory()
当服务不再使用且将被销毁时，系统将调用此方法。服务应该实现此方法来清理所有资源，如线程、注册的监听、接收器等。 这是服务接收的最后一个调用。


