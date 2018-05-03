## Activity

<!--  每个模块的回调需要按照调用顺序排列  -->
### onCreate（）
一般初始化UI元素

### onRestart()
一般是处于stopped状态恢复到可见状态时才会调用
### onStart()
与onStop相对应，在此方法中创建资源，或者检查某些资源是否可用，发起某种操作。
### onRestoreInstanceState()
系统仅在存在需要恢复的状态信息的时候才会调用该方法，将会回调该方法将bundle传进来用于恢复状态。
### onResume()
开始动画与初始化那些只有在获取用户焦点时才需要的组件，包括相机的预览等
### onPause()
一般在这个方法中停止正在运行的动画，或者其他操作，如视频的播放，相机的释放等
### onStop()
由于切换Activity的时候，例如ActivityA->ActivityB,会先执行当前ActivityA的onPause方法，然后调起ActivityB，等到ActivityB的生命周期走到onResume结束后，再执行ActivityA的onStop等及之后的生命周期方法，所以一般不在onPause方法中执行耗时操作，包括存储数据到数据库中等，而放在onStop中执行。

释放所有不再需要的资源，一旦Activity停止之后，有可能系统会因各种原因将APP杀死而不会调用Activity的onDestroy
,避免内存泄漏。

### onSaveInstanceState()
该方法可能在onDestroy之前的任何时候调用，当activity不是回退栈操作，而直接跳离开activity时，会执行该回调方法。
### onDestroy()
最后清除可能导致内存泄漏的地方，确保所有线程都被destroyed。

## Fragment

### onAttach()
执行该方法时即Fragment成为了Activity的一部分，从这里开始可以获取父Activity的对象。
### onCreate()
该方法中可以初始化要保持着的必要组件，非view，当Fragment在暂停或者停止状态之后可以重新启用它们。
### onCreateView()
第一次为Fragment绘制用户界面时会调用此方法，返回要展示的view。

### onViewCreated()
完成生成需要展示的view
### onActivityCreated()
当父Activity和当前Fragment的UI都完整创建完的时候被调用，初始化某些建立在父Activity和Fragment的UI的元素
### onStart()
Fragment可见时需调用
### onResume()
Fragment可进行交互的时候调用
### onPause()
Fragment 变得可见但不可交互
### onStop()
Fragment 变得不可见，可在这里添加存储操作，同Activity的onStop
### onDestroyView()
当Fragment的UI被分离的时候，清除所有和视图相关的资源，如网络请求不再想view发送数据。
### onDestroy()
该方法需要清除所有的资源，线程等。
### onDetach()
Fragment从父Activity分离
## Service

### onCreate()
服务创建的方法，在服务第一次被启动时会执行
### onStartCommand()
服务开始执行
### onBind()
服务绑定
### onUnbind()
解绑服务
### onDestroy()
销毁服务。当停止服务时，如果此时还有未解绑的部分，将不会进行销毁。

## Activity FrameLayout直接添加Fragment

1. Activity: onCreate
- Activity: onStart **start** ( **start** 和 **end** 之间表示这一段依旧在 **onStart** 的执行方法中)
- Fragment: onAttach
- Fragment: onCreate
- Fragment: onCreateView
- Fragment: onViewCreated
- Fragment: onActivityCreate
- Fragment: onStart
- Activity: onStart **end**
- Activity: onPostCreate
- Activity: onResume
- Fragment: onResume

这个时候fragment正常显示

1. Activity: onPause **start**
- Fragment: onPause
- Activity: onPause **end**
- Activity: onStop **start**
- Fragment: onStop
- Activity: onStop **end**
- Activity: onDestroy **start**
- Fragment: onDestroyView
- Fragment: onDestroy
- Fragment: onDetach
- Activity: onDestroy **end**


------
未完待续。。。