---
title: linux命令-英文全称
date: 2021-10-25 23:13:14
tags: linux常用命令-英文全称
---

alias：给命令起别名

awk = "Aho Weiberger and Kernighan" ，三个作者的姓的第一个字母

bash：GNU Bourne-Again Shell，大多Linux的默认shell

bc = Basic Calculator，基础计算器，scale设定小数位，quit退出

bg = BackGround，后台运行任务

bye = bye，用于在FTP时退出FTP执行

cal = calendar，日历，后跟月份数、年份数可显示指定月日历

cat = catenate，连续，输出文件内容，-n显示行号，-b不显示空行，有意思的是tac则从后向前输出

cd = Change Directory，切换目录

chgrp = Change group，改变文件归属用户组

clear = clear，清屏

chmod = Change mode，改变读写权限，-R递归更改，a默认所有用户u本用户g本群组o其他用户，+-rwx增减读写执行权限，rwx421

chown = Change owner，改变所有者

cp = copy，复制

crontab = Chronos，希腊文时间，定时执行工具，* * * * *分别为分时日月星期，*代表所有，"-"为范围","为多值"/"为频率，-u指定用户，-l查看任务，-r删除任务，-e编辑任务。

cut = cut，从文件中的每行文本中剪出指定字符，功能类似grep，-b以字节为单位，-c以字符为单位，-d自定义分隔符默认制表符

date = date，日期时间，date "+option"，-d显示指定时间，-r显示文件最后修改时间，-s修改时间，%x日期，%X时间，%F日期，%D月日年，%Y4位年份，%y2位年份，%m月份，%d日，%H24制时，%I12制时，%M分，%S秒

declare = declare，用于声明shell变量，-a数组，-i指定整数型

df = Disk Free，剩余磁盘空间，-h以适阅读单位显示，后跟文件则显示其所在挂载点磁盘剩余空间

dirs = directories，从目录栈中读取，功能类似于一个数组，先显示本目录再显示目录栈，-c删除目录栈中所有记录，-p每行显示一个（默认连续显示），-v每行显示一个并加编号，+N显示第N个目录（数字从0开始），-N显示倒数第N个目录

du = Disk Usage，磁盘使用情况，统计文件大小，-h以适阅读单位显示，-s不迭代仅合计统计，--max-depth n指定统计深度

egrep = Extended GREP，可使用扩展正则的grep

exec =execute，执行 ，内部命令

find = find，查找，find PATH -OPTION [-print] [-exec cmd] {} \;，PATH为查找数据若为当前目录下则为“.”，-name文件名，-mtime +/- N N天前或内更改的文件，-ctime +/-N N天前或内创建的文件，-type文件类型d为目录f为文件，-size 大于指定字节的文件，

fg = ForeGround，前台运行任务

fmt = format，简单的文本格式化

ftp = File Transfer Protocol，文件传输，后跟IP地址，get从远程FTP机下载到本机，mget批量下载，put将本机文件上传到远程FTP机，mput批量上传

free = free，内存使用情况，-s间隔N秒查询一次，-m -k -b以M、KB、Byte为单位显示

gawk = GNU AWK

grep = global regular expression print，全局正则表达式打印，强大的文本搜索工具，-c只输出计数，-i忽略大小写，-n输出行号，-v取反，-h多文件时不显文件名，-r递归搜索

head = head，查看前n行

iostat = in out status，IO及CPU状态

iostat = in out status，IO及CPU状态

less = less，分页展示文件内容

logname = loginname，显示当前登录用户名

ln = link，建立链接，-s建立软链接（默认硬链接）

locate = locate，查找文件地址，并不查硬盘，而是在/var/lib/slocate/slocate.db中查看，速度快省资源

ls = list，列出文件，-l详细信息，-h合适单位显示，-S大小排序，-t时间排序

lsof = List Open Files，列出当前系统打开的文件，ROOT权限，-c某进程打开的文件，-p某进程打开的文件，-u某用户打开的文件，跟目录为目录下打开的文件，跟文件为文件相关打开信息，-i某端口或IP打开的文件

man = Manual意思是手册，可以用这个命令查询其他命令的用法。

mkdir = Makedirectory，创建目录，-p指定路径，-m指定权限

mv = Move，移动文件，同目录下则为重命名，-i询问试覆盖，-f同名强制覆盖，-b备份旧文件（文件名后加~），-u若本文件较新则覆盖旧文件

