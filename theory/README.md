# HTML中怎么设置字符编码

在head标签中使用meta标签content属性使用charset=utf-8就可以设置为utf-8编码

```HTML
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
```

# tcp/ip四层协议有哪些，http属于那一层

四层协议表，http属于应用层

| 名称 | 结构 |
| :-- | :-- |
| 应用层 | HTTP FTP TFIP SMTP SNMP DNS |
| 传输层  | TCP UDP |
| 网络层 | ICMP IGMP IP ARP RARP |
| 网络物理接口 | 由底层网络定义  |

### 302状态码什么意思

临时重定向，搜索引擎不会收录跳转后的地址

### 浏览器地址栏输入域名回车后发生了什么

1，DNS解析域名得到ip地址
2，tcp进行3次握手
3，发送http请求
4，服务器解析http返回报文
5，浏览器渲染页面
6，断开连接