挂机步骤：
首先下载openkore_cro  : https://github.com/OpenKore/openkore/tree/42c7b6ef0010a67f35acedd3e72d38d8e8871d6f
虚拟机里面的设置：
1，电脑需要安装虚拟机，VMware Workstation 或者 Oracle VM VirtualBox ，其他的应该也可以，个人推荐Oracle VM VirtualBox，简单实用稳定

2，openkore拷贝到虚拟机里面，设置control\poseidon.txt 如下，其中“192.168.3.3”要换成你的虚拟机的ip地址
poseidon.txt设置：
ragnarokserver_ip=192.168.3.3
ragnarokserver_port=6900
queryserver_ip=192.168.3.3
queryserver_port=24390
server_type=cRO_2017-12-13a
CharBlockSize=147
debug=0

3，control\config.txt 设置:其中“192.168.3.3”要换成你的虚拟机的ip地址
poseidonServer 192.168.3.3
poseidonPort 24390

4，运行start-poseidon.exe ，得到下面的提示
>>> Starting Poseidon 2.1 <<<
Loading configuration...
Starting servers...
Building RagnarokServer with serverType cRO_2017-12-13a...
Ragnarok Online Server Ready At : 192.168.3.3:6900
Query Server Ready At : 192.168.3.3:24390
>>> Poseidon 2.1 initialized (Debug : Off) <<<

真实PC上的设置：
1，仙境传说online\data 目录下建立txt文件，改名 poseidon.xml，内容如下“192.168.3.3”要换成你的虚拟机的ip地址：
<?xml version="1.0" encoding="euc-kr" ?>
<clientinfo>
	<desc>Ragnarok Client Information - China Test</desc>
	<servicetype>china</servicetype>
	<servertype>primary</servertype>
	<hideaccountlist></hideaccountlist>
	<connection>
<display>普隆德拉</display>
<desc>None</desc>
<port>6900</port>
<domain>192.168.3.3:6900</domain>
<version>1</version>
<langtype>3</langtype>
<registrationweb>http://ro.zhaouc.com/</registrationweb>
<aid>
	<admin>100006</admin>
	<admin>100007</admin>
	</aid>
	</connection>
</clientinfo>
tinfo>
2，桌面建立一个快捷方式 ，路径要指向你的RO客户端，内容：
仙境传说online路径\Ragexe.exe 1rag1 /account:poseidon.xml

3，运行这个快捷方式，用户名密码随便输，应该可以登录进游戏，但是不能进行任何操作。

最后在虚拟机里面运行 openkore 就可以开始挂机了

注意！！！！
1，GM一般通过密聊检查外挂，所以推荐使用 alertsound 这个Plugin ，收到密聊可以播放声音，
config.txt 里面加上下面的， “2445.wav” 替换成你的声音文件，默认目录就是openkore的目录
alertSound - {
	eventList private chat
	notInTown 0
	inLockOnly 0
	play 2445.wav
}

2，要能用中文在openkore中回答问题。macro加上config里面的快捷命令alias_px 可以解决这个问题

3，挂机不要贪心，GM有可能会直接按照工作室永封，而且会封交易过的号，这个是最无赖的做法，珍惜帐号

窍门 
安装下面的strawberry-perl 
http://strawberryperl.com/download/5.12.3.0/strawberry-perl-5.12.3.0.msi
在perl cmd里面运行
ppm install Win32::Console

这样以后 可以用： openkore\src\poseidon\poseidon.pl 来运行poseidon
可以用命令： openkore\openkore.pl 来运行openkore
这样运行opkore和poseidon不会被nPgameguard 检测出来


