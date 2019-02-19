# hot_reload_exception

Request to Dart VM Service timed out

发现一个导致 Flutter 热重载出现 Request to Dart VM Service timed out 异常的问题，就是当没有设置 childCount 值的 SliverChildBuilderDelegate 在 Column 内时会导致 SliverChildBuilderDelegate 的 builder 调用出现死循环，进而导致页面渲染异常，热重载异常。

在 Android Studio 中将 main.dart 文件中的 childCount: 10 这一行注释掉在 ctl + s 保存一下代码，就能复现此问题。