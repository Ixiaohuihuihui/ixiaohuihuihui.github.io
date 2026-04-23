---
layout: page-no-nav
title: "课题组WorkFlow"
permalink: /workflow/
author_profile: false
---

<style>
.workflow-wrapper {
    display: flex;
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem 2rem 2rem 0;
    gap: 2rem;
}

.workflow-sidebar {
    width: 220px;
    flex-shrink: 0;
    position: sticky;
    top: 2rem;
    height: fit-content;
    padding-left: 1rem;
}

.workflow-nav {
    background: #f8f9fa;
    border-radius: 12px;
    padding: 0.6rem 0;
}

.workflow-nav-item {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0.85rem 1.2rem;
    color: #555;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s;
    border-left: 3px solid transparent;
    font-size: 0.95rem;
}

.workflow-nav-item:hover {
    background: #e8f0ff;
    color: #00369f;
}

.workflow-nav-item.active {
    background: linear-gradient(90deg, #e8f0ff 0%, #f0f5ff 100%);
    color: #00369f;
    border-left-color: #00369f;
    font-weight: 600;
}

.workflow-nav-item.has-sub {
    justify-content: space-between;
}

.nav-arrow {
    font-size: 0.7rem;
    transition: transform 0.2s;
    margin-left: 0.5rem;
}

.nav-arrow.expanded {
    transform: rotate(180deg);
}

.workflow-sub-nav {
    display: none;
    padding-left: 1.5rem;
    background: #f0f4f8;
}

.workflow-sub-nav.show {
    display: block;
}

.workflow-sub-item {
    display: block;
    padding: 0.7rem 1.2rem;
    color: #666;
    text-decoration: none;
    cursor: pointer;
    font-size: 0.9rem;
    transition: all 0.2s;
    border-left: 2px solid transparent;
}

.workflow-sub-item:hover {
    color: #00369f;
    background: #e8f0ff;
}

.workflow-sub-item.active {
    color: #00369f;
    border-left-color: #00369f;
    font-weight: 600;
}

.workflow-content {
    flex: 1;
    min-width: 0;
}

.workflow-section {
    background: white;
    border-radius: 12px;
    padding: 2rem;
    margin-bottom: 1.5rem;
    border: 1px solid #e8e8e8;
    box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}

.workflow-section h2 {
    color: #00369f;
    font-size: 1.4rem;
    margin-bottom: 1rem;
    padding-bottom: 0.8rem;
    border-bottom: 2px solid #f5f5f5;
}

.workflow-section p {
    color: #666;
    line-height: 1.8;
}

.back-link {
    display: inline-block;
    margin-bottom: 1.5rem;
    color: #00369f;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.95rem;
}

.back-link:hover {
    text-decoration: underline;
}

.workflow-note {
    background: linear-gradient(135deg, #fff9e6 0%, #fff8dc 100%);
    border: 1px solid #ffd966;
    border-radius: 12px;
    padding: 1.5rem 2rem;
    margin-top: 2rem;
    text-align: center;
}

.workflow-note p {
    margin: 0;
    color: #856404;
    font-size: 1rem;
    line-height: 1.6;
}

.workflow-note-icon {
    font-size: 1.8rem;
    display: block;
    margin-bottom: 0.5rem;
}
</style>

<div class="workflow-wrapper">
<nav class="workflow-sidebar">
<div class="workflow-nav">
<div class="workflow-nav-item" onclick="toggleSection('section-1', this)">📌 流程规范</div>

<div class="workflow-nav-item" onclick="toggleSection('section-2', this)">🖥️ 服务器账号领取</div>

<div class="workflow-nav-item has-sub" onclick="toggleSubNav(this, 'sub-3')">📦 软件安装<span class="nav-arrow">▶</span></div>
<div id="sub-3" class="workflow-sub-nav">
<div class="workflow-sub-item" onclick="showSection('section-3-1', this)">MobaXterm</div>
<div class="workflow-sub-item" onclick="showSection('section-3-2', this)">Tmux</div>
<div class="workflow-sub-item" onclick="showSection('section-3-3', this)">Oh-my-zsh</div>
<div class="workflow-sub-item" onclick="showSection('section-3-4', this)">PyCharm</div>
<div class="workflow-sub-item" onclick="showSection('section-3-5', this)">Anaconda</div>
<div class="workflow-sub-item" onclick="showSection('section-3-6', this)">Cursor</div>
<div class="workflow-sub-item" onclick="showSection('section-3-7', this)">Claude Code</div>
<div class="workflow-sub-item" onclick="showSection('section-3-8', this)">好用软件推荐</div>
</div>

<div class="workflow-nav-item has-sub" onclick="toggleSubNav(this, 'sub-4')">📝 论文写作<span class="nav-arrow">▶</span></div>
<div id="sub-4" class="workflow-sub-nav">
<div class="workflow-sub-item" onclick="showSection('section-4-1', this)">想法诞生</div>
<div class="workflow-sub-item" onclick="showSection('section-4-2', this)">实验对比</div>
<div class="workflow-sub-item" onclick="showSection('section-4-3', this)">中文稿件</div>
<div class="workflow-sub-item" onclick="showSection('section-4-4', this)">Overleaf</div>
</div>

<div class="workflow-nav-item has-sub" onclick="toggleSubNav(this, 'sub-5')">💡 写论文提示词<span class="nav-arrow">▶</span></div>
<div id="sub-5" class="workflow-sub-nav">
<div class="workflow-sub-item" onclick="showSection('section-5-1', this)">CVPR等顶会风格的Prompt</div>
<div class="workflow-sub-item" onclick="showSection('section-5-2', this)">TPAMI等期刊论文的Prompt</div>
<div class="workflow-sub-item" onclick="showSection('section-5-3', this)">画框架图的Prompt</div>
</div>

<div class="workflow-nav-item has-sub" onclick="toggleSubNav(this, 'sub-6')">🤖 AI审稿专家的Prompt<span class="nav-arrow">▶</span></div>
<div id="sub-6" class="workflow-sub-nav">
<div class="workflow-sub-item" onclick="showSection('section-6-1', this)">AI顶会审稿专家</div>
<div class="workflow-sub-item" onclick="showSection('section-6-2', this)">AI顶刊审稿专家</div>
</div>

<div class="workflow-nav-item has-sub" onclick="toggleSubNav(this, 'sub-7')">📨 投稿管理<span class="nav-arrow">▶</span></div>
<div id="sub-7" class="workflow-sub-nav">
<div class="workflow-sub-item" onclick="showSection('section-7-1', this)">投稿流程</div>
</div>

<div class="workflow-nav-item" onclick="toggleSection('section-8', this)">🎁 奖励政策</div>
</div>
</nav>

<div class="workflow-content">
<a href="/#-ktzwf" class="back-link">← 返回</a>

<div id="section-1" class="workflow-section">
<h2>📌 流程规范</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">本文档旨在为课题组建立一套开源、共享、智能、规则明确的工作流程。</p>
<ul style="margin-top:1.5rem;font-size:1rem;color:#555;line-height:1.8;">
<li style="margin-bottom:0.5rem;"><strong>适用对象：</strong> 所有课题组成员</li>
<li style="margin-bottom:0.5rem;"><strong>更新机制：</strong> 核心流程将跟随平台版本迭代实时更新。</li>
</ul>
</div>

<div id="section-2" class="workflow-section" style="display:none;">
<h2>🖥️ 服务器账号领取</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">本页面用于规范课题组服务器账号的申请、开通、使用与回收流程，帮助新成员快速上手，并保障科研计算资源安全、有序、可追踪地使用。</p>
<ul style="margin-top:1rem;font-size:1rem;color:#555;line-height:1.8;">
<li style="margin-bottom:0.5rem;"><strong>适用对象：</strong> 所有课题组成员</li>
<li style="margin-bottom:0.5rem;"><strong>管理原则：</strong> 实名申请、一人一号、按需开通、统一管理</li>
</ul>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、联系人</h3>
<ul style="font-size:1rem;color:#555;line-height:1.8;">
<li>服务器管理员：向健林</li>
<li>联系方式（WX）：x1114374366</li>
</ul>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、向管理员提交申请</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">请填写服务器账号申请信息，发送给管理员，内容包括：</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>姓名</li>
<li>年级</li>
<li>导师姓名</li>
<li>研究方向 / 所属课题</li>
<li>使用目的</li>
<li>所需显卡个数，需要占用多少显存</li>
</ul>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">三、账号开通</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">审核通过后，管理员将完成账号创建，并告知：</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>登录IP地址</li>
<li>登录方式</li>
<li>初始账号信息</li>
<li>首次登录注意事项</li>
<li>相关目录与环境说明</li>
</ul>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">四、使用规范</h3>
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">账号安全</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>不得转借账号</li>
<li>不得泄露密码</li>
<li>发现异常登录请及时联系管理员</li>
</ul>
<p style="font-size:1rem;color:#555;font-weight:600;margin-top:1rem;margin-bottom:0.5rem;">资源使用</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>共享资源请按需使用</li>
<li>禁止无意义占卡、空跑、重复提交异常任务</li>
<li>任务结束后及时释放资源</li>
</ul>
<p style="font-size:1rem;color:#555;font-weight:600;margin-top:1rem;margin-bottom:0.5rem;">数据与环境</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>个人数据存放在个人目录</li>
<li>公共资源存放在指定共享位置</li>
<li>不覆盖公共文件</li>
<li>不擅自修改公共环境和系统配置</li>
</ul>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">五、账号回收</h3>
<p style="font-size:1rem;color:#555;line-height:1.8;">以下情形将触发账号回收：</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>毕业离组</li>
<li>违反使用规定</li>
</ul>
<p style="font-size:1rem;color:#555;line-height:1.8;margin-top:1rem;">回收前请自行完成数据整理与必要备份，课题组仅保留管理所需信息，不对个人未备份数据负责。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">六、常见问题</h3>
<ul style="font-size:1rem;color:#555;line-height:1.9;padding-left:1.5rem;">
<li><strong>忘记密码怎么办？</strong> 联系管理员重置。</li>
<li><strong>资源不够怎么办？</strong> 联系管理员说明任务需求与预计时长，统一协调。</li>
<li><strong>可以自己安装软件吗？</strong> 个人环境可以，公共环境或系统级变更需提前沟通。</li>
</ul>
</div>

<div id="section-3-1" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - MobaXterm</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">MobaXterm 是一款集成化远程连接工具，支持 SSH、SFTP、X11 等协议，广泛用于连接服务器（如实验室 GPU 服务器）。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、下载</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">下载地址：<a href="https://mobaxterm.mobatek.net/download-home-edition.html" target="_blank">https://mobaxterm.mobatek.net/download-home-edition.html</a></p>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">下载解压后进行安装：</p>
<img src="/images-wf/MobaXtem1.png" alt="MobaXterm安装步骤" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击next，修改路径后点击next，install即可</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、连接服务器</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">申请服务器账号成功后可以在mobaxterm登录</p>
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">步骤：打开mobaxterm</p>
<img src="/images-wf/MobaXtem2.png" alt="步骤1" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击左上角Session</p>
<img src="/images-wf/MobaXtem3.png" alt="步骤2" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">在这里填写自己的服务器地址和用户名，其中Remote host为服务器ip，Specify username为用户名。例如</p>
<img src="/images-wf/MobaXtem4.png" alt="步骤3" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击ok</p>
<img src="/images-wf/MobaXtem5.png" alt="步骤4" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击Accept</p>
<img src="/images-wf/MobaXtem6.png" alt="步骤5" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;">输入你的密码后回车（注意，这里界面不会显示你的输入）</p>
</div>

<div id="section-3-2" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Tmux</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">tmux 是终端复用工具，可以在服务器上保持会话不中断（即使断网）。即一般都在tmux窗口进行实验。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、安装</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">这里是一个不需要管理员权限的安装方法</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">下载地址（需要外网）：<a href="https://github.com/pythops/tmux-linux-binary/releases" target="_blank">https://github.com/pythops/tmux-linux-binary/releases</a></p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>选择 tmux-linux-x86_64版本（取决于服务器cpu架构）</li>
<li>下载后上传服务器</li>
<li>再在命令行输入指令：</li>
</ul>
<p style="font-size:1rem;color:#555;margin-top:0.5rem;margin-bottom:0.3rem;">mkdir -p ~/.local/bin</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.3rem;">mv tmux-linux-x86_64 ~/.local/bin/tmux（看tmux-linux-x86_64具体目录）</p>
<p style="font-size:1rem;color:#555;">即可使用</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、使用指令</h3>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>tmux new -s session_name &nbsp;&nbsp;# 新建会话</li>
<li>tmux attach -t session_name &nbsp;# 重新连接</li>
<li>tmux ls &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;# 查看会话</li>
<li>tmux kill-session -t name &nbsp;# 关闭会话</li>
</ul>
<p style="font-size:1rem;color:#555;margin-top:1rem;">更多指令：<a href="https://zhuanlan.zhihu.com/p/90464490" target="_blank">https://zhuanlan.zhihu.com/p/90464490</a></p>
</div>

<div id="section-3-3" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Oh-my-zsh</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-4" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - PyCharm</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">PyCharm 是 Python 集成开发环境（IDE），适合本地代码开发与调试。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、下载</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">pycharm下载地址：<a href="https://www.jetbrains.com/pycharm/download/?section=windows" target="_blank">https://www.jetbrains.com/pycharm/download/?section=windows</a></p>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">下载后点击安装包点击下一步：选择你安装的路径，这里我设置了D盘</p>
<img src="/images-wf/Pycharm1.png" alt="安装步骤1" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击下一步：这里全部勾选上</p>
<img src="/images-wf/Pycharm2.png" alt="安装步骤2" style="border-radius:8px;margin-bottom:1rem;">
<img src="/images-wf/Pycharm3.png" alt="安装步骤3" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">直接点击安装，等待一小会</p>
<img src="/images-wf/Pycharm4.png" alt="安装步骤4" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">点击完成即可</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">因为pycharm专业版需要付费使用，但是可以使用咱们学校给我们注册的邮箱来获得免费的一年使用权，过期了可以续订，具体流程参考如下：<a href="https://zhuanlan.zhihu.com/p/555346721" target="_blank">https://zhuanlan.zhihu.com/p/555346721</a></p>
<p style="font-size:1rem;color:#555;">认证完后用你的用户名和密码登录即可正常使用pycharm</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、Pycharm远程连接服务器账号</h3>
<p style="font-size:1rem;color:#555;font-style:italic;margin-bottom:1rem;">说明：这个操作可以同步主机和服务器的文件，即操作成功后可直接在pycharm改代码以及用终端跑实验（前提是在服务器上安装好环境）</p>

<h4 style="color:#555;font-size:1rem;margin-top:1.2rem;margin-bottom:0.8rem;">2.1 配置python解释器</h4>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">首先用pycharm打开一个项目点击左上角菜单，点击设置</p>
<img src="/images-wf/Pycharm5.png" alt="配置步骤1" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击左上角菜单，点击设置</p>
<img src="/images-wf/Pycharm6.png" alt="配置步骤2" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">选择python解释器：</p>
<img src="/images-wf/Pycharm7.png" alt="配置步骤3" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">选择添加解释器，选择on ssh</p>
<img src="/images-wf/Pycharm8.png" alt="配置步骤4" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">选择New</p>
<img src="/images-wf/Pycharm9.png" alt="配置步骤5" style="border-radius:8px;margin-bottom:1rem;">
<img src="/images-wf/Pycharm10.png" alt="配置步骤6" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">这里Host填写服务器ip，Username填写你的用户名，点击Next，填写密码</p>
<img src="/images-wf/Pycharm11.png" alt="配置步骤7" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击两次next后，选择环境以及同步的文件（注意，这里的同步文件是需要提前把这个项目文件传到服务器上去的，直接拖拽文件至服务器目录即可上传）</p>
<img src="/images-wf/Pycharm12.png" alt="配置步骤8" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">选择你的虚拟环境，需要同步的文件夹</p>
<img src="/images-wf/Pycharm13.png" alt="配置步骤9" style="border-radius:8px;margin-bottom:1rem;">
<img src="/images-wf/Pycharm14.png" alt="配置步骤10" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击右边文件图标，左边是你的本地文件，右边是服务器文件</p>
<img src="/images-wf/Pycharm15.png" alt="配置步骤11" style="border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">选择好后点击OK，点击Create，再点击ok</p>

<h4 style="color:#555;font-size:1rem;margin-top:1.2rem;margin-bottom:0.8rem;">三、代码同步</h4>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击菜单→Tools→Deployment→Options，选择CTRL+S保存同步文件</p>
<img src="/images-wf/Pycharm16.png" alt="代码同步" style="border-radius:8px;margin-bottom:1rem;">
</div>

<div id="section-3-5" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Anaconda</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">Anaconda 是 Python 环境管理工具，用于创建独立虚拟环境，避免依赖冲突。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、下载</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">一般我们在 MobaXterm 里使用 Anaconda 管理我们之后项目的环境，在 MobaXterm 里下载 Anaconda 参考如下：</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;"><a href="https://zhuanlan.zhihu.com/p/562859394" target="_blank">https://zhuanlan.zhihu.com/p/562859394</a></p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、虚拟环境的创建</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">一般一个项目需要创建一个虚拟环境，在命令行输入指令：</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.3rem;padding-left:1rem;">conda create --name myenv python=3.8</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">myenv 改为自己的环境名，python 版本自行选择更改。</p>
<img src="/images-wf/Anaconda1.png" alt="创建环境" style="border-radius:8px;margin-bottom:1rem;">
<img src="/images-wf/Anaconda2.png" alt="创建环境" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">输入 y 回车。</p>
<img src="/images-wf/Anaconda3.png" alt="确认创建" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">这样我们就创建好一个名叫 demo 的环境了。</p>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">怎样查看你创建的环境：输入 conda env list。</p>
<img src="/images-wf/Anaconda4.png" alt="查看环境" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">激活环境：conda activate demo。</p>
<img src="/images-wf/Anaconda5.png" alt="激活环境" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">这样我们就进入创建的 demo 环境了。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">三、PyTorch的下载</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">PyTorch 官网：<a href="https://pytorch.org/" target="_blank">https://pytorch.org/</a></p>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">根据自己项目要求和实验室服务器版本选择 torch 和 CUDA 版本，以前的 torch 版本点击左下角进行选择。选择好后复制粘贴命令回车即可。</p>
<img src="/images-wf/Anaconda6.png" alt="PyTorch下载" style="border-radius:8px;margin-bottom:1rem;">
</div>

<div id="section-3-6" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Cursor</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">Cursor 是基于 AI 的代码编辑器，类似 VS Code，但深度集成 AI 辅助编程。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">一、下载</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">官网下载最新版本：<a href="https://cursor.com/cn" target="_blank">https://cursor.com/cn</a></p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、使用</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">VPN设置：选择全局模式+TUN模式（有的VPN是全局模式+虚拟网卡），地区选台湾/新加坡/日本（香港不能），延迟最低的那个。</p>
<img src="/images-wf/cursor1.png" alt="VPN设置" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;margin-top:1rem;">启动 Cursor，没充值的情况下只能使用 Auto 模式，就是它自动给你分配模型。充值了（谷歌账号登录+支付宝支付）可以在设置里选择模型。</p>
<img src="/images-wf/cursor2.png" alt="模型选择" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">带脑子图案的是有推理/思考，效果更好但是费用更高。</p>
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">推荐模型：</p>
<ul style="font-size:1rem;color:#555;line-height:1.8;padding-left:1.5rem;">
<li>Opus 4.5 - 最好用但是很贵</li>
<li>GPT-5.2 Codex - 性价比最高</li>
</ul>
<img src="/images-wf/cursor3.png" alt="模型说明" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;margin-top:1rem;">对话框输入要求，使用 Agent 模式。</p>
<img src="/images-wf/cursor4.png" alt="Agent模式" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;margin-top:1rem;">每次打开一个项目，如果代码文件不多，建议在设置中打开 Code Index 功能，回答的效果更好。</p>
<img src="/images-wf/cursor5.png" alt="Code Index设置" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;margin-top:1rem;">Cursor 是按使用的 Token 计费的，输入的要求越多，改动的代码越多，用的 Token 就越多，可在此处查看。</p>
<img src="/images-wf/cursor6.png" alt="Token查看" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;margin-top:1rem;">如果对改的代码不满意，点击此处回档。</p>
<img src="/images-wf/cursor7.png" alt="回档" style="border-radius:8px;margin-bottom:1rem;">
<img src="/images-wf/cursor8.png" alt="回档" style="border-radius:8px;margin-bottom:1rem;">
</div>

<div id="section-3-7" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Claude Code</h2>
<h3 style="color:#00369f;font-size:1.1rem;margin-bottom:1rem;">说明</h3>
<p style="font-size:1.05rem;line-height:1.9;">Claude Code 是基于 Claude 模型的编程辅助工具，擅长长代码理解与逻辑分析。</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">使用流程</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">这里在 Cursor 举例。</p>
<img src="/images-wf/claudecode1.png" alt="Claude Code使用" style="border-radius:8px;margin-bottom:1rem;">

<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">在模型里面选择 Opus 或 Codex 都可以。</p>
</div>

<div id="section-3-8" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - 好用软件推荐</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-4-1" class="workflow-section" style="display:none;">
<h2>📝 论文写作 - 想法诞生</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-4-2" class="workflow-section" style="display:none;">
<h2>📝 论文写作 - 实验对比</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-4-3" class="workflow-section" style="display:none;">
<h2>📝 论文写作 - 中文稿件</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-4-4" class="workflow-section" style="display:none;">
<h2>📝 论文写作 - Overleaf</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-5-1" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词 - CVPR等顶会风格</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-5-2" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词 - TPAMI等期刊论文</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-5-3" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词 - 画框架图的Prompt</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-6-1" class="workflow-section" style="display:none;">
<h2>🤖 AI审稿专家 - AI顶会审稿专家</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-6-2" class="workflow-section" style="display:none;">
<h2>🤖 AI审稿专家 - AI顶刊审稿专家</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-7-1" class="workflow-section" style="display:none;">
<h2>📨 投稿管理 - 投稿流程</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-8" class="workflow-section" style="display:none;">
<h2>🎁 奖励政策</h2>
<p>（请在此处填写内容）</p>
</div>

</div>
</div>

<div class="workflow-note">
<span class="workflow-note-icon">💡</span>
<p><b>温馨提示：</b>遇到任何问题欢迎随时与导师或师兄师姐沟通，我们是一个大家庭！</p>
</div>

<script>
function showSection(id, element) {
    document.querySelectorAll('.workflow-section').forEach(function(section) {
        section.style.display = 'none';
    });
    document.getElementById(id).style.display = 'block';

    document.querySelectorAll('.workflow-nav-item, .workflow-sub-item').forEach(function(item) {
        item.classList.remove('active');
    });
    element.classList.add('active');
}

function toggleSection(id, element) {
    document.querySelectorAll('.workflow-section').forEach(function(section) {
        section.style.display = 'none';
    });
    document.getElementById(id).style.display = 'block';

    document.querySelectorAll('.workflow-nav-item').forEach(function(item) {
        item.classList.remove('active');
    });
    element.classList.add('active');

    document.querySelectorAll('.workflow-sub-nav').forEach(function(sub) {
        sub.classList.remove('show');
    });
    document.querySelectorAll('.nav-arrow').forEach(function(arrow) {
        arrow.classList.remove('expanded');
        if (arrow.textContent === '▼') {
            arrow.textContent = '▶';
        }
    });
}

function toggleSubNav(element, subNavId) {
    var subNav = document.getElementById(subNavId);
    var arrow = element.querySelector('.nav-arrow');
    var firstSubItem = subNav.querySelector('.workflow-sub-item');

    // Show the first sub-item's section
    if (firstSubItem) {
        var firstSectionId = firstSubItem.getAttribute('onclick').match(/'([^']+)'/)[1];
        showSection(firstSectionId, firstSubItem);
    }

    if (subNav.classList.contains('show')) {
        subNav.classList.remove('show');
        if (arrow) {
            arrow.textContent = '▶';
            arrow.classList.remove('expanded');
        }
    } else {
        subNav.classList.add('show');
        if (arrow) {
            arrow.textContent = '▼';
            arrow.classList.add('expanded');
        }
    }

    document.querySelectorAll('.workflow-nav-item').forEach(function(item) {
        item.classList.remove('active');
    });
    element.classList.add('active');
}

document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('.workflow-nav-item').click();
});
</script>