more = more，分页显示

nl = Number of Lines，计算文件行号，类似cat，-b a 计算空行（默认不计算），-n rz以6位数字显示行号前补0，-w指定占位数（默认6）

passwd = PassWord

pg = pager，分页显示文件内容

ping = Packet InterNet Grouper，测试网络，-c指定次数，-i指定间隔秒数

printf = Print Format

ps = Processes Status，进程状态 ，命令执行时刻进程信息，-a同终端进程，-A所有进程，-u指定用户，-e同-A，-f展示所有信息，aux查看进程详细信息类似-ef，-C可跟搜索词，--sort=-pcpu,+pmem按cpu降序按mem内存升序排序

pushd = push Directory，当目录放入目录栈，+/-N将正数/倒数第N个目录移到栈顶并切换到该目录，-n在切目录栈时不切目录

popd = pop Directory，从目录栈弹出目录，+/-N将正数/倒数第N个目录从目录栈中移除

pwd = print working Directory，打印工作目录

rcp = remote copy，远程拷贝，-r递归，-p保留修改时间和权限，将远程文件拷贝到本机，限制条件较多

rm = ReMove，删除文件，-r递归，-f不询问强制删除

rmdir = Remove directory，删除目录

rlogin = remote login，-l指定登录用户名，rlogin IP/主机名

rsh = remote shell，远程执行shell，-l指定用户

rmp = RedHat Package Manager，RedHat软件包管理工具，类似Windows里面的“添加/删除程序”，-a查询所有，-e卸载，-h显示进度，-i显示相关信息，-l列出软件所有文件名，-q查询，-p软件包内文件，-v显示执行过程；常用参数：-ivh安装并显示进度，-qpl查看软件包内文件，-qa查询一个软件是否安装过，--relocate指定安装目录，--rebuild编译+打包，--recompile编译+打包+安装

reboot=Restart your computer，重启

scp = secure copy，用于Linux间复制，基于ssh远程复制，-p保留修改时间权限，-r递归，-P指定端口，-v显示进度，

sed = Stream Editor，流编辑器，本身即先查，在CMD中匹配字符两侧要有//，sed -OPTION 'CMD' file，选项：-n安静模式，-i直接修改不屏幕输出，-r支持扩展正则，-e多命令，-f文件指定动作；命令：a增，d删除，i插，c改，s正则查，p屏幕输出，g获取内存缓冲区内容并替代当前模板块中文字，G获取内容追加，h内容拷贝到内存，H内容追加到内存

set = set，主要作用是显示系统中已经存在的shell变量，以及设置shell变量的新变量值，不能够定义新的shell变量，定义新的变量使用declare命令。

shutdown，关机，-t设定延迟时间，-k通知所有用户，-r重启，-h关机后停机，-c取消关机，-f强制关机，time设定关机时间

sleep = sleep，动作延迟

sort = sort，排序，-b忽略行首空格，-r反向，-n以数值，-o排序结果输出文件，-t指定列分隔符，-k指定排序列，-f忽略大小定

split = split，将大文件分割成小文件，-N每N行分割成一个文件，-bN每N字节分割成一个文件，-C按字节分割保证完整性

ssh = Secure Shell，远程登录Linux，-l指定用户，-p指定端口

sshpass，一款ssh免密码输入软件

su = switch user，切换用户，root切任何用户不需要密码，但其他用户之间切换需要密码，- user表示切换到用户user并将用户环境一并切换，-c执行命令再退回原用户

sudo = super user do，受限制的su

svn = SubVersioN

sync = 强制将内存写入硬盘

tar = tape archive，打包归档文件，-c创建create，-x提取extract，-t查看list，-f指定归档文件，-m解压时不变更文件更改时间，-p解压时原权限不变，-v显示执行详情，-r向归档文件中追加，-u更新归档文件中文件

tail = tail，查看尾部n行

touch = touch，创建，修改文件或者目录的时间属性，若文件不存在，系统会建立一个新的文件，更改文件权限再结合chmod

top = top，实时显示系统中各个进程的资源占用状况，该命令可以按CPU使用、内存使用和执行时间对任务进行排序

umount = Unmount 卸载，可以通过设备名卸载或挂载点卸载

unset = unset，用于删除变量或函数

useradd、userdel、usermod，新增用户、删除用户、修改用户

w = who，显示目前登入系统的用户信息

