<div class="post-content">
<p>搭建 V2Ray 看这篇文章就够了！这是完完全全为小白准备的 V2Ray 搭建教程，详细的图文教程确保你可以百分百成功搭建 V2Ray 使用。</p>

<h2 id="前言">前言</h2>

<p>此 V2Ray 教程完完全全是为小白准备的，从购买 VPS 到使用 SSH 登录并使用 V2Ray 一键安装脚本配置 V2Ray，详细的图文教程确保你可以百分百成功搭建 V2Ray 使用，哪怕你只是一个小白。<br />
由于 V2Ray 的配置对于小白来说是非常不友好的，所以此 V2Ray 教程的 V2Ray 服务器端配置将会使用我本人撰写的 <a href="https://github.com/233boy/v2ray/wiki/V2Ray%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85%E8%84%9A%E6%9C%AC" rel="nofollow" target="_blank">V2Ray 一键安装脚本</a>，这是一个对小白友好的 V2Ray 一键脚本，简化 V2Ray 安装和部署，并且自动开启 BBR 优化，当然你也可以手动打开 BBR 来优化 V2Ray，也可以选择使用锐速来 优化 V2Ray。</p>

<h2 id="v2ray-简介">V2Ray 简介</h2>

<p>官网：<a href="https://www.v2ray.com" rel="nofollow" target="_blank">https://www.v2ray.com</a></p>

<p><a href="https://www.v2ray.com/" rel="nofollow" target="_blank">V2Ray(Project V)</a> 相对于 Shadowsocks，V2Ray 更像全能选手，拥有更多可选择的协议 / 传输载体 (Socks、HTTP、TLS、TCP、mKCP、WebSocket )，还有强大的路由功能，不仅仅于此，它亦包含 Shadowsocks 组件，你只需要安装 V2Ray，你就可以使用所有的 V2Ray 相关的特性包括使用 Shadowsocks，由于 V2Ray 是使用 GO 语言所撰写的，天生的平台部署优势，下载即可使用，当然啦，由于 V2Ray 的配置相对来说是很繁琐的，毫无夸张的说，但是有了本人所写的 <a href="https://github.com/233boy/v2ray/wiki/V2Ray%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85%E8%84%9A%E6%9C%AC" rel="nofollow" target="_blank">V2Ray 一键安装脚本</a> 加持下，使用 V2Ray 便会显得轻松多了。</p>

<h2 id="备注">备注</h2>

<p>总结一下此文章的大致流程，此 V2Ray 教程可百分百帮助你搭建 V2Ray 使用。哪怕你只是一个小白。</p>

<ul>
<li>购买一个 VPS<br />
想要搭建 V2Ray，就必须要拥有一台 VPS。<br /></li>
<li>获取 VPS 信息<br />
我们必须要知道 VPS IP 地址，root 用户密码，SSH 端口<br /></li>
<li>安装 Xshell<br />
Xshell 是一个 SSH 客户端，要登录 VPS，当然需要 SSH 客户端<br /></li>
<li>登录 VPS<br />
使用 Xshell 配置 VPS SSH 信息，然后登录<br /></li>
<li>安装 V2Ray<br />
安装过程你可以随意选择你喜欢的传输协议或者配置 Shadowsocks<br /></li>
<li>V2Ray 安装完成<br />
此时你可以使用客户端配置 V2Ray 使用了<br /></li>
<li>V2Ray 高级玩法<br />
配置 WebSocket + TLS ， HTTP/2 ， mKCP 等<br />
<br /></li>
</ul>

<h2 id="购买一个vps">购买一个VPS</h2>

<p>想要搭建 V2Ray， 拥有一个 VPS 是必需的。<br />
我们推荐使用：<a href="https://affpass.com/go/bwg" rel="nofollow" target="_blank">搬瓦工（Bandwagon Host）</a> VPS 来搭建 V2Ray，搬瓦工是一个对中国用户极度友好的 VPS 商家，有香港，CN2 GIA 等线路，支持支付宝付款，当然也是支持退款的！</p>

