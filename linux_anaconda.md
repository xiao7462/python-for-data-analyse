1. linux 下安装anaconda [官网](https://www.anaconda.com/download/)下载对应的linux版本
    `bash Anaconda3-5.3.1-Linux-x86_64.sh` 一路yes ,Enter


2. 安装python包: 由于之前安装了其他版本的conda,所以先 `cd ~/anaconda/bin` 进入安装的conda目录，再` ~/anaconda3/bin/conda install keras`

3. 修改jupyter的文件夹：
    * 输入 `jupyter notebook --generate-config` 
    该命令会在用户的主目录下创建一个隐藏的.jupyter文件夹，并在文件夹下生成jupyter_notebook_config.py文件
    * `vim ./.jupyter/jupyter_notebook_config.py` 
    后找到并改变     
    `c.NotebookApp.notebook_dir = '/your/file/saved/path/'` 换成想要的文件夹位置

4. 运行jupyter-lab(同理可以jupyter-notebook): `nohup jupyter-lab --no-browser --NotebookApp.token='' >/dev/null 2>&1 &`   
可以先直接`jupyter-lab`查看localhost的地址   # 不建议自己设置localhost的IP,jupyter会自动分配

5. 在windows的cmd下输入 `ssh -N -L 8888:localhost:8888 your_server_username@your_server_ip` 其中8888就是linux上运行jupyter的localhost IP

6. 在浏览器上输入 `http://localhost:8888`
