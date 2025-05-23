## git 常用指令

### 常用

`git init` 初始化

`git add target_file` 或 `git add .` 添加文件到暂存区

`git commit -m "first commit"` 提交暂存区文件到仓库区

`git remote add origin https://github.com/username/reponame.git` 关联远程仓库

`git push -u origin master` 推送代码到远程仓库

`git pull upstream master` 拉取远程仓库最新代码

### git config
`git config --list` 查看配置信息  
`git config --global user.name "xxx"`  
`git config --global user.email "xxx@xxx.com"`

### git clone

`git clone https://github.com/username/reponame.git`

### git branch

`git branch` 查看本地分支

`git branch -r` 查看远程分支

`git branch -a` 查看所有分支

`git branch new_branch` 创建新分支

`git checkout new_branch` 切换到新分支

`git checkout -b new_branch` 创建并切换到新分支

`git push --set-upstream origin <branch-name>` 推送到并创建（如果不存在）远程分支

`git branch -d new_branch` 删除本地分支

`git push origin --delete new_branch` 删除远程分支

## 报错处理

1
```
ssh: connect to host github.com port 22: Connection refused
```
意思是ssh连接不上github 22端口，一般是加速器问题，比如把watt关掉就好了。

如果关掉之后不行先试试切换成443端口，注意第二行地址是ssh.github.com而不是github.com。
```
ssh -T -p 443 git@ssh.github.com
git remote set-url origin git@ssh.github.com:USERNAME/REPONAME.git
```
还是不行就要考虑是不是dns被污染了，输入`ssh -vT git@github.com`查看，如果github.com解析成了\[127.0.0.1\]或者\[::1\]，就说明被污染了，试试在cmd里输入`ipconfig /flushdns`刷新dns缓存，再不行只能去C:/Windows/System32/drivers/etc/host文件里改域名映射，把`127.0.0.1 github.com`这一行删掉改成`140.82.112.4 github.com`。后面这个地址来自[https://dnschecker.org/](https://dnschecker.org/)，可以查到github.com的ip地址，我这里是找了最上面一个。

2
```
warning: LF will be replaced by CRLF the next time Git touches it
```
意思是git在提交时，会把LF替换成CRLF，因为git默认使用LF作为换行符，而windows使用CRLF作为换行符

如果不想看warning可以关掉，使用``git config --global core.autocrlf false``

3
```
error: src refspec main does not match any
error: failed to push some refs to 'github.com:Cousprr/left_for_world.git'
```
意思是本地分支main没有和远程分支匹配，（因为远程分支是master而不是main）可以尝试``git push origin master``