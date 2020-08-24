# git的基本所用方法

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
   

