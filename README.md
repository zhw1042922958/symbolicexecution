# symbolicexecution
ubuntu下使用：
1.先安装git
2.检查ssh  ssh -T git@github.com
倘若出现 Permission denied (publickey).  则说明没有ssh密钥
3.安装ssh密钥  cd ~/.ssh  ls
查看该目录下是否已经具有ssh keys，发现并没有id_rsa（私钥）和id_rsa.pub（公钥）这两个文件
若存在 则移除 备份并移除已经存在的ssh keys
4. 没有sshkeys时执行
ssh-keygen -t rsa -C "你自己的github对应的邮箱地址"
5.将刚刚创建的ssh keys添加到github中
（1）利用gedit/cat命令，查看id_rsa.pub的内容
（2）在GitHub中，依次点击Settings -> SSH Keys -> Add SSH Key，将id_rsa.pub文件中的字符串复制进去，注意字符串中没有换行和空格。
6.再次检查： ssh -T git@github.com

下面就是开始使用github
git config --global user.name "你的github用户名"
git config --global user.email "你的github邮箱地址"

第一次上传项目到此仓库
 git init
 git add .
 git commit -m "添加说明"
 git remote add origin git@github.com:zhw1042922958/symbolicexecution.git
 git push -u origin master
 
 第二次：
 git add .
 git commit -m "添加说明"
 git push  origin master

 下载该仓库：
git@github.com:zhw1042922958/symbolicexecution.git

更新本地仓库:git pull origin master
