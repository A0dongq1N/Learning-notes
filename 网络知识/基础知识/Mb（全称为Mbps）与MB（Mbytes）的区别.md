# Mb（全称为Mbps）与MB（Mbytes）的区别

 一般在书写带宽单位的时候，我们会写网络带宽是10M，很多网管误以为最大下载流量可以达到每秒下载10M的文件。其实是10/8 =1.25M。 
原因：带宽的单位和硬盘的单位是不一样的。 容易误解的技术概念：Kb是否等于KB ? 
假设我们申请的100Mb带宽的光纤，可是当下载本地网站的软件时，下载速度只能达到10MB左右的速度，而电信部门却说网络速度非常正常。原因在哪里呢？ 
上面的两个数据中，单位不同，一个是Mb，另外一个是MB。具体的差别就是在这里了。我们在日常的书写中，经常会不注意上面的细节，而这两个单位，真正的含义是不同的。 
Mb（全称为Mbps）这是电信部门衡量网络带宽的单位，意思是兆比特位每秒。 MB（Mbytes）是电脑文件容量的单位兆字节。 
带宽单位详解： bps是bit Per Second的缩写，翻译成中文就是比特位每秒，也就是表示一秒钟传输多少位（bit）的意思。 
   位(bit)与字节(Byte)之间的关系: 
存储单位详解：80G硬盘。G就是硬盘容量的单位，也是存储的单位。存储的最小单位是字节Byte，对于存储单位，有以下几个单位，GB、MB和KB，那么这三者之间的换算关系是：1GB＝1024MB，1MB＝1024KB，1KB＝1024Bytes。 
Kb与KB之间的关系：我们在电脑原理中知道，电脑的最小存储单位是字节Byte，一个字节，是由八位二进制位组成的。由此，我们可以这样认为，一个字节是由8个位组成的，或者说一个字节与八个位所占的空间是相同的。因为，当我们使用100Mb带宽的网络下载时，理论上的速度应该是100除以8等于12.5MB。 
bps：位/每秒，通常对于串行总线设备使用bps为单位，如串口，USB口，以太网总线等。 
Bps：字节/每秒，通常对于并行总线设备使用Bps为单位，如并口，IDE硬盘等。 带宽1M,是1024K个bit，即16个64K bit 
磁盘是1M，是1024K个byte ( 1M = 1024K = 1024*1024 byte =1024*1024 * 8bit ) 另: 100M局域网都是bps计量，当用于软件下在时，下载工具一般又以Bps计算