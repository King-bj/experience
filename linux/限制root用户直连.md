# experience
遇到的问题及解决方案
1.新建一个用户，用来登录
test@cloud:~> useradd test (已添加用户名test为例).

2.设置密码（需要切换到root下进行设置）
test@cloud:~> cd /root

test@cloud:~> ls

test@cloud:~> passwd test 设置密码

3.修改SSHD配置，禁用root登录
test@cloud:~> vi /etc/ssh/sshd_config

找到“PermitRootLogin yes”把后面的yes改成no。

4.启用telnet服务（如果没安装请安装）
防止sshd服务没能启动成功

5.重启SSHD服务
test@cloud:~> service sshd restart

6.下次登陆的时候先用test用户登录，然后再切换root用户即可.
以下为切换到root下命令：

test@cloud:~> su root 回车会提示输入密码,输入root密码即可切换到root权限