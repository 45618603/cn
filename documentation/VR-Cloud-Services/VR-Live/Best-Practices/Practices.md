# VR直播最佳实践

## 1.VR直播信号采集

VR直播需要用到专业的VR采集设备及相关软件，如Detu、Insta360等，您可根据需求选择对应的设备。   
如果您已经有专业的VR采集设备，按照设备使用说明即可进行VR直播信号的采集。

## 2.VR直播图像拼接

由于VR直播信号是通过多个镜头采集的，所以采集后的直播信号需要进行图像拼接后方可进行推流。一般情况下VR设备厂商都会提供配套的拼接软件，您只需要下载并安装厂商提供的拼接软件即可，安装完成后按照软件使用说明对采集设备多个镜头输出的直播信号进行图像拼接。
##
## 3.VR直播信号推流

**3.1 开通京东云VR直播服务**

在推流之前，你需要开通京东云直播服务，并在控制台创建推流域名及绑定CNAME等操作，具体详见“[入门指南](https://github.com/jdcloudcom/cn/blob/edit/documentation/VR-Cloud-Services/VR-Live/Getting-Started/Service-Provisioning.md)”。

**3.2 VR直播推流**

A.使用VR设备厂商提供的推理工具推流  
很多VR采集设备厂商提供直播推流工具，在推流之前您需要下载并安装厂商提供的推流工具，按照操作说明进行推流即可，在此过程中您需要将3.1中配置好的推流域名作为输出的推流地址。

B.使用RTMP服务器+常用推流工具推流  
将VR直播现场的VR采集设备、RTMP服务器等所有硬件链接到一个局域网内，并确保能够访问外部网络，且满足实际需求的上行带宽；然后开启RTMP服务器，将VR采集设备拼接好的直播信号推流至RTMP服务器；最后使用常用的推流工具（如OBS等）设置在京东云配置好的推流地址进行推流。
 

