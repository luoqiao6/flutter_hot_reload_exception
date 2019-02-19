# hot_reload_exception

Request to Dart VM Service timed out

发现一个导致 Flutter 热重载出现 Request to Dart VM Service timed out 异常的问题，就是当 当没有设置childCount 值的 SliverChildBuilderDelegate 在 Column 内时会导致 SliverChildBuilderDelegate 的 builder 调用出现死循环，进而导致页面渲染异常，热重载异常。