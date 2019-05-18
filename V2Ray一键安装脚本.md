<div class="post-content">
<p>支持 V2Ray 绝大多数传输协议，WebSocket + TLS，HTTP/2，Shadowsocks，动态端口，集成 BBR 和锐速优化等。</p>

<h2 id="前言">前言</h2>

<p>V2Ray 官网：<a href="https://www.v2ray.com" rel="nofollow" target="_blank">https://www.v2ray.com</a></p>

<p>V2Ray 是一个于 Shadowsocks 之后非常好用的代理软件，但是由于 V2Ray 的配置略复杂，GUI 客户端不完善，所以 V2Ray 并没有像 Shadowsocks 在科学上网人群之中那么流行。<br />
不过我想，像我这种小小白萌新，更需要的是一个好用的一键安装脚本……<br />
所以，此脚本是为了方便像我这种小小白萌新更加容易去使用 V2Ray，配置 V2Ray。希望对你有帮助 ^_^</p>

<blockquote>
<p>如果你是毫无经验的小白，搭建 V2Ray 请看此教程：<a href="https://github.com/233boy/v2ray/wiki/V2Ray%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E5%9B%BE%E6%96%87%E6%95%99%E7%A8%8B" rel="nofollow" target="_blank">V2Ray搭建详细图文教程</a></p>
</blockquote>

<h2 id="更新日志">更新日志</h2>

<ul>
<li>2018-01-28<br />
第一个完善版本发布&hellip;<br /></li>
<li>2018-5-2<br />
支持 HTTP/2 &hellip; 懒得发一个版本就在这里写一下<br /></li>
<li>2018-5-26<br />
支持 Socks5 &hellip;<br /></li>
<li>2019-1-5<br />
v3 版本，更加好用了。新年快乐！<br />
<br /></li>
</ul>

<h2 id="温馨提示">温馨提示</h2>

<p><strong>特么这个脚本没有挖矿，没有挖矿，没有挖矿。</strong> 我很抱歉……认真的开了个玩笑<br />
脚本是开源的，开源地址： <a href="https://github.com/233boy/v2ray" rel="nofollow" target="_blank">https://github.com/233boy/v2ray</a></p>

<h2 id="功能特点">功能特点</h2>

<ol>
<li>支持 V2Ray 多数传输协议<br /></li>
<li>支持 WebSocket + TLS / HTTP/2<br /></li>
<li>支持 动态端口 (WebSocket + TLS，Socks5， HTTP/2 除外)<br /></li>
<li>支持 屏蔽广告<br /></li>
<li>支持 配置 Shadowsocks<br /></li>
<li>支持 下载客户端配置文件 (不用 Xshell 也可以下载)<br /></li>
<li>客户端配置文件同时支持 SOCKS 和 HTTP<br /></li>
<li>支持 生成 V2Ray 配置二维码链接 (仅适用部分客户端)<br /></li>
<li>支持 生成 V2Ray 配置信息链接<br /></li>
<li>支持 生成 Shadowsocks 配置二维码链接<br /></li>
<li>支持修改 V2Ray 传输协议<br /></li>
<li>支持修改 V2Ray 端口<br /></li>
<li>支持修改 动态端口<br /></li>
<li>支持修改 用户ID<br /></li>
<li>支持修改 TLS 域名<br /></li>
<li>支持修改 Shadowsocks 端口<br /></li>
<li>支持修改 Shadowsocks 密码<br /></li>
<li>支持修改 Shadowsocks 加密协议<br /></li>
<li>自动启用 BBR 优化 (如果内核支持)<br /></li>
<li>集成可选安装 BBR (by teddysun.com)<br /></li>
<li>集成可选安装 锐速 (by moeclub.org)<br /></li>
<li>一键 查看运行状态 / 查看配置信息 / 启动 / 停止 / 重启 / 更新 / 卸载 / 等等…<br /></li>
<li>人性化向导 &amp; 纯净安装 &amp; 卸载彻底<br />
<br /></li>
</ol>

<p>哈哈哈..我故意要写够 23 条的。说着当然，脚本肯定都会有如上所说的功能。</p>

<h2 id="安装或卸载">安装或卸载</h2>

<blockquote>
<p>温馨提醒，此脚本默认屏蔽一些不友好的网站！(仅限轮子相关)</p>
</blockquote>

<p>要求：Ubuntu 16+ / Debian 8+ / CentOS 7+ 系统<br />
推荐使用 Debian 9 系统，脚本会自动启用 BBR 优化。<br />
备注：不推荐使用 Debian 8 系统，因为 Caddy 申请证书可能会出现一些莫名其妙的问题<br />
<strong>强烈推荐使用 <a href="https://affpass.com/go/bwg" rel="nofollow" target="_blank">搬瓦工VPS</a>，稳定，快速，针对中国线路专门优化，完全无须担心跑路，服务好，30天退款保证。<br />
在这里可以找到 <a href="https://233vps.com/post/bandwagonhost-plans/" target="_blank">
     搬瓦工 VPS 套餐大全  
