# 编译第三方库

以往我们最熟悉的使用三方库的方法就是从网络上下载。不过由于不同操作系统、不同编译器的存在，三方库的提供者无法枚举每一种情况，这样我们就需要通过自己的编译器来编译出我们所需要的三方库了。

## 编译Boost库

Boost库是一个经过千锤百炼、可移植、提供源代码的C++库，作为标准库的后备，是C++标准化进程的发动机之一。 Boost库由C++标准委员会库工作组成员发起，其中有些内容有望成为下一代C++标准库内容。在C++社区中影响甚大，其成员已近2000人。 Boost库为我们带来了最新、最酷、最实用的技术，是不折不扣的“准”标准库。在我们的系统中，Boost最经常用于多线程、进程间通信、虚拟内存、字符串解析等方面。

+ 动手做
参考以下链接编译Boost库
https://www.cnblogs.com/lidabo/p/3782193.html
文中的使用的编译器是VS2008，可以根据自己的实际情况进行调整。另整个Boost库的体量比较大，可以选择性编译最常用的一部分，比如Thread, Asio等等，我们在后面的动手作业中会用到。

## 编译DCMTK库

DICOM只是一个标准，委员会并不提供相应的开发包。所以每一个医学图像厂商都需要遵循DICOM标准开发自己的软件（医学图像的编码/解析/传输），但这部分的工作量难免重复。[DCMTK](https://www.dcmtk.org/dcmtk.php.en)因此应运而生，它是一个开源的软件开发包，提供了所有DICOM协议的实现，并且随着DICOM标准更新。
DCMTK的编译又有别于Boost：由于不同的编译器与IDE有不同的工程配置文件（如Visual Studio的.sln与.vcxproj），软件的提供者也无法穷尽所有的IDE，所以我们需要一种通用的工程设置格式，这是就需要用到大名鼎鼎的CMake了。

+ 动手做
参考以下链接使用CMake编译DCMTK库
https://blog.csdn.net/chaoenhu/article/details/78200274
https://blog.csdn.net/wanhongluli/article/details/77745719
DCMTK编译完成后不仅会生成类库，也会生成一些小工具，可以参考链接中的例子尝试打开一些DICOM文件。


PS：在编译三方库时，请尽量选择编译64位的动态链接库，因为这是我们软件中所使用的设置。