<blockquote>
<p>备注：按住 Ctrl + 单击， 即可在新窗口打开链接</p>
</blockquote>

<p>推荐购买的搬瓦工套餐如下</p>

<table>
<thead>
<tr>
<th align="center">线路</th>
<th align="center">CPU</th>
<th align="center">内存</th>
<th align="center">硬盘</th>
<th align="center">带宽</th>
<th align="center">流量</th>
<th align="center">价格</th>
<th align="center">链接</th>
</tr>
</thead>

<tbody>
<tr>
<td align="center">香港</td>
<td align="center">2 核</td>
<td align="center">8192 MB</td>
<td align="center">160 GB</td>
<td align="center">1 G</td>
<td align="center">500GB / 月</td>
<td align="center"><strong>$79.99 / 月</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/64" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">香港</td>
<td align="center">4 核</td>
<td align="center">16384 MB</td>
<td align="center">320 GB</td>
<td align="center">1 G</td>
<td align="center">1000GB / 月</td>
<td align="center">$159.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/65" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">香港</td>
<td align="center">6 核</td>
<td align="center">32768 MB</td>
<td align="center">640 GB</td>
<td align="center">1 G</td>
<td align="center">2000GB / 月</td>
<td align="center">$319.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/77" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">香港</td>
<td align="center">6 核</td>
<td align="center">32768 MB</td>
<td align="center">640 GB</td>
<td align="center">1 G</td>
<td align="center">4000GB / 月</td>
<td align="center">$599.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/78" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">2 核</td>
<td align="center">1 GB</td>
<td align="center">20 GB</td>
<td align="center"><strong>2.5 G</strong></td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$65.99 / 半年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/87" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">3 核</td>
<td align="center">2 GB</td>
<td align="center">40 GB</td>
<td align="center"><strong>2.5 G</strong></td>
<td align="center">2000GB / 月</td>
<td align="center">$69.99 / 季</td>
<td align="center"><a href="https://affpass.com/go/bwg/88" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">4 核</td>
<td align="center">4 GB</td>
<td align="center">80 GB</td>
<td align="center"><strong>2.5 G</strong></td>
<td align="center">3000GB / 月</td>
<td align="center">$49.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/89" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">6 核</td>
<td align="center">8 GB</td>
<td align="center">160 GB</td>
<td align="center"><strong>5 G</strong></td>
<td align="center">5000GB / 月</td>
<td align="center">$75.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/90" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">8 核</td>
<td align="center">16 GB</td>
<td align="center">320 GB</td>
<td align="center"><strong>5 G</strong></td>
<td align="center">8000GB / 月</td>
<td align="center">$139.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/91" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">10 核</td>
<td align="center">32 GB</td>
<td align="center">640 GB</td>
<td align="center"><strong>10 G</strong></td>
<td align="center">10000GB / 月</td>
<td align="center">$249.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/92" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">12 核</td>
<td align="center">64 GB</td>
<td align="center">1280 GB</td>
<td align="center"><strong>10 G</strong></td>
<td align="center">12000GB / 月</td>
<td align="center">$479.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/93" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">1 核</td>
<td align="center">512 MB</td>
<td align="center">10 GB</td>
<td align="center">1 G</td>
<td align="center">500GB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/94" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">2 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$25.99 / 季</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/72" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">3 核</td>
<td align="center">2048 MB</td>
<td align="center">40 GB</td>
<td align="center">1 G</td>
<td align="center">2000GB / 月</td>
<td align="center">$51.99 / 季</td>
<td align="center"><a href="https://affpass.com/go/bwg/73" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">4 核</td>
<td align="center">4096 MB</td>
<td align="center">80 GB</td>
<td align="center">1 G</td>
<td align="center">3000GB / 月</td>
<td align="center">$32.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/74" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">6 核</td>
<td align="center">8GB</td>
<td align="center">160 GB</td>
<td align="center">1 G</td>
<td align="center">5000GB / 月</td>
<td align="center">$62.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/75" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">8 核</td>
<td align="center">16GB</td>
<td align="center">320 GB</td>
<td align="center">1 G</td>
<td align="center">8000GB / 月</td>
<td align="center">$119.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/76" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">1 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/57" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">1 核</td>
<td align="center">2048 MB</td>
<td align="center">40 GB</td>
<td align="center">1 G</td>
<td align="center">2000GB / 月</td>
<td align="center">$52.99 / 半年</td>
<td align="center"><a href="https://affpass.com/go/bwg/58" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">2 核</td>
<td align="center">4096 MB</td>
<td align="center">80 GB</td>
<td align="center">1 G</td>
<td align="center">3000GB / 月</td>
<td align="center">$59.99 / 季</td>
<td align="center"><a href="https://affpass.com/go/bwg/59" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">2 核</td>
<td align="center">8 GB</td>
<td align="center">160 GB</td>
<td align="center">1 G</td>
<td align="center">5000GB / 月</td>
<td align="center">$39.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/67" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">3 核</td>
<td align="center">16 GB</td>
<td align="center">320 GB</td>
<td align="center">1 G</td>
<td align="center">8000GB / 月</td>
<td align="center">$79.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/68" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
<td align="center">-</td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">2 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1 TB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/44" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">3 核</td>
<td align="center">2 GB</td>
<td align="center">40 GB</td>
<td align="center">1 G</td>
<td align="center">2 TB / 月</td>
<td align="center">$52.99 / 半年</td>
<td align="center"><a href="https://affpass.com/go/bwg/45" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">4 核</td>
<td align="center">4 GB</td>
<td align="center">80 GB</td>
<td align="center">1 G</td>
<td align="center">3 TB / 月</td>
<td align="center">$19.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/46" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">5 核</td>
<td align="center">8 GB</td>
<td align="center">160 GB</td>
<td align="center">1 G</td>
<td align="center">4 TB / 月</td>
<td align="center">$39.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/47" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">6 核</td>
<td align="center">16 GB</td>
<td align="center">320 GB</td>
<td align="center">1 G</td>
<td align="center">5 TB / 月</td>
<td align="center">$79.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/48" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">普通</td>
<td align="center">7 核</td>
<td align="center">24 GB</td>
<td align="center">480 GB</td>
<td align="center">1 G</td>
<td align="center">6 TB / 月</td>
<td align="center">$119.99 / 月</td>
<td align="center"><a href="https://affpass.com/go/bwg/49" rel="nofollow" target="_blank">购买</a></td>
</tr>
</tbody>
</table>

