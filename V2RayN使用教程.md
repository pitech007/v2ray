<div class="post-content">
<p>V2RayN 是 PC 平台上一个对新手比较友好的 V2Ray Windows 客户端。写个简单的 V2RayN 使用教程帮助新手</p>

<h2 id="备注">备注</h2>

<p>以下教程均以使用了本站的一键安装 V2Ray 脚本为前提：<a href="https://github.com/233boy/v2ray/wiki/V2Ray%E4%B8%80%E9%94%AE%E5%AE%89%E8%A3%85%E8%84%9A%E6%9C%AC" rel="nofollow" target="_blank">V2Ray 一键安装脚本</a><br />
如果你还没有安装 V2Ray，可以参考这教程：<a href="https://github.com/233boy/v2ray/wiki/V2Ray%E6%90%AD%E5%BB%BA%E8%AF%A6%E7%BB%86%E5%9B%BE%E6%96%87%E6%95%99%E7%A8%8B" rel="nofollow" target="_blank">V2Ray搭建详细图文教程</a></p>

<h2 id="下载-v2rayn">下载 V2RayN</h2>

<blockquote>
<p>备注：按住 Ctrl + 单击， 即可在新窗口打开链接</p>
</blockquote>

<p>下载链接：<a href="https://github.com/2dust/v2rayN/releases/latest" rel="nofollow" target="_blank">
     https://github.com/2dust/v2rayN/releases/latest 
</a>
</p>

<p>然后选择 v2rayN-Core.zip 下载<br />
下载好了之后，解压，然后打开解压的文件夹<br />
目录结构大概如下图所示</p>


<img src="https://i.loli.net/2018/08/03/5b642bc166d29.png" alt="">


<h2 id="获取-v2ray-客户端配置">获取 V2Ray 客户端配置</h2>

<p>SSH 登录你的 VPS （如果你没登录）<br />
输入 <code>v2ray url</code></p>

<div class="post-ad">
    
    
    
</div>


<p>然后复制 vmess 链接 （将链接全选，然后鼠标右键，再选择复制即可）</p>

<h2 id="配置-v2rayn">配置 V2RayN</h2>

<p>双击 <code>v2rayN.exe</code> 启动，然后在任务栏托盘找到 V2RayN 图标并双击它<br />
添加一个 VMess 服务器</p>


<img src="https://i.loli.net/2018/02/10/5a7ef4f42264c.png" alt="">


<p>从剪贴板导入 URL</p>


<img src="https://i.loli.net/2018/02/10/5a7ef4f422311.png" alt="">


<p>设置本地监听端口，此处我将它设置为 2333</p>


<img src="https://i.loli.net/2018/02/10/5a7ef4f425367.png" alt="">


<h2 id="启用系统代理">启用系统代理</h2>

<p>在任务栏托盘找到 V2RayN 图标并鼠标右键，然后选择 启动系统代理<br />
并且设置 系统代理模式 》PAC 模式<br />
之后在 V2RayN 主界面，找到 检查更新 》检查更新 PAC</p>

<div class="post-ad">
    
    
    
</div>


<h2 id="测试一下">测试一下</h2>

<p>在完成上面的步骤的时候，正常来说，你已经处于翻出去的状态了<br />
OK，此时你已经自由了，赶紧打开 <a href="https://www.google.com/ncr" rel="nofollow" target="_blank">
     Google  
</a>
 找部十八减的大电影喵喵吧。哈哈</p>

<p><strong>备注一，如果你浏览器有使用 Proxy SwitchyOmega ，请点击它的图标然后选择 系统代理</strong><br />
<strong>备注二，如果你在使用 Firefox 浏览器，打开选项，找到网络代理，再选上 使用系统代理</strong></p>

<h2 id="暂停一下">暂停一下</h2>

<p>默认来说，使用 V2RayN 的 启动系统代理 来管理翻墙比较简捷一些，浏览器直接就能翻出去了<br />
说着当然，如果你想要手动来管理浏览器的代理也行，往下看<br />
<strong>备注，如果你不是有特别的需求，不需要参考下面的 Firefox 和 Chrome 的做法。</strong></p>

<h2 id="firefox-火狐浏览器">Firefox (火狐浏览器)</h2>

