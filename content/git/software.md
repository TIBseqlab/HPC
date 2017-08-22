## 集群软件
#### 基本原则
原则上，用户尽量把软件安装在自己的home文件夹下，这样可以保证在各个计算节点上软件的正常使用。实在有必要，请联系管理员安装部分软件。
#### 通用软件安装
###### 编辑器
|软件名称|      软件信息||
|--|--|--|
|R| 3.4.1|/public/R/3.4.1|
|zlib|1.2.8|/public/packages|
|bzip|1.0.6|/public/packages|
|pcre|8.38|/public/packages|
|curl|7.47.1|/public/packages|

为了使用/public/packages/中的软件,请把下面这段代码加入你自己的~/.bashrc文件，然后source
```bash
export PATH=/public/packages/bin:$PATH
export LD_LIBRARY_PATH=/public/packages/lib:$LD_LIBRARY_PATH 
export CFLAGS="-I/public/packages/include" 
export LDFLAGS="-L/public/packages/lib" 
```