<p>选择哪个套餐？如果你不知道选择哪个套餐<br />
下面这是最常见的购买套餐</p>

<table>
<thead>
<tr>
<th align="center">线路</th>
<th align="center">CPU</th>
<th align="center">内存</th>
<th align="center">硬盘</th>
<th align="center">带宽</th>
<th align="center">流量</th>
<th align="center">价格</th>
<th align="center">链接</th>
</tr>
</thead>

<tbody>
<tr>
<td align="center">普通</td>
<td align="center">2 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1 TB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/44" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2</td>
<td align="center">1 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/57" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">1 核</td>
<td align="center">512 MB</td>
<td align="center">10 GB</td>
<td align="center">1 G</td>
<td align="center">500GB / 月</td>
<td align="center"><strong>$49.99 / 年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/94" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA</td>
<td align="center">2 核</td>
<td align="center">1024 MB</td>
<td align="center">20 GB</td>
<td align="center">1 G</td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$25.99 / 季</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/72" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">CN2 GIA-E</td>
<td align="center">2 核</td>
<td align="center">1 GB</td>
<td align="center">20 GB</td>
<td align="center"><strong>2.5 G</strong></td>
<td align="center">1000GB / 月</td>
<td align="center"><strong>$65.99 / 半年</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/87" rel="nofollow" target="_blank">购买</a></td>
</tr>

<tr>
<td align="center">香港</td>
<td align="center">2 核</td>
<td align="center">8192 MB</td>
<td align="center">160 GB</td>
<td align="center">1 G</td>
<td align="center">500GB / 月</td>
<td align="center"><strong>$79.99 / 月</strong></td>
<td align="center"><a href="https://affpass.com/go/bwg/64" rel="nofollow" target="_blank">购买</a></td>
</tr>
</tbody>
</table>


