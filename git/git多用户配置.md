# experience
遇到的问题及解决方案
1.检查电脑是否已有ssh key
`
$ cd ~/.ssh
$ ls
`
2.创建一个shh key
$ ssh-keygen -t rsa -C "your_email@example.com"

3.运行上条命令输入文件名
你可以不输入文件名，使用默认文件名，那么就会生成 id_rsa 和 id_rsa.pub 两个全局默认的秘钥文件，前者为私钥，后者为公钥。
当然我们有两个代码仓库，所以最好写上文件名，如id_rsa(公司)或id_rsa_user2(个人). 这样ssh目录下会生成id_rsa.pub和id_rsa_user2.pub两个文件

接着又会提示你输入两次密码（该密码是你push文件的时候要输入的密码，而不是github管理者的密码）。也可以直接按回车键，那么push的时候就不需要输入密码，直接提交到github上了 

4.添加shh key 到github上
5.创建config文件 
$ touch config
6.添加内容
# Default gitLab user
Host gitlab.com
HostName gitlab.com
User git
IdentityFile ~/.ssh/id_rsa

# second user
Host github-king
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_user2 

7.下载的时候把git ssh地址修改 从 git@github.com:xxx/xxxx-xxx.git 到 git@github.king:xxx/xxxx-xxx.git。

用户名不正确，修改你提交项目处的用户名和邮箱
git config user.name：查看用户名
git config user.email：查看邮箱
git config user.name "你的用户名"：修改你本地一个仓库的用户名
git config user.email"你的邮箱"：修改你本地一个仓库的邮箱
git config --global user.name"你的用户名"：修改全局仓库的用户名
git config --global user.email"你的邮箱"：修改全局仓库的邮箱 