# git基本用法(win10 64位环境)
请原谅我的懒惰，很多没有截图^=^.........

## 一、基本配置
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

## 二、下载自己的文件
1. 很多时候我们可以下载别人开源的项目代码，也经常上传、下载自己的分享，这里简单介绍如何下载自己的文件,我们可以在github新建一个仓库，至于如何新建可以搜索【github 新建仓库】，说lowd点就是新建文件夹，本文的文件夹是git。新建完以后有个Clone or download按钮，我们一般下载自己的都用use SSH <br>
  复制链接 https://github.com/freezyh/git.git <br>
2. 打开cmd命令，本文把下载的文件放到c:\gitdown， 所以命令行输入的是：<br>
   git clone https://github.com/freezyh/git.git   <br>
   实际效果：<br>
   c:\gitdown>git clone https://github.com/freezyh/git.git   <br>
   然后我们就可以修改自己的资料了，比如本文修改README.md文件，修改完以后如何提交呢？<br>
3. 下载以后进入目录，本文的是git,如果你命名的就cd 你命名的，本文的是前面的cmd命令拉取下来文件以后继续操作cmd git来进入目录。<br>
   提交文件之前，我们现在先看下资料的状态<br>
   使用命令git status <br>
   能看到红色字体标注的modified:   README.md <br>
   知道就修改了就行了，不是每次都需要看 <br>
4. 我们要把修改的文件提交需要使用git add '文件名' <br>
    本文是git add README.md    <br>
    执行了命令文件还是没有成功提交到github的，我们可以继续使用git status命令查看形状和提示
    你会发现modified:   README.md 变绿色了，其他先不管什么意思<br>
    到github查看README.md文件并没有修改，那就说明没有上传成功，我们需要继续如下操作。
5. git commit -m "修改备注信息" <br>
    我们修改了以后需要备注修改了哪些内容，以便以后恢复或者其他人参考 <br>
    本文：git commit -m "fix"  <br>
    有了这一步，文件还是没有提交到github，我们还要继续下一步。
6. git push 这一步就成功提交啦。

## 三、批量添加文件
git add .    <br>
不加参数默认为将修改操作的文件和未跟踪新添加的文件添加到git系统的暂存区，注意不包括删除<br>

git add -u .  <br>
-u  == --update 表示将已跟踪文件中的修改和删除的文件添加到暂存区，不包括新增加的文件，注意这些被删除的文件被加入到暂存区再被提交并推送到服务器的版本库之后这个文件就会从git系统中消失了。

 git add -A .  <br>
-A == --all 表示将所有的已跟踪的文件的修改与删除和新增的未跟踪的文件都添加到暂存区。

## 四、忽略不需要上传的文件夹
打开Git Bash 输入touch .gitignore <br>
生成 .gitignore，打开这个文件输入你想要忽略的文件夹，比如忽略node_modules这个文件夹，我们就需要在.gitignore输入/node_modules/，当然有更多过滤的规则，后续补上。。

## 五、历史记录
git log <br>
按小写q可以退出<br>

如果觉得界面不好看可以使用下列指令<br>
git log --pretty=oneline <br>

Git中，使用HEAD表示目前的版本 <br>
git reset --hard HEAD <br>

如果现在把目前版本退回到上一个版本 <br>
git reset --hard HEAD~1   <br>
上上一个版本就是HEAD~2 <br>
git reset --hard HEAD~2 <br>

如果要指定回到某个特定版本：<br>
git reset --hard XXXXXXX<br>
版本号没必要全部都写，写前几位就可以了,git会自动去找 <br>
git push -f -u origin master <br>

当你退回到某个版本的时候，想恢复到之前的新版本 <br>
git reflog <br>
git reset --hard XXXXXX<br>
git push orighin master <br>

###checkout
git checkout -- file 可以丢弃工作区的修改

## 六、新建与合并分支branch
通常开发的时候，大家都是从 master 做一个分支 branch 出去，最后再 merge 回 master，确保大家都是使用最新的master

git branch 查看目前分支 <br>

创建分支<br>
git branch zyh <br>
git checkout zyh <br>
在分支zyh分支上进行的任何修改操作，然后执行git add 和git commit合并到master分支上<br>