<p>没有找到合适的套餐？你可以前往官网详细查看：<a href="https://affpass.com/go/bwg" rel="nofollow" target="_blank">https://bwh8.net/cart.php</a></p>

<p>哪个套餐好？<br />
一般来说，<strong>推荐购买 香港线路</strong> 或 <strong>CN2 GIA 线路</strong>，或者哪个便宜选择那个，说着当然如果你使用量比较多或者想要分享给同学和朋友一起用的话，选择合适的套餐即可。又或者你土豪的话，选择最贵的也行。</p>

<p><strong>VPS 速度：香港线路 &gt; CN2 GIA 线路 &gt; CN2 线路 &gt; 普通线路</strong></p>

<p><strong>香港套餐 VPS 的速度最快。</strong> 如果你非常在乎速度的话，建议购买香港线路的 VPS，当然，但价格贵，流量相对其他套餐来说也是比较少的……退一步的选择是 CN2 GIA 线路，这个线路的速度也比较好。</p>

<p>线路是比较重要的，像香港和 CN2 GIA 线路到晚上一般不会怎么炸，其他的到了晚上可能会出现很慢慢的感觉。</p>

<p>我本人比较推荐 CN2 GIA 线路，稳定性，速度与价格适中选择，当然啦！如果你觉得价格太贵了，推荐你查看一下<a href="https://bwgjms.com/post/how-to-buy-justmysocks/" target="_blank">
     搬瓦工 Just My Socks  
</a>
，搬瓦工官方出品的代理服务，同样是 CN2 GIA 线路，<strong>每月仅需 $2.88 起！</strong>再也不用自己折腾搭建了，更不用担心 IP 被墙问题！<br />
Just My Socks 购买教程在这里：<a href="https://bwgjms.com/post/how-to-buy-justmysocks/" target="_blank">
     搬瓦工 Just My Socks 详细图文购买教程  
</a>
</p>

<p>毫无疑问！绝对的一分钱一分货。</p>

<blockquote>
<p>如果出现 out of stock 这样的提示，那就是这个套餐卖完了，选择其他套餐即可。</p>
</blockquote>

<h2 id="添加到购物车">添加到购物车</h2>

<p>在上面表格中选择想要购买的套餐，然后点击 <code>购买</code> 即可。<br />
将 VPS 添加到购物车</p>


<img src="https://i.loli.net/2018/11/18/5bf1684742682.png" alt="Add to Cart">


<p>说明一下，在Billing Cycle选项那里选择：<code>$xxxx USD Annually</code>，按年付的意思</p>

<p><strong>推荐按年付，比按月付最高可省55%的钱</strong><br />
Location 选择: <code>HK - Hong Kong xxxxx</code> （如果你购买的是香港线路的话）<br />
否则选择: <code>US - Los Angeles xxxxx</code><br />
然后点击<code>Add To Cart</code></p>

<h2 id="结算">结算</h2>

<p>推荐使用搬瓦工 6.25% 优惠码：<a href="https://affpass.com/go/bwg" rel="nofollow" target="_blank">BWH26FXH3HIQ</a></p>

<p>这个优惠码是搬瓦工目前最高优惠的优惠码<br />
输入优惠码之后点击 <code>Validate Code &gt;&gt;</code></p>


<img src="https://i.loli.net/2018/11/18/5bf168474423c.png" alt="输入优惠码">


<p>然后点击 <code>Checkout</code><br />
如下图所示：已经使用搬瓦工优惠码</p>


<img src="https://i.loli.net/2018/11/18/5bf1684703cec.png" alt="Checkout">


<p>然后会提示你注册账号 （如果你没账号或者还没登录）<br />
请按照下面图片提示来填写~</p>


<img src="https://i.loli.net/2018/11/18/5bf16da6832c6.png" alt="Checkout now">


<p>要注意的是，Country 选项记得选择 <code>China</code>，Payment Method 选择 <code>Alipay</code><br />
不要忘了勾上 I have read and agree to the Terms of Service<br />
然后 <code>Complete Order</code></p>

