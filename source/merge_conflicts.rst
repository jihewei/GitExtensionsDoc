合并冲突
===============

当进行分支合并或者提交更新时，伴有冲突发生。Git会尝试自动解决，对于解决不了的则需要人工干预。这个时候Git Extensions会显示冲突警告。

.. image:: /images/merge_conflicts.png

处理冲突
----------------------

当点击冲突警告时，处理冲突窗口就是冒出来。当然你也可以从菜单调出处理冲突窗口。接下来就可以双击一个文件开始解决了。

.. image:: /images/resolve_merge_conflicts.png

冲突有三类：

+---------------------------------------+-------------------------------+
|File deleted and changed               | Use modified or deleted file? |
+---------------------------------------+-------------------------------+
|File deleted and created               | Use created or deleted file?  |
+---------------------------------------+-------------------------------+
|File changed both locally and remotely | Start merge tool.             |
+---------------------------------------+-------------------------------+


如果文件在一个提交中标记为删除，另外一个提交而是修改，窗口就是提示保留修改还是删除，也就解决了。而对于本地与远程同时修改的情况，
冲突合并工具就会被自动打开。其中合并工具可以配置，下面的图片是P4Merge。Git Extensions的安装包打包的是KDiff3。

在合并工具中，冲突文件会有4个版本在不同的区域展示：

+--------+----------------------------------------------------------------+
|Base    | The latest version of the file that exist in both repositories |
+--------+----------------------------------------------------------------+
|Local   | The latest local version of the file                           |
+--------+----------------------------------------------------------------+
|Remote  | The latest remote version of the file                          |
+--------+----------------------------------------------------------------+
|Merged  | The result of the merge                                        |
+--------+----------------------------------------------------------------+

.. caution::

    When you are in the middle of a merge the file named local represents your file. When you are in the middle of a rebase the 
    file named remote represents your file. This can be confusing, so double check if you are in doubt. 

.. image:: /images/perforce_p4merge.png