<p>(什么？没有在使用 Firefox ，那赶紧来试用吧，<a href="https://www.mozilla.org/zh-CN/firefox/" rel="nofollow" target="_blank">
     Firefox Quantum，更好的浏览器。  
</a>
)<br />
打开选项，找到网络代理</p>


<img src="https://i.loli.net/2018/01/28/5a6dc3460c705.png" alt="火狐设置代理">


<p>选择手动代理设置，输入 <code>127.0.0.1 和 2333</code>，勾选 使用 Socks v5 代理 DNS，然后确定即可。</p>


<img src="https://i.loli.net/2018/01/28/5a6dc34607f7b.png" alt="设置代理信息">


<p>OK，此时你已经自由了，赶紧打开 <a href="https://www.google.com/ncr" rel="nofollow" target="_blank">
     Google  
</a>
 找部十八减的大电影喵喵吧。哈哈</p>

<h2 id="chrome-谷歌浏览器">Chrome (谷歌浏览器)</h2>

<p>安装 Proxy SwitchyOmega （如果你已经安装，知道怎么设置代理吧。。SOCKS5 协议，2333 端口 ）<br />
在线安装：<a href="https://chrome.google.com/webstore/detail/padekgcemlokbadohgkifijomclgjgif" rel="nofollow" target="_blank">从 Chrome 应用商店 安装</a></p>

<p>手动安装如下：<br />
在 Chrome 地址栏输入 <strong>chrome://extensions</strong> 打开扩展程序，之后<br />
下载 <a href="https://github.com/FelisCatus/SwitchyOmega/releases" rel="nofollow" target="_blank">
     Proxy SwitchyOmega   
</a>
，打开链接后，找到 SwitchyOmega_Chromium.crx 下载，将下载完后的文件拖动到刚才打开的扩展程序的标签进行安装<br />
然后点击 添加扩展程序 即可</p>


<img src="https://i.loli.net/2018/01/28/5a6dc9a4ea438.png" alt="添加扩展程序">


<p>OK，在完成安装 Proxy SwitchyOmega 后，<br />
浏览器会自动打开一个 SwitchyOmega 选项的窗口，选择跳过教程，</p>


<img src="https://i.loli.net/2018/01/28/5a6dc9a4ed527.png" alt="跳过教程">


<p>选择 导入/导出，在线恢复，输入：<a href="https://github.com/FelisCatus/SwitchyOmega/wiki/GFWList.bak" rel="nofollow" target="_blank">
     https://github.com/FelisCatus/SwitchyOmega/wiki/GFWList.bak 
</a>
</p>

<div class="post-ad">
    
    
    
</div>



<img src="https://i.loli.net/2018/01/28/5a6dc9a4f41ff.png" alt="在线恢复">


<p>选择 GFWed，设置代理端口为 2333，然后点击 应用选项</p>


<img src="https://i.loli.net/2018/01/28/5a6dc9a4e8a6d.png" alt="设置代理">


<p>然后右上角找到 Proxy SwitchyOmega 图标，点击它，再点击自动切换</p>


<img src="https://i.loli.net/2018/01/28/5a6dc9a4ebd18.png" alt="切换代理">


<p>OK，此时你已经自由了，赶紧打开 <a href="https://www.google.com/ncr" rel="nofollow" target="_blank">
     Google  
</a>
 找部十八减的大电影喵喵吧。哈哈</p>

<h2 id="结束">结束</h2>

<p>实际上，没有特别的需求根本不需要安装 Proxy SwitchyOmega ，直接使用 V2RayN 打开 启动系统代理 就可以自动翻出去了<br />
如果你有使用 Proxy SwitchyOmega<br />
V2RayN 设置的那个 本地鉴听端口 可以随便修改的，如果你修改了，Proxy SwitchyOmega 那边也要设置成对应的端口就行<br />
啊~生活如此美好</p>

<p><img src="https://affpass.com/ga?ga=v2ray&amp;dt=github.wiki.8&amp;dr=&amp;ul=zh-CN&amp;sd=24-bit&amp;sr=&amp;vp=&amp;z=0&amp;dl=/github/8" alt="" /></p>
</div>