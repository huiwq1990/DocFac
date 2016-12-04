

### 配置环境遍历

```
# 将anaconda的bin目录加入PATH，根据版本不同，也可能是~/anaconda3/bin
echo 'export PATH="/opt/program/anaconda3/bin:$PATH"' >> ~/.bashrc
# 更新bashrc以立即生效
source ~/.bashrc
```


### 添加国内镜像

```
# 添加Anaconda的TUNA镜像
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
# TUNA的help中镜像地址加有引号，需要去掉

# 设置搜索时显示通道地址
conda config --set show_channel_urls yes
```


nohup wget https://repo.continuum.io/archive/Anaconda2-4.2.0-Linux-x86_64.sh &



su tf
nohup jupyter-notebook --port=8998 --ip=123.57.230.238 --no-browser &

jupyter-notebook --port=8998 --ip=123.57.230.238 --no-browser


### anconda 多环境配置

创建Python2.7
conda create -n python2 python=2.7 anaconda

This will create an environment named python2 that contains the Python 2.7 version of Anaconda. You can activate this environment with

source activate python2
source deactivate python2




### conda使用

http://conda.pydata.org/docs/commands/conda-install.html

### 参考

http://www.jianshu.com/p/2f3be7781451

http://www.jianshu.com/p/d2e15200ee9b