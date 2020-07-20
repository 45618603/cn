# 常见问题

**1、Q: 基础防护应用场景是什么？**

A: 京东云DDoS基础防护应用于攻击流量最高不超过2G的DDoS攻击防护场景。一旦攻击流量超过该机房的基础防护能力，黑洞将被触发，触发黑洞后会对被黑洞的公网IP限制一定时长。

**2、Q: 怎么启动基础防护？**

A: 基础防护无需启动，您只要购买了京东云的公网IP，默认会自动对每个公网IP开启DDos防御，提供2G的防御带宽。

**3、Q: 如何关闭基础防护？**

A: DDos基础防护为自动开启，无法进行关闭。DDos基础防护对您的公网IP进行DDos防御，并不会对正常的业务访问造成任何影响。

**4、Q: 对防御的公网IP有什么要求？**

A: 基础防护只能防御已经备案的域名，如域名未备案，将立刻停止防御，并发送告警通知。

**5、Q: 触发黑洞状态的公网IP，在黑洞中会停留多长时间？**

A：默认的黑洞策略是封禁2小时，服务器解封的时间，与黑洞触发的次数和攻击峰值均有关系，如果该服务器公网IP持续遭受攻击，封禁的时间会不断加长，实际封禁的时间2小时到24小时不等。

如果攻击流量过大，触发了运营商的封禁，解封时长将由运营商的策略决定，时长不确定。
  
**6、Q: 攻击流量超过2G，会如何处理？**

A: 在攻击超过2G的情况下会触发黑洞，屏蔽一段时间外部对该IP的访问。

建议您购买京东云的[DDoS防护包](https://www.jdcloud.com/cn/products/anti-ddos-protection-package)服务或[IP高防](https://www.jdcloud.com/products/ipanti)服务，以获得更大的防御能力。

**7、Q: 基础防护支持哪些攻击类型**

A：包括并不限于SYN Flood、ACK Flood、TCP Flood、UDP Flood、DNS反射攻击、NTP反射攻击、SSDP反射攻击等常见攻击。

**8、Q: 基础防护2G的防护能力不能满足需求怎么办？**

A：建议您购买DDoS防护包服务，提升防护能力。

目前DDoS防护包仅支持华北-北京和华东-上海最大50G的防护，公测期间暂不支持购买。如更大的防护能力及网站类型的攻击防护，建议购买[IP高防](https://www.jdcloud.com/products/ipanti)。

如果上述不能解决您的问题，请咨询产品售后：[售后咨询](https://ticket.jdcloud.com/myorder/form?cateId=4&questionId=23)

# 相关文档

- [什么是基础防护？](../Introduction/Product-Overview.md)
- [基础防护架构](../Introduction/Basic-Infrastructure.md)
