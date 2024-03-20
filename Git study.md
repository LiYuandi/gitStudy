# Git study

## 1.SSH配置

### 1.1配置个人信息

```bash
git config --global user.name "你的username"
git config --global user.email "你的邮箱"
```

### 1.2生成公私密钥

```bash
ssh-keygen -t rsa -C "邮箱地址"  
```



后续一直回车即可

```bash
Generating public/private rsa key pair.
Enter file in which to save the key (/home/li/.ssh/id_rsa): 
Created directory '/home/li/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/li/.ssh/id_rsa
Your public key has been saved in /home/li/.ssh/id_rsa.pub  #在此路径下用记事本打开该文件，即为公钥
The key fingerprint is:
SHA256:8tjz3McRxlPhqhm/kBQQ7Udda7ktzHtp1PKb3XZ9K5Q 2308446575@qq.com
The key's randomart image is:
+---[RSA 3072]----+
|         oo   ..+|
|          .. ...+|
|          .... * |
|           ..+B +|
|      . S  o.o*=o|
|       =  . *Eo=.|
|      . +  =.o.++|
|         + ...=.X|
|          o .o.=*|
+----[SHA256]-----+

```

### 1.3 github SSH配置   

点击github头像，settings->SSH and GPG keys->new SSH key->输入 Title和key即可。

### 1.4配置验证

```bash
ssh git@github.com
```





## 2.仅修改某个文件夹

在 GitHub 上创建一个新的仓库。您可以在 GitHub 网站上点击 "New" 按钮来创建一个新的仓库，并按照指示填写仓库名称和其他相关信息。点击 "Create repository" 完成创建。

在本地计算机上打开命令行终端或 Git Bash 终端，并进入您希望存储代码的目标文件夹。

### 2.1初始化本地存储库。在命令行中运行以下命令：

```bash
git init
```

这将在当前目录下创建一个新的本地 Git 存储库。

### 2.2关联本地存储库和远程 GitHub 存储库。运行以下命令，将 <github-repo-url> 替换为您在 GitHub 上创建的新仓库的 URL：

```bash
git remote add origin <github-repo-url>
```

### 2.3克隆远程 GitHub 存储库到本地。运行以下命令：

```bash
git clone <github-repo-url> .
```

这会将远程仓库中的文件克隆到当前目录。

### 2.4在本地进行所需的更改。假设您修改了名为 src 的文件夹中的文件。

添加已修改的文件夹到本地存储库中。运行以下命令：

```bash
git add src
```

这将会添加已修改的 src 文件夹及其内容到本地存储库中。

### 2.5提交更改。运行以下命令：

```bash
git commit -m "first commit"
```

这将提交您对 src 文件夹的更改，并提供了一个简短的描述性提交消息。

### 2.6推送更改到 GitHub。运行以下命令：

```bash
git push -u origin master
```

这将会将您的更改推送到与本地存储库关联的远程 GitHub 存储库的 main 分支。
