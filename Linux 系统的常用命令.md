一、	Linux常用命令
Tab 补齐
上下箭头命令历史
Ctrl+c 退出当前命令的执行
Ctrl+L 或者clear清屏
1)	ls(list)  列表显示
–a 显示所有文件,包括隐藏文件(一般为系统文件),a表示all
    –l 详细信息显示, l表示long
	-h  h表示human,人性化显示,将显示文件大小为K,M或者G而不是字节数
   ls –l (ll)
ls –la (ls –a –l)
ls –lh
文件属性常见有三种,普通文件,目录文件(d开头),软链接(l开头)
ls –l /etc/grub.conf, 显示为l开头的软链接
ls –ld /etc 会显示/etc目录的详细信息, ll /etc或者ls –l /etc则会显示/etc目录下面的文件和目录的详细信息,注意这两者的区别
2)	cd(change directory) 修改目录
cd /etc
cd	回到当前用户的宿主目录
cd ..回到上一级目录
3)	mkdir(make directory)	创建目录
-p  递归创建
mkdir  /test1	在根目录下面创建子目录test1
mkdir  backup	在当前目录下面创建子目录backup
mkdir –p /root/dir1/dir2  递归创建目录,dir1可以不存在
4)	pwd(print working directory) 显示当前目录
5)	rmdir(remove empty directory) 删除目录
这个命令只能删除空目录
rmdir /root/dir1/dir2
6)	cp(copy)  拷贝文件或目录
-r  递归拷贝目录
-p  保留文件属性
cp install.log Downloads	 将install.log拷贝到当前目录下面的Downloads子目录中
cp –r Downloads  /tmp	 将当前目录下面的Downloads目录及其子目录递归拷贝到/tmp下面
7)	mv(move) 移动文件/目录,文件/目录改名
mv和cp不同,可以不加-r选项也可以移动目录,移动后也可以改名,可以同时移动多个文件或目录
mv install* anaconda* Downloads	将install开始的文件/目录和anaconda开始的文件/目录移动到Downloads子目录下
8)	rm(remove) 删除文件/目录
-r 递归删除目录
-f 强制执行(不提示)		
rm –rf backup	递归删除目录backup及其下所有文件和目录,而且不会提示
9)	touch 创建空文件
touch “my test file” 创建一个文件名中有空格的空文件
touch test file	创建两个空文件,test和file
10)	cat  显示文件内容 
-n 显示行号
cat /etc/services, 文件太长,可以按ctrl+c退出
11)	more,less	分页显示文件内容
按空格或者f 一页一页往下翻页,按b一页一页往上翻页,q退出
12)	head,tail	显示文件的最前/最后几行
-n 显示多少行
head /etc/services 默认显示前10行
tail –n 20 /etc/services	显示最后20行
tail –f /var/log/messages 动态显示文件末尾内容,常用于看日志变化
13)	useradd 添加用户
useradd hadoop
14)	passwd 为用户设置密码
passwd hadoop
15)	chmod (change the permission mode of a file/directory) 改变文件/目录的权限
chmod 755 testfolder	修改testfolder的权限为755
chmod –R 777 folder1 递归将folder1目录下的所有文件和目录的权限都改成777
16)	chown (change file ownership)  修改文件/目录的所有者
chown hadoop testfolder		将testfolder的所有者改成hadoop用户
17)	man (manual)	查看系统帮助信息
man ls	查看ls命令的帮助
18)	date	查看或修改系统时间
-s 设置日期
date 返回系统时间
date -s '2019-09-30 20:08:08'	设置当前日期为2019年9月30日20点8分8秒
19)	ifconfig(interface configure)
只有root才能修改IP地址,普通用户只能用ifconfig查看
ifconfig eth0 192.168.161.128		临时修改eth0网卡的IP地址,重启失效
20)	shutdown 关机
shutdown –h now 立刻关机  
		shutdown –r now 立刻重启 


