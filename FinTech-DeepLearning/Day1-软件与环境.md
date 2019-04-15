# **Day 1**&emsp;[[目录]](../README.md)

## Anaconda

### 一、介绍

1. 用来管理Python所用的包和环境
2. 用来创建虚拟环境，处理多个项目
3. Anaconda附带了`conda`、`Python`和150多个科学报及依赖
    >* `conda`是包和环境管理器，只能通过`命令行`使用
    >* 为什么使用`Anaconda`？答：它附带一批数据科学必须的包，方便数据处理工作
    >* 使用`conda`来管理包和环境能减少将来在处理数据过程中使用到的各种库与版本时遇到的问题

### 二、安装使用（Windows）

1. *进入conda环境：* cmd中输入`conda activate [env_name]`
    >eg: `conda activate base`&emsp;&emsp;进入名为base的环境  
ps：通常cmd内需要先执行`conda init`，然后重开cmd
2. *退出conda环境：*`conda deactivate`
3. *查看已安装的包：*`conda list`
   >推荐在默认环境下更新所有的包&emsp;&emsp;`conda upgrade --all`
4. *安装某个包：*`conda install [pkg1_name] [pkg2_name] ...`
   >可指定包版本&emsp;&emsp;eg：`conda install numpy=1.10`  
conda会自己解决依赖问题
5. *更新某个包：*`conda update [pkg_name]`  
*&emsp;&emsp;PS:更新所有包：*`conda update --all`
6. *删除某个包：*`conda remove [pkg_name]`