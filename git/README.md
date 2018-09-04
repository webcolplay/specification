## 创建分支

```
 // 新建本地分支
 git checkout master
 git pull origin master
 git checkout -b [branch-name]

 // 新建远程已有的本地分支
 git checkout -b [branch-name] origin/[branch-name]
```


## 修改和提交

```
 // 查看状态
 git status

 // 查看变更内容
 git diff
 
 // 跟踪所有改动过的文件
 git add .
 
 // 跟踪指定的文件
 git add <file>
 
 // 文件改名
 git mv <old> <new>
 
 // 删除文件
 git rm <file>
 
 // 停止跟踪文件但不删除
 git rm --cached <file>
 
 // 提交所有更新过的文件
 git commit -m "commit messages"
 
 // 修改最后一次改动
 git commit --amend
```


## 



## 查看提交历史

```
 // 查看当前分支的存在提交历史记录,不包括删除的或被合并的提交
 git log
 
 // 查看当前分支所有操作历史，历史提交记录，撤销，合并提交等详细历史记录
 git reflog
 
 // 查看指定文件的提交历史
 git log -p <file>
 
 // 以列表方式查看指定文件的提交历史
 git blame <file>
 
 
```


##  撤销/回滚:Checkout、Reset、Revert


| 命令 | 作用域 | 常用情景 |
| ----- | ----- | ----- |
| git checkout | commit | 切换分支或查看旧版本 |
| git checkout | file | 舍弃工作目录中的更改 |
| git reset | commit | 私有分支 |
| git reset	| file | 将文件从缓存区中移除,--soft、--mixed 和 --hard参数无效 |
| git revert | commit | 公共分支 |
| git revert | file | 无 |


**git仓库组成部分：**
![](https://camo.githubusercontent.com/eacc3cd372cf72b9902a1ff40b3db89df00e7539/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30312e737667)


### git checkout

```
 // commit
 git checkout HEAD~2
 
 // 清空工作区域的改动
 git checkout .
```

![](https://camo.githubusercontent.com/b6b326af6c5f485ea326120dd2f1f78e741d1748/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30352e737667)


```
 // file，更改工作目录而不是缓存区
 git checkout HEAD~2 foo.py
```

![](https://camo.githubusercontent.com/cf90b3529e12e1ccb439d1b45513e187fc90291d/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30382e737667)


### git reset

```
 git reset HEAD~2
```

![](https://camo.githubusercontent.com/3d55df040cb530482894661b35212b83ff4e5e14/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30322e737667)


 * --soft：缓存区和工作目录都不会被改变
 * --mixed：默认选项。缓存区和你指定的提交同步，但工作目录不受影响
 * --hard：缓存区和工作目录都同步到你指定的提交
  
![](https://camo.githubusercontent.com/6f605243c7eedce24cd32e53348d7f5b2db20bff/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30332e737667) 


```
 // file,缓存区同步到你指定的那个提交
 git reset HEAD~2 foo.py
```

运行 git reset HEAD foo.py 会将当前的 foo.py 从缓存区中移除出去，而不会影响工作目录中对 foo.py 的更改。

![](https://camo.githubusercontent.com/9919767b710f165cb3ee6b18cf32356a220e814f/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30372e737667)


### git revert

```
git revert HEAD~2
```

![](https://camo.githubusercontent.com/ca3c454935277b49e1c75e04644d979e796c50e8/68747470733a2f2f7777772e61746c61737369616e2e636f6d2f6769742f696d616765732f7475746f7269616c732f616476616e6365642f726573657474696e672d636865636b696e672d6f75742d616e642d726576657274696e672f30362e737667)


## 合并与衍合:merge rebase

```
 // 使用非快进方式合并分支
 git merge --no-ff [branch-name]
 
```
![](https://sfault-image.b0.upaiyun.com/415/067/4150677953-54b1020caf45c_articlex)

```
 // 合并多次commit信息，已经提交到服务器的不要修改
 git rebase -i HEAD~2
```