</a>
 ，优惠码在这里： <a href="https://233vps.com/post/bandwagonhost-coupon-code/" target="_blank">
     搬瓦工 VPS 优惠码  
</a>
</strong><br />
使用 root 用户输入下面命令安装或卸载</p>

<pre><code>bash &lt;(curl -s -L https://git.io/v2ray.sh)
</code></pre>

<div class="post-ad">
    
    
    
</div>


<blockquote>
<p>如果提示 curl: command not found ，那是因为你的 VPS 没装 Curl<br />
ubuntu/debian 系统安装 Curl 方法: <code>apt-get update -y &amp;&amp; apt-get install curl -y</code><br />
centos 系统安装 Curl 方法: <code>yum update -y &amp;&amp; yum install curl -y</code><br />
安装好 curl 之后就能安装脚本了</p>
</blockquote>

<p>备注：安装完成后，输入 <code>v2ray</code> 即可管理 V2Ray<br />
如果提示你的系统不支持此脚本，那么请尝试更换系统</p>

<p>下面是此脚本的一些截图</p>

<p>安装选项</p>


<img src="https://i.loli.net/2019/01/05/5c305224cfe05.jpg" alt="安装 V2Ray">


<p>配置 Shadowsocks</p>


<img src="https://i.loli.net/2019/01/05/5c305224ad11c.jpg" alt="配置 Shadowsocks">


<p>安装完成</p>


<img src="https://i.loli.net/2019/01/05/5c305224bbd75.jpg" alt="V2Ray 安装完成">


<p>管理面板</p>


<img src="https://i.loli.net/2019/01/05/5c305224c606e.jpg" alt="V2Ray 管理面板">


<div class="post-ad">
    
    
    
</div>


<h2 id="telegram-专用代理">Telegram 专用代理</h2>

<p>如果你在使用 Telegram 的话，你可以配置一个 Telegram 的专用代理，这样来，在某些情况下你就不需要再开一个代理软件了。<br />
输入 <code>v2ray tg</code> 即可配置 TG 专用代理<br />
配置 Telegram MTProto</p>


<img src="https://i.loli.net/2019/01/05/5c3052248ea74.jpg" alt="配置Telegram MTProto">


<p>Telegram MTProto 配置信息</p>


<img src="https://i.loli.net/2019/01/05/5c3052248a10f.jpg" alt="Telegram MTProto 配置信息">


<h2 id="快速管理">快速管理</h2>

<p><code>v2ray info</code> 查看 V2Ray 配置信息<br />
 <code>v2ray config</code> 修改 V2Ray 配置<br />
 <code>v2ray link</code> 生成 V2Ray 配置文件链接<br />
 <code>v2ray infolink</code> 生成 V2Ray 配置信息链接<br />
 <code>v2ray qr</code> 生成 V2Ray 配置二维码链接<br />
 <code>v2ray ss</code> 修改 Shadowsocks 配置<br />
 <code>v2ray ssinfo</code> 查看 Shadowsocks 配置信息<br />
 <code>v2ray ssqr</code> 生成 Shadowsocks 配置二维码链接<br />
 <code>v2ray status</code> 查看 V2Ray 运行状态<br />
 <code>v2ray start</code> 启动 V2Ray<br />
 <code>v2ray stop</code> 停止 V2Ray<br />
 <code>v2ray restart</code> 重启 V2Ray<br />
 <code>v2ray log</code> 查看 V2Ray 运行日志<br />
 <code>v2ray update</code> 更新 V2Ray<br />
 <code>v2ray update.sh</code> 更新 V2Ray 管理脚本<br />
 <code>v2ray uninstall</code> 卸载 V2Ray</p>

<h2 id="配置文件路径">配置文件路径</h2>

<p>V2Ray 配置文件路径：/etc/v2ray/config.json<br />
Caddy 配置文件路径：/etc/caddy/Caddyfile<br />
脚本配置文件路径: /etc/v2ray/233blog_v2ray_backup.conf</p>

<blockquote>
<p>警告，请不要修改脚本配置文件，免得出错。。<br />
如果你不是有特别的需求，也不要修改 V2Ray 配置文件<br />
不过也没事，若你实在想要瞎折腾，出错了的话，你就卸载，然后重装，再出错 ，再卸载，再重装，重复到自己不再想折腾为止。。</p>
</blockquote>

<h2 id="ws-tls-http2">WS+TLS / HTTP2</h2>

<p>如果你使用了这两个协议，那么就会使用了脚本自带的 Caddy 集成<br />
不管如何，不建议直接去更改 Caddy 的配置：/etc/caddy/Caddyfile<br />
如果你需要配置其他网站相关，请将网站的配置文件放到 /etc/caddy/sites 目录下，然后重启 Caddy 进程即可，脚本默认生成的 Caddy 的配置会加载 /etc/caddy/sites 这个目录下的所有配置文件。<br />
所以，请将你的网站配置文件放到 /etc/caddy/sites 目录下，完完全全不需要去更改 /etc/caddy/Caddyfile<br />
记得重启 Caddy 进程：service caddy restart</p>

<h2 id="caddy-插件相关">Caddy 插件相关</h2>

<p>本脚本集成了 Caddy，但不集成任何 Caddy 插件，如果你需要安装某些 Caddy 插件，你可以使用官方的 Caddy 安装脚本来一键安装。<br />
本人的脚本集成的 Caddy 的安装路径，跟 Caddy 官方的安装脚本是一致的。所以可以直接安装，不会有任何问题</p>

<p>举个例子，安装包含 http.filebrowser 插件的 Caddy，执行如下命令即可</p>

<pre><code>curl https://getcaddy.com | bash -s personal http.filebrowser
</code></pre>

<p>你可以在 <a href="https://caddyserver.com/download" rel="nofollow" target="_blank">https://caddyserver.com/download</a> 找到 Caddy 更多插件和安装命令。</p>

<h2 id="备注">备注</h2>

<p>V2Ray 客户端配置文件 SOCKS 监听端口为 <code>2333</code>， HTTP 监听端口为 <code>6666</code><br />
可能某些 V2Ray 客户端的选项或描述略有不同，但事实上，此脚本显示的 V2Ray 配置信息已经足够详细，由于客户端的不同，请对号入座。</p>

<h2 id="反馈问题">反馈问题</h2>

<p>请先查阅：<a href="https://v2ray6.com/post/10/">V2Ray 一键安装脚本疑问集合</a><br />
Telegram 群组：<a href="https://t.me/blog233" rel="nofollow" target="_blank">
     https://t.me/blog233 
</a>
<br />
Github 反馈：<a href="https://github.com/233boy/v2ray/issues" rel="nofollow" target="_blank">
     https://github.com/233boy/v2ray/issues 
</a>
<br />
任何有关于 V2Ray 的问题，请自行到 V2Ray 官方反馈。<br />
<strong>目前只支持配置一个 V2Ray 账号&hellip;一个 Shadowsocks 账号。。不支持 SSR。。</strong><br />
<strong>使用国际大厂的 VPS，请自行在安全组 (防火墙) 开放端口和 UDP 协议 (如果你要使用含有 mKCP 的传输协议)</strong></p>

<h2 id="备份">备份</h2>

<p>为了避免由于不可抗拒的原因所造成本人主动删除脚本，所以建议请将本脚本 Fork 一份<br />
备份地址：<a href="https://github.com/233boy/v2ray/fork" rel="nofollow" target="_blank">
     https://github.com/233boy/v2ray/fork 
</a>
<br />
安装方法，确保你已经 Fork 了脚本，将 233boy 修改成你的 Github 用户名</p>

<pre><code>git clone https://github.com/233boy/v2ray -b master
cd v2ray
chmod +x install.sh
./install.sh local
</code></pre>

<div class="post-ad">
    
    
    
</div>


<p>如果提示 git 命令不可用，那就自己安装咯，不会安装啊？我也不知道啊。哈哈</p>

<h2 id="及时更新脚本">及时更新脚本</h2>

<p>为确保你能愉快使用，请留意使用 <code>v2ray update.sh</code> 命令来更新管理脚本。<br />
脚本难免会有 BUG，所以建议有空就检查一下更新情况。</p>

<h2 id="关注脚本最新动态">关注脚本最新动态</h2>

<p>本人会在 <a href="https://t.me/blog2333" rel="nofollow" target="_blank">本站 Telegram 公告频道</a> 推送脚本最新动态相关，如果你使用 Telegram 的话，可以关注一下。<br />
当然啦，你也可以加入 <a href="https://t.me/blog233" rel="nofollow" target="_blank">本站 Telegram 群组</a> 来吹水。</p>

<h2 id="资助-v2ray">资助 V2Ray</h2>

<p>如果你觉得 V2Ray 很好用，能解决你的某些问题，请考虑 <a href="https://www.v2ray.com/chapter_00/02_donate.html" rel="nofollow" target="_blank">
     资助 V2Ray 发展  
</a>
。</p>

<h2 id="感谢">感谢</h2>

<p>V2Ray：<a href="https://www.v2ray.com/" rel="nofollow" target="_blank">
     https://www.v2ray.com/ 
</a>
</p>

<h2 id="版权">版权</h2>

<p>此脚本使用 GPL v3 协议共享。</p>

<h2 id="分享">分享</h2>

<p>如果觉得脚本好用，记得分享给你的其他小伙伴们哦~</p>

<h2 id="其他">其他</h2>

<p>请勿违反国家法律法规，否则后果自负！<br />
使用一键脚本并不会害了你，并且会让你节省大量的时间，工具从来都是为了更快的解决问题。</p>

<p><img src="https://affpass.com/ga?ga=v2ray&amp;dt=github.wiki.1&amp;dr=&amp;ul=zh-CN&amp;sd=24-bit&amp;sr=&amp;vp=&amp;z=0&amp;dl=/github/1" alt="" /></p>
</div>