<div class="post-ad">
    
    
    
</div>


<h2 id="付款">付款</h2>

<p>点击 <code>Pay now</code><br />
之后便会跳转到支付宝付款界面，完成付款即可</p>


<img src="https://i.loli.net/2018/11/18/5bf1684732175.png" alt="Pay now">


<h2 id="获取vps信息">获取VPS信息</h2>

<blockquote>
<p>备注：按住 Ctrl + 单击， 即可在新窗口打开链接</p>
</blockquote>

<p>确保你已经成功付款之后<br />
打开：<a href="https://bwh8.net/clientarea.php?action=products" rel="nofollow" target="_blank">https://bwh8.net/clientarea.php?action=products</a><br />
选择 <code>KiwiVM Control Panel</code><br />
如果出现以下界面，稍等一会，等待资源分配即可。</p>


<img src="https://i.loli.net/2017/09/05/59ae8a8fc83e2.jpg" alt="Task in progress">


<p>等待两三分钟，刷新一下。<br />
这是已经在运行的界面，请记下 <code>IP address</code>然后点击 <code>stop</code></p>


<img src="https://i.loli.net/2018/11/18/5bf1684733cec.png" alt="停止VPS">


<p>当出现：Great Success! Virtual server will stop in a few seconds. 相关提示<br />
证明 VPS 已经停止了，我们需要重装一个系统。点击左边的 <code>Install new OS</code><br />
之后选择 <code>debian-9-x86_64</code><br />
再勾上：I agree that all existing data on my VPS will be lost.<br />
然后点击 <code>Reload</code></p>


<img src="https://i.loli.net/2018/11/12/5be904c32f31b.jpg" alt="Install new OS">


<p>当点击 <code>Reload</code> 之后，稍等片刻将会出现下图所示的界面，<br />
请务必记下： <code>You will need a new root password to access your VPS：xxxx</code><br />
还有：<code>New SSH Port:</code><br />
一个是root密码，一个是SSH端口</p>


<img src="https://i.loli.net/2018/11/18/5bf168473b33d.png" alt="Reload">


<p>OK，这时我们已经获取到VPS的信息了。</p>

<h2 id="安装-xshell">安装 Xshell</h2>

<blockquote>
<p>备注：按住 Ctrl + 单击， 即可在新窗口打开链接</p>
</blockquote>

<p>Xshell 是一个易用的 SSH 客户端，要登录 VPS，当然需要 SSH 客户端</p>

<p><a href="https://fingerit-my.sharepoint.com/:u:/g/personal/ai_fingertc_com/EeP_cDRqGvpMtLoaJc1zk5AB-nDlc71rt9fQWIH4I5ShPg?e=jvAzk6" rel="nofollow" target="_blank">Xshell 下载链接点我</a></p>

<p>这是一个绿色版本的 Xshell ，打开链接后，就点击 <code>下载</code>，下载好了之后，就双击打开，然后点击 <code>浏览...</code> 可以选择解压的路径，比如说 D 盘，之后再选择 <code>解压</code> 即可。</p>


<img src="https://i.loli.net/2018/12/27/5c24f0c995b84.jpg" alt="解压 Xshell">


<p>然后在解压的目录找到 <code>Xshell+Xftp 绿色版本</code> 文件夹，打开它，之后找到 <code>!安装.bat</code> 并且右键选择 <code>以管理员身份运行</code>，安装完成后会有一个提示窗口，关闭即可。这样来就安装好了 Xshell</p>


<img src="https://i.loli.net/2018/12/27/5c24f0c9994a4.jpg" alt="安装 Xshell">


<h2 id="登录vps">登录VPS</h2>

<p>在桌面找到 Xshell ，打开它，新建一个会话。</p>


<img src="https://i.loli.net/2018/12/27/5c24f0c8d78f6.jpg" alt="新建会话">


<p>主机写上你的 VPS IP 地址，端口写上 SSH 端口。</p>


<img src="https://i.loli.net/2018/11/18/5bf1684735776.png" alt="new">


