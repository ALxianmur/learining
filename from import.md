这里介绍python中import的用法

import 本质是调用其他的资源，避免重复造轮子，实现高效编程
写法有好几种
~~~
import package_name
from package_name import module_name
from .package_name import module_name
~~~
# 文件地址的写法有两种：
相对地址
绝对地址

# 资源调用的顺序
1. 当前文件夹 
2. 系统环境zpzp
3. `python`安装的位置

# 调用文件的类型

第三方库
本地文件
标准库

# 调用原理
简单来说，我们日常看到的`.py`文件，都称作是一个`module`。

当你的 python 代码需要获取外部的一些功能（一些已经造好的轮子），你就需要使用到 `import` 这个声明关键字。`import`可以协助导入其他 module 。（类似 C 预约的 `include`）

`import` 声明是常见的导入方式，但它不是唯一的方式。即其实可以通过其他方式进行 module 导入。

`import` 语句结合了两个操作：

1. **搜索命名模块**。通过传入合适的参数调用 `__import()__` 实现。
2. **将搜索的结果绑定到本地命名空间**。 `__import()__` 的返回值用作命名空间绑定操作。

`import` 语句执行时，`__import__()` 会被调用，Python 会查找 module 并创建一个 module object 并初始化它；如果 module 没找到，会抛出 `ModuleNotFoundError`的一个 exception 。 

# `import` vs `__import__()`

简单来说，调用`__import__()` 只是 `import` 声明操作的一个子集。

直接调用 **import**() 仅执行模块搜索，如果找到，则执行模块创建操作。虽然可能会出现某些副作用，例如导入父包，以及更新各种缓存（包括 sys.modules），但只有 import 语句执行名称绑定操作。


# 参考来源：
+ [Python中import的用法总结_pycharm import_易冷cheng的博客-CSDN博客](https://blog.csdn.net/qq_41092406/article/details/118203572)
+ [Python Import 详解 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/156774410)
+ [**python import 原理剖析-腾讯云开发者社区-腾讯云 (tencent.com)**](https://cloud.tencent.com/developer/article/1847428)
2023-08-29