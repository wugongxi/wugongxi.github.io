一般情况下无法安装igraph因为igraph在windows下的c kernel编译有问题，同时anaconda和pip都提示你是不是与jgraph重复了，其实是不对的

顺利安装igraph步骤：

1. 按照链接[http://igraph.org/python/#pyinstallwin](http://igraph.org/python/#pyinstallwin) 上所说的，到 网址

   [http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-igraph](http://www.lfd.uci.edu/~gohlke/pythonlibs/#python-igraph)

2. 下载python_igraph-0.7.1.post6-cp27-none-win_amd64.whl

3. 将文件拷贝至工作目录下，注意上面文件cp27m对应着python27

4. 在cmd窗口下输入pip install python_igraph-0.7.1.post6-cp27-none-win_amd64.whl

   ​