<p>之后点击 用户身份验证，用户名：<code>root</code>，密码：你的 root 密码。然后点击确定</p>


<img src="https://i.loli.net/2018/11/18/5bf1684737f3c.png" alt="user-and-passwd">


<p>之后选择连接。</p>


<img src="https://i.loli.net/2018/11/18/5bf1684739aab.png" alt="连接">


<p>然后会提示SSH安全警告，选择，接受并保存。</p>


<img src="https://i.loli.net/2018/11/18/5bf15f4b04c72.png" alt="SSH 安全警告">


<p>这是登录成功后的界面</p>


<img src="https://i.loli.net/2018/11/18/5bf15f4b0cd33.png" alt="登陆成功">


<h2 id="安装-v2ray">安装 V2Ray</h2>

<p>输入下面命令回车，你可以复制过去，然后在 Xshell 界面按 Shift + Insert 即可粘贴，不能按 Ctrl + V 的。。</p>

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

<p>然后选择安装，即是输入 1 回车<br />
选择传输协议，如果没有特别的需求，使用默认的 TCP 传输协议即可，直接回车<br />
选择端口，如果没有特别的需求，使用默认的端口即可，直接回车<br />
是否屏蔽广告，除非你真的需要，一般来说，直接回车即可</p>


<img src="https://i.loli.net/2019/01/05/5c305224cfe05.jpg" alt="安装 V2Ray">


<p>是否配置 Shadowsocks ，如果不需要就直接回车，否则就输入 Y 回车<br />
Shadowsocks 端口，密码，加密方式这些东西自己看情况配置即可，我个人当然是全部直接回车。。<br />
OK，按回车继续</p>


<img src="https://i.loli.net/2019/01/05/5c305224ad11c.jpg" alt="配置 Shadowsocks">


<p>安装信息，如果确保没有什么问题了，按回车继续</p>


<img src="https://i.loli.net/2019/01/05/5c3052248ca3e.jpg" alt="安装信息">


<p>(备注，安装信息会因你的配置而变化..不用在乎这截图)<br />
(备注，由于我懒&hellip;脚本显示的一些信息可能会跟上面的截图有少许不同，但实际上都是很简单明了的)</p>

<h2 id="v2ray-安装完成">V2Ray 安装完成</h2>

<p>OK，此时 V2Ray 已经安装完成了。</p>


<img src="https://i.loli.net/2019/01/05/5c305224bbd75.jpg" alt="V2Ray 安装完成">


<p>如上图所示，V2Ray 配置信息，Shadowsocks 配置信息都有了<br />
如果你使用过 Shadowsocks ，那么现在你可以测试一下 Shadowsocks 配置了，看看是否能正常使用。<br />
如果你使用过 V2Ray 某些客户端，那么现在也可以测试一下配置了。<br />
(备注，可能某些 V2Ray 客户端的选项或描述略有不同，但事实上，上面的 V2Ray 配置信息已经足够详细，由于客户端的不同，请对号入座。)</p>

<h2 id="v2ray-客户端使用教程">V2Ray 客户端使用教程</h2>

<p>暂停一下，我想，看这篇的孩子多数都是萌新，由于 V2Ray 已经安装完成了，所以此时你应该尝试使用 V2Ray 来连接上真正的互联网了。</p>

<blockquote>
<p>Windows<br />
<a href="https://github.com/233boy/v2ray/wiki/V2RayN%E4%BD%BF%E7%94%A8%E6%95%99%E7%A8%8B" rel="nofollow" target="_blank">V2RayN使用教程</a></p>
</blockquote>

<h2 id="v2ray-管理面板">V2Ray 管理面板</h2>

<p>现在可以尝试一下输入 <code>v2ray</code> 回车，即可管理 V2Ray</p>


<img src="https://i.loli.net/2019/01/05/5c305224c606e.jpg" alt="V2Ray 管理面板">


<h2 id="tcp-阻断">TCP 阻断</h2>

