CentOS 6编译安装Python3.6.5

https://blog.csdn.net/qq_33841518/article/details/72831372

```
cd /usr/local/src
wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz 
```

```
tar -zxvf Python-3.6.5.tgz
```

```
cd Python-3.6.5
```

```
./configure --prefix=/usr/local/python
make && make install
```

```
echo PATH='/usr/local/python/bin/:$PATH' >> /etc/profile
source /etc/profile
```

问题：

```
configure: error: no acceptable C compiler found in $PATH
```

https://stackoverflow.com/questions/19816275/no-acceptable-c-compiler-found-in-path-when-installing-python

```
yum groupinstall "Development Tools"
```



```
zipimport.ZipImportError: can't decompress data; zlib not available
```

https://unix.stackexchange.com/questions/291737/zipimport-zipimporterror-cant-decompress-data-zlib-not-available

```
yum install zlib-devel
```



https://stackoverflow.com/questions/41328451/ssl-module-in-python-is-not-available-when-installing-package-with-pip3

```
yum install openssl-devel
```

再重新编译一遍

成功