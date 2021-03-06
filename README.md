# 提示

此项目存放的是一些笔者日常开发总结的一些知识片段，现在改到语雀进行维护。

https://www.yuque.com/yinzhi/dgritd

# 其他结构化知识

1、PowerShell: [https://github.com/x-cold/TipsAboutPowerShell](https://github.com/x-cold/TipsAboutPowerShell)

2、Windows Batch: [https://github.com/x-cold/TipsAboutBatch](https://github.com/x-cold/TipsAboutBatch)

# Linux

## 进程控制

1、Kill Process

```bash
sudo kill -s 9 $(ps aux | grep 'node' | grep -v grep|  awk '{print $2}')
```

```bash
sudo kill `pgrep vim`
```


2、Fork Bomb

> Detail: [https://linux.cn/article-5685-1.html](https://linux.cn/article-5685-1.html)

```bash
:(){:|:&};:
```

# Git

## Rebase

1、rebase 流程解释

```plain
git rebase 
while(存在冲突) {
    git status
    // 查找和处理冲突
    git add -u
    if (需要修改 commit 信息) {
        git commit --amend --author
    }
    git rebase --continue
    // 慎用 git rebase --skip
    if( git rebase --abort )
        break; 
}
```

# Windows

## VirtualBox

* windows 后台启动

```cmd
@echo off
pushd "C:\Program Files\Oracle\VirtualBox"

VBoxManage.exe startvm "HadoopMaster" -type headless
VBoxManage.exe startvm "HadoopSlave1" -type headless
```

* windows 停止虚拟机

```cmd
@echo off
pushd "C:\Program Files\Oracle\VirtualBox"

VBoxManage.exe controlvm "HadoopMaster" poweroff 
VBoxManage.exe controlvm "HadoopSlave1" poweroff 
```