<p>如果你觉得你的小鸡出现了这种情况，那么可以尝试使用 UDP 协议相关的 mKCP<br />
当然，用了我的脚本那是很简单的啦，直接输入 <code>v2ray config</code> 然后选择修改 V2Ray 传输协议<br />
之后再选择 mKCP 相关的就行咯<br />
备注：使用 mKCP 或许还可以提高速度，但由于 UDP 的原因也许会被运营商 Qos，这是无解的。</p>

<h2 id="快速管理-v2ray">快速管理 V2Ray</h2>

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

<div class="post-ad">
    
    
    
</div>


<h2 id="优化-v2ray">优化 V2Ray</h2>

<p>由于本人的脚本在 Debian9 系统会自动开启 BBR 优化加速了，所以不需要再安装 BBR 优化了，<br />
如果你还是觉得网络比较慢的话，你可以尝试使用含有 mKCP 的传输协议，这个 mKCP 的东东，简单一点说就像 Kcptun 一样加速，并且还能进行伪装 (可选)，但是由于 mKCP 是使用 UDP 协议的，也许运营商会限速得更加厉害，网络变得更加慢。但不管怎么样，你都可以随时尝试一下。<br />
服务器输入 <code>v2ray config</code> 回车，然后选择 修改 V2Ray 传输协议，再接着选择 mKCP 相关的传输协议即可<br />
如果你是使用其他商家的 VPS 并且是按照此教程流程来安装 V2Ray 的话，那么你可以输入 <code>v2ray bbr</code> 回车，然后选择安装 BBR 或者 锐速 来优化 V2Ray<br />
只是还想再啰嗦一下，如果你是使用国际大厂的 VPS，并且是按照此教程流程来安装 V2Ray 的话，请自行在安全组 (防火墙) 开放端口和 UDP 协议 (如果你要使用含有 mKCP 的传输协议)</p>

<h2 id="websocket-tls">WebSocket + TLS</h2>

<p>实现 WebSocket + TLS 超级无敌简单，前提是要拥有一个能正常解析的域名 (并且知道怎么解析域名)<br />
服务器输入 <code>v2ray config</code> 回车，然后选择 修改 V2Ray 传输协议，再选择 WebSocket + TLS，即是输入 4，接着输入你的域名，然后我都懒得说了，脚本都那么简单明了，我还瞎BB干嘛&hellip;<br />
哈哈&hellip;可能有不少人在折腾 V2Ray 实现 WS + TLS 的时候真的是搞到很蛋痛咯，有些人的教程可能说得不是很清楚，或者是直接忽略小白萌新这些亲爱的用户，嗯，小白们好好加油吧，请尽量多学一些基础知识，别总是做伸手党，对于毫无交集的陌生人，人家并没有任何义务要帮你的啊<br />
偷偷跟你说&hellip;使用 WebSocket + TLS 会有断流的问题<br />
多说一句，不要被某些人带节奏，WS + TLS 并不是 V2Ray 的神级配置，该墙还是会墙，墙你不需要理由<br />
备注一下啦，这里我没写怎么教你注册域名啦，怎么解析域名啦，如果你真的想要使用 WebSocket + TLS，那就 自己谷歌摸索一下，其实好简单的啦！<br />
我本人并没有在使用 WS + TLS (WebSocket + TLS)，我用 TCP，就是用一键脚本全程回车的那种懒人</p>

<h2 id="http-2">HTTP/2</h2>

<p>实现 HTTP/2 (h2) 也超级无敌简单，和 WebSocket + TLS 一样，也就是只要一个域名就够<br />
服务器输入 <code>v2ray config</code> 回车，然后选择 修改 V2Ray 传输协议，再选择 HTTP/2，即是输入 16，然后………看上面的 WebSocket + TLS 的相关。<br />
备注一下，HTTP/2 相比 WS + TLS (WebSocket + TLS) ，在浏览网页时有一些优势。速度是差不多的啦</p>

<h2 id="mkcp">mKCP</h2>

<p>mKCP 这个东东其实就是 KCP 协议，反正你知道是能提速的就行，但是不保证都能提速，还能避免 TCP 阻断，但是也可以会被运营商 Qos.<br />
使用方法：服务器输入 <code>v2ray config</code> 回车，然后选择 修改 V2Ray 传输协议，之后再选择 mKCP 相关的就行</p>

