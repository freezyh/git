

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
   过程中回车就行了<br>
    Generating public/private rsa key pair. <br>
    Enter file in which to save the key (/c/Users/admin/.ssh/id_rsa): <br>
    Enter passphrase (empty for no passphrase): <br>
    Enter same passphrase again: <br>
    Your identification has been saved in /c/Users/admin/.ssh/id_rsa. <br>
    Your public key has been saved in /c/Users/admin/.ssh/id_rsa.pub. <br>
   用编辑器打开位于c/Users/admin/.ssh/id_rsa.pub的文件,复制就行了<br>
5. 登录你的github，点击头像的下箭头，Settings,SSH and GPG keys, New SSH key,输入title,key的输入框粘贴前面复制的，最后点击Add SSH key,这样就完成了基本的配置。

