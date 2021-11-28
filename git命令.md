## git命令

**本地命令开始**

### 本质还是拷贝一份



## 初始化

git init  初始化一个本地仓库  本质创建一个.git 目录  用来存拷贝的多个版本

## 添加待拷贝的文件

git add index.html  git add .  标记为将要提交到本地仓库

git restore --staged <file>  删除add过的某文件

## 过滤器

.gitignore  过滤器 过滤不能提交的文件



## 提交（就是开始拷贝)

git status  查看文件状态

git status -sb  查看文件状态  简洁了些

git commit -m "1.0. 0"    复制一份到git目录

git commit -v  会养成好的习惯  只有提交才会拷贝到.git目录

删除文件了还要提交

## 回退（在操作之前，看下有没有没提交的文件）

git log  查看有多少版本

git reset --hard 7122c58 回退

git reflog  回退记录



## 分支（切之前要提交）

git branch 查看当前有那些分支

git branch x 创建一个分支  会基于本地仓库里最新一次 commit（提交），创建一个新的分支 x

git checkout x 切换分支

分支可以各种回退，提交互不影响

结合上面的命令一起用

相当于开了一个影分身

![branch](imgs\branch.png)



git merge x 合并分支 把**master**和x合并在一起 可能要解决冲突  x分支不会改变，就是合并一些文件。

git branch -d x 删除分支

---

## 现在是远程端用的命令

## 认证

```bash
ssh-keygen -t rsa -b 4096 -C 你的邮箱
cat ~/.ssh/id_rsa.pub                           # 得到公钥内容

# 注意私钥不要泄露
```

把公钥放到github上

![1638083304156](\imgs\1638083304156.png)

## 远程常用操作

```bash
ssh -T git@github.com   # yes 接受github的公钥
git remote add origin git@xxxxxxx  # 设置上传远程地址 可以多个  把origin变一下
git remote -v # 查看有多少远程地址
git remote remove origin #删除远程地址
git push -u origin master # 上传分支  第一次需要设置origin master，之后不用 不到万不得已不要用-f
git pull # 如果远程被改过 ，不一样 就得用pull 和本地代码合并
git push origin x:x  # 传其他分支
git clone git@xxxxxxx # 克隆|下载分支
git rebash # 美化log提交历史 ####后面补
git stash # 把文件先藏起来 ，配合git pull
git stash pop # 把藏起来的文件拿出来。
```



## git 高级操作

~~~bash
touch ~/.bashrc
echo 'alias ga="git add"'>> ~/.bashrc
echo 'alias gc="git commit -v"'>> ~/.bashrc
echo 'alias gl="git pull"'>> ~/.bashrc
echo 'alias gp="git push"'>> ~/.bashrc
echo 'alias gco="git checkout"'>> ~/.bashrc
echo 'alias gst="git status -sb"'>> ~/.bashrc
~~~



~~~bash
## 美化glog 用code在~/.bashrc 里添加
alias glog="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit -- | less"
~~~

最后 source ~/.bashrc