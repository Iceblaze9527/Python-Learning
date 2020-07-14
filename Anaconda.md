# Anaconda
  
## 0. 下载

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
## 2 基本操作
* `conda update --all`: 升级所有package
* `conda update package_name`: 升级单个的package
* `conda remove package_name`: 删除单个package
* `conda env list`: 查看Python环境



```sh
conda create -n <env_name> python=<version>
```
#### 移除Python环境
```sh
conda remove -n <env_name> --all
```
#### 重命名环境
```sh
conda create --name <new_name> --clone <old_name>
conda remove --name <old_name> --all
```
#### 导出Python环境配置
```sh
conda env export -f <config_name.yml (or.yaml)>
```
#### 导入Python环境配置
```sh
conda env create -f <config_name.yml (or.yaml)>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MTU3MTc4MjAsMTMwODc0OTYxN119
-->