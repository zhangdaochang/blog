# linux 常用命令

### too long; didn't read.  太长了，不想读

```bash
yarn global add tldr #展示出某个命令的常用选项
tldr ls
tldr cp
```

## 该有的空格一定要有 不能省了

## 不要随便删除系统的文件，有可能出发重装系统套餐

## ~代表用户目录,进入命令行第一件事就是 cd~

## bash 双感叹号执行上一次命令

```bash
ls
!!  # 还是执行的ls alt+. 也是类似的效果
echo -e "卢本伟牛逼!! \n 全体起立" > 1.txt # 其中的双感叹号会替换成上一次执行的命令
```

## ctrl+c  救命大法

当你用错命令 可以  

```javascript
ctrl + c
```

让时光倒流 骚年 大胆去搞吧 ！！

## 查看当前路径

```bash
pwd
λ pwd
/d/SoftWare/cmder
```

## 查看目录有啥

```bash
ls # 查看当前目录
ls /data # 指定目录有啥
ls -l # 显示详细信息
```

## 查看文件内容

```bash
cat index.js # 全部显示
head index.js  # 前10行  --n 14 加参数显示前多少行
tail index.js  # 后10行  --n 14 加参数显示后多少行
less index.js  # 翻页  按'q'退出 '↑↓'翻页 j和'↓' k '上
```

## 自动补全

按tab键可以补全

## 清屏

```bash
clear # 清屏
```

## 创建文件

```bash
touch 1.txt  # 创建文件 || 更新文件最后操作日期
touch 1.txt 2.txt ... # 可以创建多个
touch a/1.txt # 要确定有没有这个目录 没有就会 No such file or directory
```

## echo 创建文件

```bash
echo 卢本伟牛逼! > 1.txt # 会覆盖当前文件
echo 全体起立!! >> 1.txt # 追加文件
echo -e "卢本伟牛逼 \n 全体起立" > 1.txt # 特殊的符号都得加双引号
```

## 制作目录

```bash
mkdir b  # 制作一个b目录
mkdir b c# 制作两个目录 1个是b  1个是c 可以多个 mkdir a b c ...
mkdir -p a/b/c/d/e # 创建多级目录

```

## 拷贝

```bash
cp 源文件 目标文件 # cp 1.txt 2.txt 复制到其他的目录要确保目录存在 不存在会报 No such file or directory
cp -r 源目录 目标目录 # cp -r a b
# -r 递归的意思
```

## 删除文件

```bash
rm 1.txt # 删除文件
rm -r a # 删除目录
rm -rf a # 强制删除
```

## 打开文件方式

```bash
start 1.txt ## 用默认软件打开文件
code 1.txt ## 用vscode 打开文件
```

## 清空文件

```bash
echo '' > 1.txt # 用空覆盖文件
```

## 显示命令在那个目录

```bash
λ which tldr
/c/Users/Admin/AppData/Local/Yarn/bin/tldr
```

## 移动目录||重命名文件

```bash
 mv 1.txt b/2/3.txt #  移动1.txt 到 b/2目录 要确定目录存在
 mv 1.txt 2.txt # 将1.txt 重命名为 2.txt
```

# shell脚本(后面补充)

## 用&& 这个组合的命令 只有左边成功才会执行 右边的命令 

## 用; 这个组合的命令 不管左边是否成功都会执行 右边的命令

<u>shebang</u>

成功什么也不提示 会返回 0  ，失败会提示error  返回非0 例如  1，2，3，4 ...

chmod +x 给执行权限

echo $?  给出上条命令的执行结果