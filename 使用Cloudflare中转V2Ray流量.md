<div class="post-content">
<p>担心 IP 被墙？或者不想 IP 被墙？是的！使用 Cloudflare 来中转 V2Ray 的 WebSocket 流量就行！由于使用了 Cloudflare 中转，所以墙根本不知道背后的 IP 是多少，你可以愉快的玩耍了~</p>

<h2 id="提醒">提醒</h2>

<p>如果你不是使用 移动宽带 的用户，那么使用 Cloudflare 中转的速度相对来说是比较慢的，这个是因为线路的问题，无解。<br />
<strong>警告警告警告</strong><br />
<strong>该教程目前写得比较简陋，以后应该会增加详细图文教程</strong><br />
<strong>V2Ray 的 WS + TLS 不是神话，如果你没学会走路就不要急着跑</strong><br />
<strong>大佬。。。你如果是从来没接触过 V2Ray 的人一上来就开玩  WS + TLS</strong><br />
<strong>你真的不怕摔跤吗</strong><br />
<strong>你有解析过域名吗，知道什么是 A 记录吗，会修改 NS 吗。。</strong><br />
<strong>如果不懂，那就先补上这些知识再往下看</strong><br />
<strong>如果实在想玩 WS + TLS，请认认真真看教程</strong><br />
<strong>教程真的写得比较简陋，如果实在折腾不成功，那也很正常的，改天再来</strong><br />
<strong>或者直接放弃</strong></p>

<h2 id="准备">准备</h2>

<p>一个域名，建议使用免费域名<br />
确保域名已经可以在 Cloudflare 正常使用。<br />
<strong>在 Cloudflare 的 Overview 选项卡可以查看域名状态，请确保为激活状态，即是： Status: Active</strong><br />
怎么 SSH 连接上被墙的 IP ? Xshell 在属性那里可以设置代理，或者你可以在一台没有被墙的境外 VPS 使用 iptables 转发数据到被墙的机器上，此处不细说了。</p>

<h2 id="添加域名解析">添加域名解析</h2>

<p>在 DNS 选项卡那边添加一个 A 记录的域名解析，假设你的域名是 233blog.com，并且想要使用 www.233blog.com 作为翻墙的域名<br />
那么在 DNS 那里配置，Name 写 www，IPv4 address 写你的 VPS IP，<strong>务必把云朵点灰</strong>，然后选择 Add Record 来添加解析记录即可<br />
(如果你已经添加域名解析，<strong>请务必把云朵点灰</strong>，即是 DNS only)</p>

<p>OK，确保操作没有问题的话，继续</p>

<h2 id="安装-v2ray">安装 V2Ray</h2>

<blockquote>
<p>如果你已经使用本人提供的 V2Ray 一键安装脚本并安装了 V2Ray，那就直接输入 <code>v2ray config</code> 修改传输协议为 WebSocket + TLS</p>
</blockquote>

<p>如果你并没有使用本站提供的 V2Ray 一键安装脚本来安装 V2Ray<br />
那么现在开始使用吧，最好用的 V2Ray 安装脚本，保证你满意<br />
使用 root 用户输入下面命令安装或卸载</p>

<pre><code>bash &lt;(curl -s -L https://git.io/v2ray.sh)
</code></pre>

<blockquote>
<p>如果提示 curl: command not found ，那是因为你的小鸡没装 Curl<br />
ubuntu/debian 系统安装 Curl 方法: <code>apt-get update -y &amp;&amp; apt-get install curl -y</code><br />
centos 系统安装 Curl 方法: <code>yum update -y &amp;&amp; yum install curl -y</code><br />
安装好 curl 之后就能安装脚本了</p>
</blockquote>

<p>之后选择安装，传输协议选择 WebSocket + TLS (即是选择 4 )，V2Ray 端口随便，不要是 80 和 443 即可，<strong>然后输入你的域名，域名解析 Y ，自动配置 TLS 也是 Y</strong> ，其他就默认吧，一路回车。等待安装完成<br />
如果你的域名没有正确解析，安装会失败，解析相关看上面的 <strong>添加域名解析</strong></p>

<p>安装完成后会展示 V2Ray 的配置信息，并且会询问是否生成二维码等，不用管它，直接回车</p>

<p><strong>然后输入 v2ray status 查看一下运行状态，请确保 V2Ray 和 Caddy 都在运行</strong></p>

<p>如果没有问题的话，继续</p>

<h2 id="设置-crypto-和-开启中转">设置 Crypto 和 开启中转</h2>

<p>确保 Cloudflare 的 Crypto 选项卡的 SSL 为 Full<br />
<strong>并且请确保 SSL 选项卡有显示 Universal SSL Status Active Certificate 这样的字眼，如果你的 SSL 选项卡没有显示这个，不要急，只是在申请证书，24 小时内可以搞定。</strong></p>

<p><strong>然后在 DNS 选项卡那里，把刚才点灰的那个云朵图标，点亮它，一定要点亮一定要点亮一定要点亮</strong></p>

<p>云朵图标务必为橙色状态，即是 DNS and HTTP proxy(CDN)</p>

<h2 id="v2ray-配置信息">V2Ray 配置信息</h2>

<p>很好，现在接下来配置客户端使用<br />
输入 <code>v2ray info</code> 即可查看 V2Ray 的配置，如果你有使用某些 V2Ray 客户端，可以根据给出的配置的信息来配置使用了。赶紧测试吧</p>

<blockquote>
<p>V2Ray 客户端使用教程：<br />
Windows<br />
<a href="https://github.com/233boy/v2ray/wiki/V2RayN%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B" rel="nofollow" target="_blank">V2RayN使用教程</a></p>
</blockquote>

<div class="post-ad">
    
    
    
</div>


<p>什么鬼？对啊，就是如此简单啊，要不然你以为啊。</p>

<h2 id="备注">备注</h2>

<p>如果你的 VPS 位置是在美国西海岸的话，速度应该还算可以吧，如果不是在美国西海岸，那么也许速度会很慢，不过好在不用担心 IP 被墙或者能让被墙的 IP 重生也挺好的。难道不是么？<br />
如果你使用移动网络的话，那么 Cloudflare 的中转节点可能会在香港，速度也许会不错 (不完全保证)。</p>

<h2 id="无限域名备用">无限域名备用</h2>

<p>懒得写了，自己悟吧&hellip;<br />
反正绝大多数人只要知道怎么把墙的 IP 救活就行&hellip;<br />
算啦，我还是提示一下吧，WebSocket 协议，80 端口，Cloudflare 的 Crypto 选项卡 SSL 为 Flexible<br />
如果没有太多必要，不需要折腾这</p>

<h2 id="结束">结束</h2>

<p>哇，没有图文教程你就看不懂的话，我能怎么办，我也很绝望，我更加迷茫</p>

<p><img src="https://affpass.com/ga?ga=v2ray&amp;dt=github.wiki.5&amp;dr=&amp;ul=zh-CN&amp;sd=24-bit&amp;sr=&amp;vp=&amp;z=0&amp;dl=/github/5" alt="" /></p>
</div>