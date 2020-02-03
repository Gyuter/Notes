#### Git 命令笔记

设置用户名

```
git config --global user.name "Gyuter"
```

设置电子邮件

```
git config --global user.email "zzhpro@bupt.edu.cn"
```

将目录设置为存储库的目录

```
git init
```

添加文件

```
git add readme.txt
git add <filename>
```

提交改变

```
git commit -m "added a readme file"
git commit -m <message>
```

查看状态

```
git status
```

查看修改内容

```
git diff
```

撤回 add 到 to be committed 中的修改

```
git restore --staged readme.txt
git checkout -- readme.txt
```

查看日志

```c++
git log
git log --pretty=oneline
//下面是后者的输出，最前面的一串数字是哈希值
55fbd218605fe922ee1a83fdd583840fc732533e (HEAD -> master) refined readme.txt
f4cbed177b2bd61d242059449c0b9099513c1a82 added a readme file
```

回到上一次commit的版本，每个^符号代表回退一个版本，n个^可以用HAED~n来表示

```C++
git reset --hard HAED^
//还可以使用哈希值来指定版本
git reset --hard 55fbd218605fe922ee1a83fdd583840fc732533e
```

查看命令记录

```
git reflog
```

阶段与操作示意图

![git-repo](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

撤掉暂存区的修改，重新放到工作区

```
git reset HEAD readme.txt
git restore --staged readme.txt
```

撤销工作区的修改

```
git checkout -- readme.txt
```

删除文件

```
git rm <filename>
```

产生SSH公钥

```
ssh -keygen -t rsa -C "email address"
```

要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`；

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；