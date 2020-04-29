# YK-Unit.github.io

This project is used to deploy [YorkCooking Blog Site](https://yorkfish.me) .



## 注意

#### 1. 当前仓库的默认分支为：`source`分支。

- Q：为何不让`master`分支为默认分支？
  A：因为GitHub要求：User pages must be built from the `master` branch。而静态网页工程只好放在了`source`分支。

  
  
- Q：为何把`source`分支设置为默认分支？
   A：`workflow`脚本放置在`source`分支上。其中，`workflow`脚本应用到了`repository_dispatch`事件监听功能。而该功能只在`master`分支和默认分支生效。在`master`分支已经有它用的情况下，只能选择把`source`分支设置为默认分支。
   
   > 关于`repository_dispatch`的细节可见[《外部事件：`repository_dispatch`》](https://help.github.com/cn/actions/reference/events-that-trigger-workflows#)技术文档。



#### 2. `source`分支的`workflow`脚本成功执行后，会被GitHub自动copy一份到`master`分支。

​	注意：GitHub的这种设计会有坑，若`source`分支的`workflow`脚本定义新的触发事件`test_event`供其他仓库的脚本使用，但是若由于其他原因（如toekn失效）导致其没能成功被同步copy到`master`分支，而运行在其他仓库的`workflow`脚本，即使成功发送了协商好的触发事件`test_event`，该脚本也可能无法运行。

