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

### 2.3 重置环境
1.  `conda list --revisions`  
    查看历史，按需选择 `REV_NUM` 数值。一般情况下，0表示是第一次安装，包括root环境和conda命令，所以**一般为1或之后**。
    
2.  `conda install --revision REV_NUM`  
    稍等片刻，即可重置。

## 3. conda 包的编译
-   Run: `conda build conda-recipe/ -c conda-forge`
-   Install locally with `conda install --use-local pytorch-3dunet -c conda-forge` (optional)


https://docs.conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs.html

https://github.com/wolny/pytorch-3dunet/tree/master/conda-recipe





<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY0NTc4NzcsMjAxNDI0MzM4MywtMjA4OD
k2MzY3OSwxNTgxOTA2ODEyLDE5NjU1NTA3MTEsMzE3NjE3NzM1
LC0xOTY2MjEzMDg1LDE3NjIzMjE4OTYsMTMwODc0OTYxN119
-->