<h2 id="搬瓦工-vps-速度慢">搬瓦工 VPS 速度慢</h2>

<p>由于本教程使用了 搬瓦工 VPS 做为教程的一部分，那么相信有些新接触 VPS 的同学可能会是按照教程使用了 搬瓦工 VPS 翻墙。<br />
如果你觉得搬瓦工 VPS 速度慢，你可以尝试修改一下端口，服务器输入 <code>v2ray config</code> ，，然后选择 修改 V2Ray 端口 即可，建议使用常见的端口，比如说 443，当然，为了更加安全隐蔽，你可以直接尝试使用 WebSocket + TLS 或者 HTTP/2 协议，但是使用这两个协议对于没有接触过 域名 的同学相对来说会是比较困难的。<br />
搬瓦工 VPS 速度慢的一个主要原因可能会是因为端口限速，如果你已经修改端口为 443，速度还是慢的话，我建议你尝试使用 mKCP 协议。</p>

<h2 id="telegram-专用代理">Telegram 专用代理</h2>

<p>如果你在使用 Telegram 的话，你可以配置一个 Telegram 的专用代理，这样来，在某些情况下你就不需要再开一个代理软件了。<br />
输入 <code>v2ray tg</code> 即可配置 TG 专用代理<br />
配置 Telegram MTProto</p>


<img src="https://i.loli.net/2019/01/05/5c3052248ea74.jpg" alt="配置Telegram MTProto">


<p>Telegram MTProto 配置信息</p>


<img src="https://i.loli.net/2019/01/05/5c3052248a10f.jpg" alt="Telegram MTProto 配置信息">


<h2 id="v2ray-多用户">V2Ray 多用户</h2>

<p>目前此 V2Ray 一键脚本只支持配置一个 V2Ray 账号&hellip;一个 Shadowsocks 账号<br />
说着当然，如果你是大佬，配置 多用户 这种事，不是分分钟的事么？</p>

<h2 id="查看配置-修改配置-端口-传输协议">查看配置 / 修改配置 / 端口 / 传输协议…… ？</h2>

<p>请看上面的快速管理。。。或者直接输入 <code>v2ray</code> 回车，找到你想要执行的功能。</p>

<h2 id="哪个传输协议好">哪个传输协议好？</h2>

<p>心中无杂念，用 TCP<br />
ISP 常作怪，用 动态端口<br />
小鸡速度不好，用 mKCP<br />
处子之身，用 WS + TLS</p>

<h2 id="v2ray-脚本说明">V2Ray 脚本说明</h2>

<p><a href="https://github.com/233boy/v2ray/wiki/V2Ray%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85%E8%84%9A%E6%9C%AC" rel="nofollow" target="_blank">V2Ray 一键安装脚本</a></p>

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
<strong>目前只支持配置一个 V2Ray 账号&hellip;一个 Shadowsocks 账号。。不支持 SSR。。</strong></p>

<h2 id="分享">分享</h2>

<p>如果这篇文章对你帮助的话，记得分享给你的小伙伴们。</p>

<h2 id="其他">其他</h2>

<p>请勿违反国家法律法规，否则后果自负！<br />
低调低调低调。</p>

<h2 id="资助-v2ray">资助 V2Ray</h2>

<p>如果你觉得 V2Ray 很好用，能解决你的某些问题，请考虑 <a href="https://www.v2ray.com/chapter_00/02_donate.html" rel="nofollow" target="_blank">
     资助 V2Ray 发展  
</a>
。</p>

<h2 id="结束">结束</h2>

<p>我有写少了什么吗？我这种小小白萌新看了这教程都觉得很明白了啊。<br />
一次不会，那么就两次，还是不会，那就再来一次。可还是不会啊？大佬请收下我的膝盖。</p>

<p><img src="https://affpass.com/ga?ga=v2ray&amp;dt=github.wiki.2&amp;dr=&amp;ul=zh-CN&amp;sd=24-bit&amp;sr=&amp;vp=&amp;z=0&amp;dl=/github/2" alt="" /></p>
</div>