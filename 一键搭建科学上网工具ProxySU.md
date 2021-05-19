**2020年12月6日更新。**

***


**介绍**:

ProxySU是一款windows科学上网搭建软件，支持一键搭建V2ray，Trojan，NaiveProxy, Trojan-Go, ShadowsocksR(SSR),Shadowsocks-libev及相关插件一键安装工具。

**使用提醒**：

ProxySU的安装流程，是假设在全新系统下，没有装过以上代理软件，如果已经安装过，最好将系统重装一下，会减少很多的麻烦。ProxySU在开发过程中，一般都是在[vultr](https://www.vultr.com/?ref=7048874)的vps中测试，测试系统版本为：Centos7/8 Debian9/10 Ubuntu18.04/20.04(推荐Debian9)。[ProxySU官网](https://github.com/proxysu/windows/tree/v2.2.2)。

**ProxySU-v2.2.2功能如下:**

##### V2ray可一键安装的模式有：
* tcp 
* tcp+http伪装  
* tcp+TLS 
* tcp+TLS （自签证书）
* Vless+tcp+TLS+Web (新热门协议)
* WebSocket
* WebSocket+TLS 
* WebSocket+TLS+Web 
* WebSocket+TLS（自签证书） 
* http2  
* http2+TLS+Web
* http2（自签证书）
* mKCP及各种伪装 
* QUIC及各种伪装。  
注：mKCP和QUIC模式使用udp协议，可以有效减少网络延时，有加速的作用，但在网络管控严厉时期，会导致IP被封，遇到的一次，就是刚安装好，使用了3个小时后，IP被封（现已确认是mKCP的流量被识别导致，项目组正在维护中。2020.6.10维护完毕，升级到版本4.24.2及以上，启用mKCP密钥可增强抗识别）。以上模式最推荐的是WebSocket+TLS+Web 和http2+TLS+Web 需要有一个域名。如果能加上CDN则稳定性更好。加上CDN后，是加速还是减速，与线路有关。

##### Trojan 可一键安装：  
* Trojan + TLS + Web

##### Trojan-Go 可一键安装：  
* Trojan-Go + TLS + Web  
* Trojan-Go + WebSocket + TLS + Web

##### NaiveProxy一键安装：  
* NaiveProxy + TLS +Web  

##### ShadowsocksR(SSR)一键安装：  
* SSR+TLS+Caddy  

##### Shadowsocks-libev及相关插件一键安装：  
* SS 经典模式  
* SS+WebSocket+TLS+Caddy(Web前置) (推荐)  
* SS+WebSocket  
* SS+QUIC  
* SS+kcptun  
* SS+obfs+http+Web  
* SS+obfs+TLS+Web  

##### 支持的VPS系统为：  
* CentOS 7/8   
* Debian 8/9/10 (推荐Debian9)  
* Ubuntu 16.04及以上

示意图:

![](./static/ps1.jpg)

![](./static/ps11.jpg)

**搭建流程**:

第一步:购买服务器获得ip和密码

第二步:ProxySU下载及搭建


***

**第一步:购买服务器获得ip和密码**

VPS服务器需要选择国外的，首选国际知名的vultr，速度不错、稳定且性价比高，按小时计费，能够随时开通和删除服务器，新服务器即是新ip。

vultr注册地址：[https://www.vultr.com](https://www.vultr.com)  （vps最低2.5美元/月，vultr全球17个服务器位置可选，包括日本、韩国、新加坡、洛杉矶、德国、荷兰等。支持支付宝和paypal付款。） 

<a href="https://www.vultr.com"><img src="https://www.vultr.com/media/banners/banner_728x90.png" width="728" height="90"></a>

虽然是英文界面，但是现在的浏览器都有网页翻译功能，鼠标点击右键，选择网页翻译即可翻译成中文。

注册并邮件激活账号，充值后即可购买服务器。充值方式是支付宝或paypal，使用paypal有银行卡（包括信用卡）即可。paypal注册地址：[https://www.paypal.com](https://www.paypal.com) （paypal是国际知名的第三方支付服务商，注册一下账号，绑定银行卡即可购买国外商品）

***

2.5美元/月的服务器配置信息：单核   512M内存  10G SSD硬盘   带宽1G    500G流量/月   (**不推荐，仅提供ipv6 ip，不推荐**)

3.5美元/月的服务器配置信息：单核   512M内存  10G SSD硬盘   带宽1G    500G流量/月   (**推荐**)

5美元/月的服务器配置信息：  单核   1G内存    25G SSD硬盘   带宽1G    1000G流量/月  (**推荐**)
 
10美元/月的服务器配置信息： 单核   2G内存    55G SSD硬盘   带宽1G    2000G流量/月  

20美元/月的服务器配置信息： 2cpu   4G内存   80G SSD硬盘    带宽1G    3000G流量/月  

40美元/月的服务器配置信息： 4cpu   8G内存   160G SSD硬盘   带宽1G    4000G流量/月  

**[vultr](https://www.vultr.com)17个服务器位置官方测试地址：**
<table id="tablepress-1">
<thead>
<tr>
<th>服务器位置</th>
<th>官方测试ip</th>
<th>下载测试文件100M</th>
<th>下载测试文件1GB</th>
</tr>
</thead>
<tbody>
<tr>
<td>韩国汉城</td>
<td>141.164.34.61</td>
<td><a rel="nofollow" href="https://sel-kor-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://sel-kor-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>新加坡</td>
<td>45.32.100.168</td>
<td><a rel="nofollow" href="https://sgp-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://sgp-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>日本东京</td>
<td>108.61.201.151</td>
<td><a rel="nofollow" href="https://hnd-jp-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://hnd-jp-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国硅谷</td>
<td>104.156.230.107</td>
<td><a rel="nofollow" href="https://sjo-ca-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://sjo-ca-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国洛杉矶</td>
<td>108.61.219.200</td>
<td><a rel="nofollow" href="https://lax-ca-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://lax-ca-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>德国法兰克福</td>
<td>108.61.210.117</td>
<td><a rel="nofollow" href="https://fra-de-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://fra-de-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国纽约</td>
<td>108.61.149.182</td>
<td><a rel="nofollow" href="https://nj-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://nj-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国芝加哥</td>
<td>107.191.51.12</td>
<td><a rel="nofollow" href="https://il-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://il-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国亚特兰大</td>
<td>108.61.193.166</td>
<td><a rel="nofollow" href="https://ga-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://ga-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国西雅图</td>
<td>108.61.194.105</td>
<td><a rel="nofollow" href="https://wa-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://wa-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国迈阿密</td>
<td>104.156.244.232</td>
<td><a rel="nofollow" href="https://fl-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://fl-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>美国达拉斯</td>
<td>108.61.224.175</td>
<td><a rel="nofollow" href="https://tx-us-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://tx-us-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>加拿大多伦多</td>
<td>149.248.50.81</td>
<td><a rel="nofollow" href="https://tor-ca-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://tor-ca-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>澳大利亚悉尼</td>
<td>108.61.212.117</td>
<td><a rel="nofollow" href="https://syd-au-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://syd-au-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>荷兰阿姆斯特丹</td>
<td>108.61.198.102</td>
<td><a rel="nofollow" href="https://ams-nl-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://ams-nl-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>法国巴黎</td>
<td>108.61.209.127</td>
<td><a rel="nofollow" href="https://par-fr-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://par-fr-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
<tr>
<td>英国伦敦</td>
<td>108.61.196.101</td>
<td><a rel="nofollow" href="https://lon-gb-ping.vultr.com/vultr.com.100MB.bin">100MB</a></td>
<td><a rel="nofollow" href="https://lon-gb-ping.vultr.com/vultr.com.1000MB.bin">1GB</a></td>
</tr>
</tbody>
</table>

***

**注意：2.5美元套餐只提供ipv6 ip，一般的电脑用不了，所以建议选择3.5美元及以上的套餐。**

vultr实际上是折算成小时来计费的，比如服务器是5美元1个月，那么每小时收费为5/30/24=0.0069美元 会自动从账号中扣费，只要保证账号有钱即可。如果你部署的服务器实测后速度不理想，你可以把它删掉（destroy），重新换个地区的服务器来部署，方便且实用。因为新的服务器就是新的ip，所以当ip被墙时这个方法很有用。当ip被墙时，为了保证新开的服务器ip和原先的ip不一样，先开新服务器，开好后再删除旧服务器即可。在账号的Billing选项里可以看到账户余额。

**账号充值如图**：

![](./static/pp100.png)

![](./static/pp101.png)


**开通服务器步骤如图**：

![](./static/vultr1.png)

![](./static/vultr2.png)

![](./static/vultr3.png)

**vps服务器推荐用Debain9，不推荐用CentOS7，CentOS7用ProxySU无法自动开启bbr加速。**

![](./static/vultr4.png)

![](./static/vultr5.png)

![](./static/vultr6.png)


**开通服务器时，当出现了ip，不要立马去ping或者用ProxySU去连接，再等5分钟之后，有个缓冲时间。完成购买后，找到系统的密码记下来，部署服务器时需要用到。vps系统密码获取方法如下图：**

![](./static/pac教程05.png)

![](./static/pac教程06.png)

**删掉服务器步骤如下图**：

删除服务器时，先开新的服务器后再删除旧服务器，这样可以保证新服务器的ip与旧ip不同。

![](./static/de4.png)

![](./static/de2.png)

![](./static/de5.png)

**第二步:ProxySU下载及搭建**

**ProxySU**:[github官方下载](https://github.com/proxysu/windows/releases) **下载那个zip文件,下载后解压.**

当前版本为ProxySU-v2.5.4,文件很小,大小为778kb.如果github国内下载慢,可以用下面的网盘来下载. 

[国外云盘下载1](https://tr61.free4444.xyz/ProxySU-v2.5.4.zip)  [国外云盘下载2](https://tr51.free4444.xyz/ProxySU-v2.5.4.zip) 

## Windows系统需要安装net4.0及以上

[Microsoft.NET Framework 4.0](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net40-offline-installer) or higher

打开ProxySU,填上第一步购买的vps服务器ip和密码后,选上想搭建的科学上网工具。步骤如下：

![](./static/softimag/ps1.jpg)

**填上ip和密码，端口22和root默认。**

![](./static/softimag/ps10.jpg)

**以搭建v2ray为例，选中v2ray模板库。**

![](./static/softimag/ps3.jpg)

**在v2ray模板库中，选中想要搭建的v2ray协议，有的协议不需要域名，可以直接搭建，有的需要域名，所以需要提前购买域名并绑定服务器ip。第一次购买域名，可以参考这个[域名购买教程](https://github.com/Alvin9999/new-pac/wiki/%E5%9F%9F%E5%90%8D%E8%B4%AD%E4%B9%B0%E6%95%99%E7%A8%8B) 。**

![](./static/softimag/ps4.jpg)

**目前比较热门的v2ray协议:WebSocket+Tls+Web （需要域名）选中后，填写域名。**

![](./static/softimag/ps5.jpg)

**如果没有域名，可以搭建其它的协议，比如TCP、WebSocket（不带tls）、KCP。**

![](./static/softimag/ps9.jpg)

**点击v2ray一键安装，软件会自动搭建。**

![](./static/softimag/ps6.jpg)

**系统工具：点击系统工具可以校对时间和部署bbr加速。v2ray需要校对时间。目前搭建v2ray的过程中，软件会自动校对时间和开启bbr加速，如果一切顺利不用手动再去点击系统工具。**

![](./static/softimag/ps11.jpg)

**部署完后，会自动弹出帐号配置信息，并且在文件夹中也会自动生成相关配置文件及客户端下载地址。**

![](./static/softimag/ps7.jpg)

![](./static/softimag/ps8.jpg)

**有个vmess地址，把它复制下来，然后右键“v2rayN”图标，选择“从剪切板批量导入url”，如下图**

![](./static/softimag/111.jpg)

**如果忘记了vmes地址，在文件夹中有url的txt文档。**

***

**除了这个工具，还可以使用SSH工具连接vps后使用一键脚本来搭建。参考以下教程**：

[自建ss/ssr服务器教程](./自建ss服务器教程.md)

[自建v2ray服务器教程](./自建v2ray服务器教程.md)

[自建brook服务器教程](./自建brook服务器教程.md)
 
[自建trojan服务器教程](./自建trojan服务器教程.md)
 
[自建WireGuard VPN服务器教程](./自建WireGuard-VPN服务器教程.md)

***

有问题可以发邮件至海外邮箱kebi2014@gmail.com