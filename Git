# Git使用

## 常用版本控制器  
```
cvs 集中式   
svn 集中式		
git 分布式 ：目前最先进的 分布式版本控制器
```
### 1. 在Windows 安装 Git 
```
url: https://gitforwindows.org/  
下载 git bash 软件,  
安装(直接一直点下一步即可)
```
### 2. 安装完成后
```
$ git config --global user.name "username"
$ git config --global user.email "username@qq.com"
```
### 3. SSH 远程连接仓库
```
$ ssh-keygen -t rsa -C "awaken@awaken.com" /* awaken@awaken.com自己的GITBUH的用户名 */
$ ssh -T git@github.com 校验SHH是否成功
```       

    注意：执行完命令后需要在Github中添加本地文件(C:/Users/Administrator/.ssh/id_rsa)中的私钥。
    
代码参数含义：
```
-t 指定密钥类型，默认是 rsa ，可以省略。
-C 设置注释文字，比如邮箱。
-f 指定密钥文件存储文件名。
```
以上代码省略了 -f 参数，因此，运行上面那条命令后会让你输入一个文件名，用于保存刚才生成的 SSH key 代码，如：
```
Generating public/private rsa key pair.
# Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```

当然，你也可以不输入文件名，使用默认文件名（推荐），那么就会生成 id_rsa 和 id_rsa.pub 两个秘钥文件。

接着又会提示你输入两次密码（该密码是你push文件的时候要输入的密码，而不是github管理者的密码），

当然，你也可以不输入密码，直接按回车。那么push的时候就不需要输入密码，直接提交到github上了，如：

```
Enter passphrase (empty for no passphrase): 
# Enter same passphrase again:
```

接下来，就会显示如下代码提示，如：

```
Your identification has been saved in /c/Users/you/.ssh/id_rsa.
# Your public key has been saved in /c/Users/you/.ssh/id_rsa.pub.
# The key fingerprint is:
# 01:0f:f4:3b:ca:85:d6:17:a1:7d:f0:68:9d:f0:a2:db your_email@example.com
```

当你看到上面这段代码的收，那就说明，你的 SSH key 已经创建成功，你只需要添加到github的SSH key上就可以了。

现在你需要拷贝 id_rsa.pub 文件的内容，你可以用编辑器打开文件复制，也可以用git命令复制该文件的内容，如：

```
$ clip < ~/.ssh/id_rsa.pub
```
登录你的github账号，从又上角的设置（ [Account Settings](https://github.com/settings) ）进入，然后点击菜单栏的 SSH key 进入页面添加 SSH key。

点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中，记得 SSH key 代码的前后不要留有空格或者回车。当然，上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名。默认的会使用你的邮件名称。

```
$ ssh -T git@github.com
```

当你输入以上代码时，会有一段警告代码，如：

```
The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
# Are you sure you want to continue connecting (yes/no)?
```

这是正常的，你输入 yes 回车既可。如果你创建 SSH key 的时候设置了密码，接下来就会提示你输入密码，如：

```
Enter passphrase for key '/c/Users/Administrator/.ssh/id_rsa':
```

当然如果你密码输错了，会再要求你输入，知道对了为止。

注意：输入密码时如果输错一个字就会不正确，使用删除键是无法更正的。

密码正确后你会看到下面这段话，如：

```
Hi username! You've successfully authenticated, but GitHub does not
# provide shell access.
```

如果用户名是正确的,你已经成功设置SSH密钥。如果你看到 “access denied” ，者表示拒绝访问，那么你就需要使用 https 去访问，而不是 SSH 。

### 4. 文件夹及文件操作
```
$ git add '文件名称'  --添加文件到本地库
$ git add .   // 表示添加所有的文件
$ git rm '文件名'  --删除文件
$ git rm '文件夹名' -r  --遍历删除文件夹下所有文件
```

### 5. 提交到本地仓库
```
$ git commit -m '备注信息'
```
### 6. 查看修改过的文件
```
$ git diff
```	
### 8. 克隆一个项目
```
$ git clone https://github.com/simontest9527/test9527
--把自己的Git网盘的储存库克隆到本地之后,把项目复制到里面 进行 add操作 
$ git add .  --添加全部文件到本地库
$ git commit -m '我的vue天猫项目' --commit把项目放到本地库
$ git push origin master --最后push上传 
```
### 9. 版本退回
```
$ git reset --hard HEAD^  --退回到上一个版本
$ git reset --hard HEAD^^ --上上个版本
```

### 10. 常用命令

1. 本地库初始化 
    ```
    $ git init
    ```

2. 设置签名
    作用：区分不同开发人员的身份。
    说明：这里设置的签名和登录远程库（代码托管中心）的账户没有关系。
    a. 项目级别签名:
    ```
    $ git config user.name [AAA]
    
    $ git config user.email [邮箱地址]
    
    --签名信息位置：cat .git/config
    ```
    
    b. 系统级别签名:
    ```
    $ git config --global user.name [AAA]
    
    $ git config --global user.email [邮箱地址]
    
    --签名信息位置：cd ~ 、cat .gitconfig
    ```
3. 基本操作
    ```
    $ git status   --查看状态(查看工作区、暂存区的状态) 
    
    $ git add 文件名  --添加操作(将工作区新建/修改的内容添加到暂存区)
    
    $ git commit -m “commit message” 文件名  --提交操作(将暂存区的内容提交到本地库)
    
    $ git push origin 分支名称
    ```
    

4. 查看历史记录
    ```
    $ git log

    $ git log --pretty=oneline
    
    $ git log --oneline
    
    $ git reflog (HEAD@{移动到当前版本需要多少步})
    ```
    
5. 前进和后退
    ```
    $ git reset --hard 哈希索引值 --基于索引值的操作（推荐做法）
    --示例：找回删除状态已经提交本地库的文件操作。
    
    $ git reset --hard HEAD^  --使用^符号 --（只能后退，一个^表示后退一步）
    
    $ git reset --hard HEAD~2 --使用~符号 （只能后退，n表示后退n步）
    ```

6. 比较文件差异
    ```
    $ git diff [文件名] (将工作区中的文件和暂存区的进行比较)
    
    $ git diff [本地库历史版本] [文件名]
    --(将工作区中的文件和本地库历史记录比较，不带文件名的话，会比较多个文件)
    ```
7. 分支管理
    > 在版本控制过程中，使用多条线同时推进多个任务。

    > 分支的优势？
    a)、同时并行推进多个功能开发，提高开发效率。
    b)、各个分支在开发过程中，如果某个分支开发失败，不会对其他分支有影响，失败的分支可以删除，然后重新开始即可。
        
    ```
    $ git branch -v （查看本地库中的所有分支）
    $ git branch dev (创建一个新的分支)
    $ git checkout dev （切换分支）
    $ git checkout master --切换到接收修改的分支(分支合并)
    $ git merge dev --执行merge命令(分支合并)
    ```
    
    > 注意：切换分支后，在dev分支中做出的修改需要合并到被合并的分支master上

8. 冲突解决
    > 当一个分支的内容和另一个分支的内容不同时，此时任一分支合并另一分支过程中就会出现冲突。

    > 冲突的解决办法：
        a)、编辑文件，删除特殊符号。
        b）、将文件修改完毕后，保存退出。
        c)、git add [文件名]。
        d)、git commit –m “日志信息”。

    > 注意：此时commit时不能带文件名。
