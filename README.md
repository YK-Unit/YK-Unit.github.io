# YK-Unit.github.io

This project is used to deploy [YorkCooking Blog Site](https://yorkfish.me) .



## 注意

当前仓库的默认分支为：`source`分支。

Q：为何不让`master`分支为默认分支？

A：因为GitHub要求：User pages must be built from the `master` branch。而静态网页工程只好放在了`source`分支。



Q：为何把`source`分支设置为默认分支？

A：`workflow`脚本放置在`source`分支上。其中，`workflow`脚本应用到了`repository_dispatch`事件监听功能。而该功能只在`master`分支和默认分支生效。在`master`分支已经有它用的情况下，只能选择把`source`分支设置为默认分支。

> 关于`repository_dispatch`的细节可见[《外部事件：`repository_dispatch`》](https://help.github.com/cn/actions/reference/events-that-trigger-workflows#)技术文档。

