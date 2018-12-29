@[TOC](这里写自定义目录标题)

# git的安装
由于最近一直不懂这个东西 然后要做一个hexo这个类型的项目需要git,刚好来学学顺便养成一个爱写博客的习惯,记录与学习天天得有.

## git和github的关系
git这个软件是免费的,而github这个软件是相当于是一个远程的仓库,而本地的git相当于一个连接远端和本机的一个平台


## 下载git和配置git
下载的链接:[gitLink](https://git-scm.com/downloads).

我是下载windows上的:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228204445771.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)
下载后如果想和远端建立连接的话需要github上配置上你自己所生成的ssh key.
必须要在
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228210027201.png)必须要在.git下的objects目录下执行命令  如果你看不见这个文件 因为它是隐藏的 所以你要在查看中点出显示隐藏文件
然后输入
ssh-keygen -t rsa -C "example@xxx.com"后就会生成了2个文件id_rsa,id_rsa.pub然后将以pub结尾的中的所有复制出来也就是你独有的ssh key 然后接着就是去git自己的用户中配置自己的git key值
![在这里插入图片描述](https://img-blog.csdnimg.cn/2018122821070671.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)然后新建一个新的ssh key
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228210905134.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)添加后 就建立了本地git与远程的github的连接了

## git的使用

1.为了方便控制所以一般配置一个全局的用户名及邮箱
![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228211820902.png)
这里的--global表示的是全局的意思,然后就开始创建 本地独有的git仓库了
说到这里刚好可以看看git和svn的区别 我参考的https://blog.csdn.net/mine_song/article/details/70770467图比较多,然后讲的也很精炼.

![在这里插入图片描述](https://img-blog.csdnimg.cn/20181228212806589.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM5OTEyNTEx,size_16,color_FFFFFF,t_70)
刚好也执行下各自的命令行练习下;
创建一个文件夹 :mkdir 创建文件夹
粗略查询:ls (为了方便记 我一般吧这个s想象成simple 也就是粗略展示)
仔细查询:ll
用户添加文件:git add "文件名" 
添加当前目录下的所有文件:git add . //可以用来
提交版本信息:git commit -m "提交的内容" 
上传:git push

