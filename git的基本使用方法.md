# git的基本使用方法

### 一、仓库的创建与文件的提交

1. 在Github上创建仓库

2. 通过命令行添加本地文件到仓库

   ```
   git init    #将本地文件夹初始化为git仓库
   git add .   #添加当前目录的所有文件
   git commit -m "commit"  #提交文件，并添加备注
   git remote add origin https://github.com/test   #添加远程仓库
   git push -u origin master   #提交文件到master分支
   ```
   

### 二、添加SSH

在利用http/https提交文件的时候经常要求输入账号与秘密进行验证身份。可以通过添加SSH免除每次的身份验证。

1. 生成RSA公匙，并复制

   ```
   $ ssh-keygen                #生成RSA公匙
   $ gedit ~/.ssh/id_rsa.pub   #用gedit编辑器打开，然后复制公匙
   ```

2. Github添加公匙

   Settings --> SSH and GPG keys -->New SSH Key

### 三、代码更新与回滚

