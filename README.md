# chn-iplist

数据来源 [ APNIC Delegated List](http://ftp.apnic.net/apnic/stats/apnic/delegated-apnic-latest)，使用 mosdns 项目 [ip 合并优化脚本](https://github.com/IrineSistiana/mosdns/blob/main/scripts/update_chn_ip_domain.py)将其转化为 txt 文件以在路由器上使用，并以此制作 Shadowrocket、Quantumult、acl、v2rayNG、v2rayN、pac、Qv2ray、SagerNet、Loon、RouterOS、sing-box、v2rayA 规则和 v2ray 配置内嵌规则，包含 chn-ip 列表及少量广告屏蔽规则。每15天自动更新一次。

## Subscribe URL:

| ios                                                                                                                                                                                                                                                                                                                                                                                                                                   | android                                                                                     | 其他                                                                                                                                                                                                                                                                                             |
|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| [Shadowrocket](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Shadowrocket.conf) \| [Shadowrocket-ASN](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Shadowrocket-ASN.conf)                                                                                                                                                                                                                        | [acl (no ban ads)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chn.acl) | chnroute [ipv4与ipv6](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute.txt) \| [纯ipv4](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute-ipv4.txt) \| [纯ipv6](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute-ipv6.txt) |
| [Quantumult(X) (no chn-ip)](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Quantumult(X)_noIP.conf)                                                                                                                                                                                                                                                                                                                  |                                                                                             | [pac](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/chnroute.pac) （默认代理走 socks5 localhost:1080）                                                                                                                                                                              |
| [Loon 配置文件](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Loon/Loon.conf)  订阅特殊规则：[direct](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Loon/ruleset/direct-special.txt) \| [proxy](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Loon/ruleset/proxy-special.txt) \| [reject](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Loon/ruleset/reject-special.txt) |                                                                                             | [v2rayN ](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/v2rayN_subrules_whitelist)                                                                                                                                                                                 |

## 需手动更新：

#### v2rayN(G)

分别将 [proxy](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/proxy.txt)、[direct-noip](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/direct-noip.txt)、[block](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayN(G)/block.txt) 规则复制粘贴至应用内。

#### Qv2ray

下载[no-chnip方案](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Qv2ray-noip.json)后导入。

#### SagerNet

分别将 [domain 屏蔽规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/block-domain.txt)、[domain 代理规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/proxy-domain.txt)、[ip 代理规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/proxy-ip.txt)、[domain 绕过规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/direct-domain.txt)、[ip 绕过规则](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/AnXray%26SagerNet/direct-ip.txt)复制粘贴至应用内路由对应分类。

#### v2ray 配置内嵌规则

将[规则文本](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2ray-config_rule.json)加入配置文件 routing 对应区域。

#### v2rayA 分流规则

将[规则文本](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/v2rayA.txt)替换入原有规则。

## PS.

1. Shadowrocket 等有 ipv6 开关的，若服务器不支持 ipv6 且连接失败，请设为仅 ipv4。额外提供前缀为 [IP-CIDR](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/ipv6.list) 和 [IP-CIDR6](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/Loon/ruleset/ipv6.list) 两种远程 ipv6 规则。
2. Loon 配置文件为简洁配置，适用于使用自建节点。订阅规则以特殊规则为主，需搭配其他更完善的订阅规则。
3. SagerNet 部分规则由 [Loyalsoldier](https://github.com/Loyalsoldier/v2ray-rules-dat/releases) 加强版规则特殊支持，需将路由资源更新源设为 Loyalsoldier/v2ray-rules-dat。
4. 对于已支持在线更新 geoip 数据的软件，本规则不再内置 cn-ip 列表。
5. 为解决 Shadowrocket 配置在线更新后覆盖掉自定义规则部分，提供一个高度精简的[自定义配置模块](https://raw.githubusercontent.com/PaPerseller/chn-iplist/master/DIY.module)。新建模块后复制本模块内容并自行增删修改后保存，不可通过 URL 添加以防模块被更新重置。此模块仅当有自定义规则需求时添加。
6. ROS 下载 cn.rsc 推荐 [CDN 加速地址](https://cdn.jsdelivr.net/gh/PaPerseller/chn-iplist/cn.rsc)以提高下载成功率。

## 致谢

- [CIDR2PAC](https://github.com/wspl/CIDR2PAC) - A es6 script for coverting CIDRs list to PAC proxy script.
- [ACL4SSR/Clash](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash) - Clash规则碎片
- [domain-list-community](https://github.com/v2fly/domain-list-community) - Community managed domain list
- [mosdns](https://github.com/IrineSistiana/mosdns) - 插件化的 DNS 转发/分流器。
- [Loyalsoldier/v2ray-rules-dat](https://github.com/Loyalsoldier/v2ray-rules-dat) - V2Ray 路由规则文件加强版
- [Shadowrocket-ADBlock-Rules-Forever](https://github.com/Johnshall/Shadowrocket-ADBlock-Rules-Forever)
- 其他部分规则来源的作者
- ChatGPT  辅助实现的自动化更新
