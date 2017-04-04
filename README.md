

# git基本操作(win10 64位环境)

1. 到官网https://git-scm.com 下载对应版本的git，由于要翻墙可以到网上搜下离线版本的，但不一定的是最新版本的，
    可以参考搜索Git-2.12.2-64-bit.exe
2. 安装的时候一般默认，点击下一步就ok
3. 本文安装的目录是C:\Program Files\Git，点击目录下git-bash.exe，配置自己的用户名和邮箱<br>
   git config --global user.name "freezyh" <br>
   git config --global user.email "2294963715@qq.com"

4. 生成密钥 （[官网](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)） <br>
   输入自己的邮箱 <br>
   ssh-keygen -t rsa -b 4096 -C "2294963715@qq.com" <br>
 `  
$ ssh-keygen -t rsa -b 4096 -C "2294963715@qq.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/admin/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/admin/.ssh/id_rsa.
Your public key has been saved in /c/Users/admin/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:C7ZctK3+SbI7BczLyX9rJgsWK1WAOScnuH39HWJI81k 2294963715@qq.com
The key's randomart image is:
+---[RSA 4096]----+
|     . o.        |
|    . * o.o   E  |
|     o O.o.+ o   |
|    . ..=+o = .  |
|      o+S+.o o . |
|     o ===. . .  |
|      + Bo.      |
|       +.=o.+    |
|        +++*..   |
+----[SHA256]-----+
`
