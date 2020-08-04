# Anaconda
  
## 0. 下载&安装
### 0.1 下载（清华大学镜像源）

### 0.2 安装

## 1. 配置TUNA镜像源
```sh
vi/code .condarc
```
写入：
```yml
ssl_verify: true
channels:
- defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
- https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```
## 2. 基本操作
* `conda update --all`: 升级所有package
* `conda update package_name`: 升级单个的package
* `conda remove package_name`: 删除单个package
* `conda env list`: 查看Python环境
* `conda create -n <env_name> python=<version>`: 创建环境
* `conda create -n <new_name> --clone <old_name>`: 克隆环境
* `conda env export -f <config_name.yml (or.yaml)>`: 导出Python环境配置
* `conda env create -n env_name -f <config_name.yml (or.yaml)>`: 导入Python环境配置

### 2.1 升级 anaconda
```
conda update conda
conda update anaconda
```

### 2.2 移除环境
* `conda remove -n <env_name> --all`
* `conda env remove -n <env_name>`

## 3. conda 包的编译
https://docs.conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs.html

https://github.com/wolny/pytorch-3dunet/tree/master/conda-recipe


https://blog.csdn.net/nima1994/article/details/103064351


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExODc4MzY2MjQsLTIwODg5NjM2NzksMT
U4MTkwNjgxMiwxOTY1NTUwNzExLDMxNzYxNzczNSwtMTk2NjIx
MzA4NSwxNzYyMzIxODk2LDEzMDg3NDk2MTddfQ==
-->