xargs = eXtended ARGuments，给命令传递参数的一个过滤器，也是组合多个命令的一个工具，它把一个数据流分割为一些足够小的块，以方便过滤器和命令进行处理

wc = Word Count，计算文件的Byte数、字数、或是列数，-c只显示字节数，-l只显示行数，-w只统计单词数

who = who，显示当前系统所有使用者等信息

whoami = whoami，命令用于显示自身用户名称。

which = which，命令用于查找文件

whereis = where is，查看文件





ls：list(列出目录内容)
 cd：Change Directory（改变目录）
 su:switch user 切换用户
 rpm:redhat package manager 红帽子打包管理器
 pwd:print work directory 打印当前目录 显示出当前工作目录的绝对路径
 ps: process status(进程状态，类似于windows的任务管理器) 常用参数：－auxf
 ps -auxf 显示进程状态  [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 df: disk free其功能是显示磁盘可用空间数目信息及空间结点信息。换句话说，就是报告在任何安装的设备或目录中，还剩多少自由的空间。
 rpm： 即RedHat Package Management，是RedHat的发明之一

rmdir：Remove Directory（删除目录）
 rm：Remove（删除目录或文件）
 cat: concatenate连锁 cat file1file2>>file3把文件1和文件2的内容联合起来放到file3中
 insmod: install module,载入模块
 ln -s : link -soft 创建一个软链接，相当于创建一个快捷方式
 mkdir：Make Directory(创建目录
 touch
 man: Manual
 pwd：Print working directory
 su：Swith user
 cd：Change directory
 ls：List files
 ps：Process Status
 mkdir：Make directory
 rmdir：Remove directory
 mkfs: Make file system
 fsck：File system check
 cat: Concatenate

uname: Unix name
 df: Disk free
 du: Disk usage
 lsmod: List modules
 mv: Move file
 rm: Remove file
 cp: Copy file
 ln: Link files
 fg: Foreground
 bg: Background
 chown: Change owner
 chgrp: Change group
 chmod: Change mode
 umount: Unmount

dd: 本来应根据其功能描述“Convert an copy”命名为“cc”，但“cc”已经被用以代表“CComplier”，所以命名为“dd”  [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 tar：Tape archive
 ldd：List dynamic dependencies
 insmod：Install module
 rmmod：Remove module
 lsmod：List module
 文件结尾的"rc"（如.bashrc、.xinitrc等）：Resource configuration
 Knnxxx /Snnxxx（位于rcx.d目录下）：K（Kill）；S(Service)；nn（执行顺序号）；xxx（服务标识）
 .a（扩展名a）：Archive，static library
 .so（扩展名so）：Shared object，dynamically linked library
 .o（扩展名o）：Object file，complied result of C/C++ source file
 RPM：Red hat package manager
 dpkg：Debian package manager
 apt：Advanced package tool（Debian或基于Debian的发行版中提供）
 部分[Linux](https://link.jianshu.com?t=http://www.2cto.com/os/linux/)命令缩写  [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)

bin = BINaries
 /dev = DEVices
 /etc = ETCetera
 /lib = LIBrary
 /proc = PROCesses
 /sbin = Superuser BINaries
 /tmp = TeMPorary
 /usr = Unix Shared Resources
 /var = VARiable ?
 FIFO = First In, First Out
 GRUB = GRand Unified Bootloader
 IFS = Internal Field Seperators
 LILO = LInux LOader

MySQL = My是最初作者女儿的名字，SQL = Structured QueryLanguage
 [PHP](https://link.jianshu.com?t=http://www.2cto.com/kf/web/php/) = Personal Home Page Tools = PHP HypertextPreprocessor
 PS = Prompt String  [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 Perl = "Pratical Extraction and Report Language" ="Pathologically Eclectic Rubbish Lister"
 [Python](https://link.jianshu.com?t=http://www.2cto.com/kf/web/Python/) 得名于电视剧Monty Python's Flying Circus
 Tcl = Tool Command Language
 Tk = ToolKit
 VT = Video Terminal
 YaST = Yet Another Setup Tool
 apache = "a patchy" server
 apt = Advanced Packaging Tool
 ar = archiver
 as = assembler

awk = "Aho Weiberger and Kernighan"三个作者的姓的第一个字母
 bash = Bourne Again SHell
 bc = Basic (Better) Calculator
 bg = BackGround
 biff = 作者HeidiStettner在U.C.Berkely养的一条狗,喜欢对邮递员汪汪叫。
 cal = CALendar
 cat = CATenate
 cd = Change Directory
 chgrp = CHange GRouP
 chmod = CHange MODe
 chown = CHange OWNer
 chsh = CHange SHell
 cmp = compare
 cobra = Common Object Request BrokerArchitecture
 comm = common
 cp = CoPy
 cpio = CoPy In and Out
 cpp = C Pre Processor
 [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 cron = Chronos 希腊文时间
 cups = Common Unix Printing System
 cvs = Current Version System
 daemon = Disk And Execution MONitor
 dc = Desk Calculator
 dd = Disk Dump
 df = Disk Free
 diff = DIFFerence
 dmesg = diagnostic message
 du = Disk Usage
 ed = editor
 egrep = Extended GREP
 elf = Extensible Linking Format
 elm = ELectronic Mail
 emacs = Editor MACroS
 eval = EVALuate
 ex = EXtended
 exec = EXECute
 fd = file descriptors
 fg = ForeGround
 fgrep = Fixed GREP
 fmt = format
 fsck = File System ChecK
 fstab = FileSystem TABle
 fvwm = F*** Virtual Window Manager
 gawk = GNU AWK
 [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 gpg = GNU Privacy Guard
 groff = GNU troff
 hal = Hardware Abstraction Layer
 joe = Joe's Own Editor
 ksh = Korn SHell
 lame = Lame Ain't an MP3 Encoder
 lex = LEXical analyser
 lisp = LISt Processing = Lots of IrritatingSuperfluous Parentheses
 ln = LiNk
 lpr = Line PRint
 ls = list
 lsof = LiSt Open Files
 m4 = Macro processor Version 4
 man = MANual pages
 mawk = Mike Brennan's AWK
 mc = Midnight Commander
 mkfs = MaKe FileSystem
 mknod = MaKe NODe
 motd = Message of The Day
 mozilla = MOsaic GodZILLa
 mtab = Mount TABle
 mv = MoVe

nano = Nano's ANOther editor
 nawk = New AWK
 nl = Number of Lines
 nm = names
 nohup = No HangUP
 nroff = New ROFF
 od = Octal Dump
 passwd = PASSWorD
 pg = pager
 pico = PIne's message COmposition editor
 pine = "Program for Internet News &Email" = "Pine is not Elm"
 ping = 拟声 又 = Packet InterNet Grouper
 pirntcap = PRINTer CAPability
 popd = POP Directory
 pr = pre

printf = PRINT Formatted
 ps = Processes Status
 pty = pseudo tty
 pushd = PUSH Directory
 pwd = Print Working Directory
 rc = runcom = run command, rc还是plan9的shell
 rev = REVerse
 rm = ReMove
 rn = Read News
 roff = RunOFF
 rpm = RPM Package Manager = RedHat PackageManager
 rsh, rlogin, rvim中的r = Remote
 rxvt = ouR XVT
 seamoneky = 我
 sed = Stream EDitor
 seq = SEQuence
 shar = SHell ARchive
 slrn = S-Lang rn
 ssh = Secure SHell
 [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 ssl = Secure Sockets Layer
 stty = Set TTY
 su = Substitute User
 svn = SubVersioN
 tar = Tape ARchive
 tcsh = TENEX C shell
 tee = T (T形水管接口)
 telnet = TEminaL over Network
 termcap = terminal capability
 terminfo = terminal information
 tex = τέχνη的缩写，希腊文art
 tr = traslate
 troff = Typesetter new ROFF
 tsort = Topological SORT
 tty = TeleTypewriter
 twm = Tom's Window Manager
 tz = TimeZone

udev = Userspace DEV
 ulimit = User's LIMIT
 umask = User's MASK
 uniq = UNIQue
 vi = VIsual = Very Inconvenient
 vim = Vi IMproved
 wall = write all
 wc = Word Count  [www.2cto.com](https://link.jianshu.com?t=http://www.2cto.com)
 wine = WINE Is Not an Emulator
 xargs = eXtended ARGuments
 xdm = X Display Manager
 xlfd = X Logical Font Description
 xmms = X Multimedia System
 xrdb = X Resources DataBase
 xwd = X Window Dump
 yacc = yet another compiler compiler
 Fish = the Friendly Interactive SHell
 su = Switch User
 MIME = Multipurpose Internet Mail Extensions
 ECMA = European Computer ManufacturersAssociation
