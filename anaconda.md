# 官网安装anaconda

* [下载地址](https://www.anaconda.com/download/) 

  ![anaconda](http://imglf3.nosdn0.126.net/img/V1RzZjNzZW9GSWlDQUV5TS9vQVVaSmU3TWJBTnErSVdyT01nU1dEWFM5NjFSNXZvOTlXWUpnPT0.png?imageView&thumbnail=1680x0&quality=96&stripmeta=0)

* 安装完成后应该这样的界面

  ![1](http://imglf3.nosdn0.126.net/img/V1RzZjNzZW9GSWlDQUV5TS9vQVVaSnlCSVRSczRVekVVSlU5TFJBMzBtWkZhdng5L1VUMFNBPT0.png?imageView&thumbnail=1680x0&quality=96&stripmeta=0 )

   jupyterlab 是jupyter的一个拓展，相对来说比较好管理多个文件

* 基本操作

  * 界面简洁，新建文件删除文件等操作很快就可以上手

  * 新建一个python3 的notebook, 可以看到以下界面

    ![2](http://imglf4.nosdn0.126.net/img/V1RzZjNzZW9GSWlDQUV5TS9vQVVaTlpDUTBGbUROUENJUVRFYlFLV01HYTA2bitaeWRMME1BPT0.png?imageView&thumbnail=1680x0&quality=96&stripmeta=0)

    一个In [] : 叫做cell , 主要的操作在红框的区域， 代码块内的操作跟正常的IDE一样，以下操作都在红框内

    * 按 'C'  复制 ，按'V' 黏贴 ，按 'M' 将cell改为markdown模式，'Ctrl + A' 全选所有代码 , 双击 'd' 删除cell
    * ‘ Shift +Enter ' 执行代码块内的语句

  * 在jupyter中可以直接调用相对路径的.py文件 ，例如：

    ```python
    import ./aaa.py
    ```

* 安装库

  * 在anaconda中安装库，十分的方便

    ![22](http://imglf3.nosdn0.126.net/img/V1RzZjNzZW9GSWlDQUV5TS9vQVVaSTdZVXNPMHpPTTBrR1V4TGZNeVUvcS9IdTFyaE1KZWVBPT0.png?imageView&thumbnail=1680x0&quality=96&stripmeta=0)

​                手动安装好后直接

​		

```python
 import numpy as np
```

* 缺点

  编写py脚本的时候还是不如用vs code , notepad++ 之类的，适合小范围的调试
