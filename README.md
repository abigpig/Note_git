# Note_git指令




--git order-- 
   


certutil -hashfile D:\1.exe MD5
certutil -hashfile D:\1.exe SHA1
certutil -hashfile D:\1.exe SHA256

eg: certutil -hashfile C:\Users\EminemRen\Desktop\ZippMini_02_423_FULL_20160825.zip MD5


adb shell pm clear com.libratone 清缓存
adb devicse 查看所有连接的设备
adb uninstall com.libratone 卸载app


gitk  (图形化 log)

cd .. 返回上一级目录（有空格） 
cd ../.. 返回上两级目录 （有空格） 
ls 查看目录中的文件 
pwd 显示工作路径
mkdir abc  创建abc文件夹
rmdir abc  删除abc文件夹
clear 清屏
 

git log   查看日志  ( q  退出 )
git config --list  本地配置信息


每次提交，执行以下步骤 ：

1.git status 当前分支状态
2.git add   追加对某文件的追踪 /  将修改的文件添加到暂存区域 一遍可以commit 
  git add . 将所有改动暂存

eg : git add  app/src/main/java/com/libratone/v3/activities/SpeakerSoundSpaceActivity.java

3.git diff  要查看尚未暂存的文件更新了哪些部分
4.git commit -m ""   提交更新加信息 Git 每次提交代码，都要写 Commit message（提交说明），否则就不允许提交   (shift +q 退出)
5.git push origin xxx    上传到某个分支
6.git fetch 下载所有远程分支最新代码到本地
7.git fetch origin master 下载某个远程分支最新代码到本地
8.git merge origin master  合并某个分支到当前本地分支
9.git push origin xxx    与master代码合并，解决冲突确定没问题了，推最新代码到远程自己的分支上


git fetch 命令只是将远端的数据拉到本地仓库，并不自动合并到当前工作分支，只有当你确实准备好了，才能手工合并
git pull 命令自动抓取数据下来，然后将远端分支自动合并到本地仓库中当前分支
git remote show origin 查看远程所有分支
git branch  查看本地所有分支
git branch xxx  新建xxx分支
git branch -d xxx  删除本地xxx分支
git branch -a  查看所有分支
git checkout xxx  切换到xxx分支
git checkout --track origin/dev 切换到远程dev分支到本地
git branch -m xxx ooo  把分支xxx改名字为ooo
git checkout -b eminem origin/eminem 拉取远程分支并创建本地分支    


git branch -r -d origin/branch-name不成功，发现只是删除的本地对该远程分支的track，正确的方法应该是这样：
git push origin :branch-name冒号前面的空格不能少，原理是把一个空分支push到server上，相当于删除该分支。

 
git clone gitlab@192.168.20.251:libratone/AndroidApp.git E:\git\Git\Libratone  克隆项目到指定目录

git reset --hard 9cf0daf2df91af1d2982a0b39ea4b1935760ce27   直接回滚到某一个版本
git push -f origin eminem 强制远程分支回滚到某一个版本
 

# 创建轻量标签
$ git tag v0.1.2-light

# 创建附注标签
$ git tag -a v0.1.2 -m “0.1.2版本”

1.git tag   查看当前分支下的标签

2.git  checkout v0.21   此时会指向打v0.21标签时的代码状态，（但现在处于一个空的分支上）


  在本地 master 分支上做了一个commit ( 38361a68138140827b31b72f8bbfd88b3705d77a ) ， 如何把它放到 本地 old_cc 分支上？ 
$ git checkout old_cc
$ git cherry-pick 38361a68138140827b31b72f8bbfd88b3705d77a 
