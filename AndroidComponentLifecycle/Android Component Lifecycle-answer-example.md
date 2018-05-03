## Activity

### onCreate（）
	Activity正在创建，一般设置布局初始化UI元素
### onStart()
    Activity正在启动，可见但不可交互
### onReStart()
    Activity由不可见变为可见时调用
### onResume()
    Activity由已经创建完成，可见可交互
### onPause()
    Activity正在暂停，部分可见，不可交互，一般可以做些不耗时的数据处理和其他逻辑处理
### onStop()
    Activity即将停止，可以做些稍微耗时的数据处理和其他逻辑处理
### onDestroy()
    Activity即将被销毁，可以做一些资源的释放和回收工作  
### onSaveInstanceState(Bundle outState)
    Activity被异常销毁时（例如屏幕方向改变，系统资源紧张），或者跳转到其他Activity，或者按Home键回到主屏时调用，可以保存当前View组件的状态
### onRestoreInstanceState(Bundle savedInstanceState)
    Activity被系统杀死后再重建时被调用



## Fragment

### onAttach()
    首次绑定到activity时调用
### onCreate()
    fragment创建时调用
### onCreateView()
    fragment布局创建时调用
### onActivityCreated()
    activity创建完成后调用
### onStart()
    可见不可交互
### onResume()
    可见可交互
### onPause()
    正在暂停，部分可见, 不可交互
### onStop()
    即将停止，不可见
### onDestroyView()
    fragment的布局view销毁时调用
### onDestroy()
    fragment销毁时候调用，一般是宿主Activity调用onDestroy()的时候执行
### onDetach()
    fragment解除与宿主Activity时候调用

## Service 

### onCreate()
    首次创建时调用，如果服务正在运行，则不会调用
### onStartCommand()
    组件通过调用startService()方式启动服务时调用，服务会一直运行，不与启动它的组件生命周期同步，可以通过调用stopSelf()或stopService()停止服务
### onBind()
    组件通过bindService()与服务绑定时调用，一般在此方法中返回一个IBinder，组件通过此IBinder与服务进行通信
### stopService()
    手动调用，用来停止服务
### unbindService()
    手动调用，用来解绑服务
### onUnbind()
    服务被解绑时调用
### onDestroy()
    Service将被销毁时调用，可以做些清理资源之类的工作