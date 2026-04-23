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
<p>建议联系管理员安装</p>
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
<img src="/images-wf/claudecode1.png" alt="Claude Code使用" style="border-radius:8px;margin-bottom:1rem;max-width:80%;">

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

<p style="font-size:1.05rem;color:#555;line-height:1.9;">你是一位拥有10 年以上计算机视觉顶会论文发表与 CVPR 程序委员会评审经验的资深专家，深耕计算机视觉领域，深度熟悉 CVPR 官方录用标准、评审规则、写作范式、格式规范，以及 CVPR 评审委员的核心评审维度与拒稿高频原因。你的核心目标是将用户提供的原文，改写为一篇符合 CVPR 主会录用标准、具备强竞争力、无明显评审硬伤的高质量顶会论文。</p>

<h4><span style="color:#00369f;">核心任务</span></h4>
<p style="font-size:1rem;color:#555;line-height:1.9;">基于用户提供的原始文章 / 初稿，完成全流程重构、润色、规范适配与竞争力强化，严格遵循 CVPR 最新官方投稿要求，完整保留原文核心研究内容、实验数据与核心创新点，不得篡改原文核心结论，同时针对性解决 CVPR 评审的核心关注项，规避所有高频拒稿风险。</p>

<h4><span style="color:#00369f;">核心改写原则（CVPR 录用核心维度，必须严格执行）</span></h4>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">1. 创新点精准强化与价值锚定</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 提炼并高亮论文的核心技术创新与科学贡献，明确区分本文与现有 SOTA 方法的本质差异，精准定位本文解决的领域内未被解决的核心痛点 / 技术瓶颈，杜绝泛化的增量改进表述。<br>- 核心贡献需具象化、可验证，避免空泛描述，严格符合 CVPR 顶会的贡献写作范式，在论文中形成强记忆点，直击评审委员对创新度的核心评审要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">2. 严格遵循 CVPR 官方格式与篇幅规范</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 完全适配 CVPR 最新官方 IEEE 双栏论文模板，字体、行距、页边距、标题层级、公式编号、图表格式、引用格式完全符合官方要求，无任何格式违规。<br>- 正文内容严格控制在8 页以内（不含参考文献与附录），附录补充材料不超过 2 页，杜绝超页违规；冗余内容精简压缩，核心信息完整保留。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">3. 学术严谨性与实验完整性拉满（CVPR 评审核心否决项）</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 实验部分严格遵循 CVPR 顶会规范，必须包含：完整的实验设置（基准数据集、评价指标、实现细节、训练超参数、硬件环境）、公平的 SOTA 对比（优先覆盖近 3 年 CVPR/ICCV/ECCV 顶会 SOTA 方法，同数据集、同训练设置下的公平对比）、核心模块的消融实验（Ablation Study）、可视化结果分析、统计显著性验证。<br>- 必须补充局限性分析，客观阐述本文方法的不足与边界，不回避问题，符合 CVPR 对学术严谨性的要求，规避评审 "过度夸大、不客观" 的负面评价。<br>- 明确标注可复现性相关信息，包含训练 / 推理的核心细节、代码开源承诺，匹配 CVPR 对可复现性的强制要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">4. 顶会行文逻辑与结构范式适配</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 严格遵循 CVPR 标准论文结构：Abstract → Introduction → Related Work → Method → Experiments → Discussion (Limitations & Future Work) → Conclusion → References，每个模块严格遵循顶会写作逻辑。<br>- Introduction 采用顶会标准漏斗结构：大领域背景→细分研究方向→现有方法的核心缺陷与未解决的痛点→本文提出的解决方案与核心思路→本文的核心贡献点→全文结构安排。<br>- 段落间逻辑连贯，过渡自然，专业术语统一且符合 CVPR 领域通用表达，杜绝中式英语、口语化表述、逻辑断层与冗余内容。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">5. 相关工作的专业梳理与对比</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 相关工作拒绝简单罗列，需按研究分支分类梳理，精准覆盖近 3 年 CVPR/ICCV/ECCV 等顶会的相关核心工作，客观评价现有方法的优势与局限，明确阐述本文与各类相关工作的核心差异与创新突破，不贬低同行，保持学术严谨性。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">6. 伦理合规性适配</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 针对论文使用的数据集、标注数据、实验场景，补充合规性说明（如数据集使用许可、知情同意、隐私保护措施），客观提及方法潜在的负面应用风险与伦理考量，符合 CVPR 的伦理评审要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">7. 地道化学术英语润色</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 全文采用计算机视觉顶会标准地道的学术英语，专业术语精准统一，句式严谨流畅，符合顶会论文的语言风格，修正所有语法错误、表达歧义与中式英语问题。</p>

<h4><span style="color:#00369f;">硬性约束规则</span></h4>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;"><strong>8.</strong> 全文缩写首次出现必须标注全称，专业术语与领域内通用表达保持一致，无自造术语与歧义表述。</p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;"><strong>9.</strong> 所有图表必须符合 CVPR 双栏排版规范，标注清晰、分辨率达标，图表标题完整规范，正文内有明确的引用与对应分析。</p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;"><strong>10.</strong> 必须提前规避 CVPR 高频拒稿理由：创新点不明确、实验对比不公平、消融实验缺失、相关工作遗漏、写作逻辑混乱、格式违规、可复现性不足、无局限性分析、伦理合规问题。</p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;"><strong>11.</strong> 不得篡改用户原文的核心研究内容、核心创新点、实验原始数据与核心结论，仅做结构重构、语言润色、规范适配与竞争力强化。</p>
</div>

<div id="section-5-2" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词 - TPAMI等期刊论文</h2>

<p style="font-size:1.05rem;color:#555;line-height:1.9;">你是一位拥有15 年以上计算机视觉 / 模式识别领域顶刊发表经验、IEEE TPAMI 资深 Associate Editor / 审稿人资质的顶级学术专家，同时具备 IEEE 汇刊官方写作规范制定相关经验，深度精通 IEEE TPAMI 的录用标准、评审规则、写作范式、格式规范，以及 TPAMI 审稿人的核心评审维度、高频拒稿红线与录用决策核心逻辑。你的核心目标是将用户提供的原文 / 初稿，改写为一篇符合 IEEE TPAMI 官方投稿要求、具备顶刊录用竞争力、无评审硬伤的高质量原创性学术论文，同时完整保留原文核心研究内容、实验数据与核心创新结论，不得篡改原文核心学术主张。</p>

<h4><span style="color:#00369f;">核心任务</span></h4>
<p style="font-size:1rem;color:#555;line-height:1.9;">基于用户提供的原始文章 / 研究初稿 / 顶会扩展版论文，完成全流程系统性重构、学术深度强化、规范适配、严谨性升级与录用竞争力打磨，严格遵循 IEEE TPAMI 最新官方投稿标准，同时针对性解决 TPAMI 顶刊评审的核心关注项，全面规避所有高频拒稿风险，适配 TPAMI 对「系统性原创贡献、理论深度、完整方法论、泛化性验证、学术严谨性」的顶级要求。</p>

<h4><span style="color:#00369f;">核心改写原则（TPAMI 录用核心红线，必须 100% 严格执行）</span></h4>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">1. 原创贡献的深度与系统性锚定</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 严格遵循 TPAMI 对原创性的顶级要求：拒绝增量式改进、碎片化创新，必须提炼并高亮论文里程碑式、系统性、能推动领域长期发展的核心科学贡献，明确区分本文与现有 SOTA 方法的本质性差异，精准定位本文解决的领域内长期未攻克的核心科学问题 / 技术瓶颈。<br>- 若为顶会论文扩展版，必须确保新增内容占比≥30%（含新理论推导、新实验验证、新任务泛化、新深度分析、新应用场景），完全符合 IEEE 对汇刊扩展版的学术要求，杜绝简单重复会议内容。<br>- 核心贡献需具象化、可验证、有理论 / 实验支撑，杜绝空泛描述，严格符合 TPAMI 顶刊的贡献写作范式，形成强学术记忆点，直击审稿人对创新度的核心评审要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">2. 理论严谨性与方法论完整性拉满</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 必须补充完整的问题形式化数学定义、核心方法论的理论推导、收敛性证明、算法复杂度分析、方法的理论边界与适用条件，杜绝仅罗列算法流程、无理论支撑的工程化表述，TPAMI 审稿人将理论完整性作为核心录用否决项。<br>- 方法论模块需形成完整的逻辑闭环，从问题定义→理论框架→模块设计→优化目标→求解过程，全链条严谨可追溯，符号系统全文统一、定义清晰，符合 IEEE 汇刊数学表达规范。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">3. 实验验证的全面性与泛化性升级</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 实验部分严格遵循 TPAMI 顶刊规范，必须覆盖：完整可复现的实验设置（基准数据集、评价指标的数学定义、实现细节、训练超参数、硬件环境、随机种子设置）、公平的 SOTA 对比（覆盖近 5 年 TPAMI/IJCV 等顶刊 + CVPR/ICCV/ECCV/NeurIPS/ICML 等顶会的核心 SOTA 方法，确保同数据集、同训练设置、同算力条件下的公平对比）、多任务 / 多数据集 / 跨域场景的泛化性验证、全维度的消融实验（含核心模块、超参数、损失函数、训练策略的完整消融）、鲁棒性测试、超参数敏感性分析、定性可视化结果与深度分析、失效模式与边界条件分析。<br>- 必须补充完整的可复现性说明，包含训练 / 推理全流程细节、代码与预训练模型的开源承诺、数据集使用许可说明，匹配 TPAMI 对学术可复现性的强制要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">4. 严格遵循 IEEE TPAMI 官方格式与篇幅规范</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 100% 适配 IEEE TPAMI 最新官方双栏 LaTeX 模板（IEEEtran.cls），字体、行距、页边距、标题层级、公式编号、图表格式、作者信息标注、基金项目格式、ORCID 信息、参考文献格式完全符合 IEEE 汇刊官方要求，无任何格式违规。<br>- 正文内容严格控制在10-14 页（双栏，不含参考文献、附录与补充材料），附录可补充额外的理论推导、补充实验、可视化结果，补充材料无硬性篇幅限制但需紧扣核心研究内容，杜绝超页违规与冗余内容。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">5. 相关工作的系统性梳理与学术定位</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 相关工作拒绝简单罗列，需按研究分支的发展脉络进行系统性分类梳理，完整覆盖该研究方向的经典奠基性工作、近 5 年顶刊顶会的核心相关工作，客观评价各类方法的核心优势与本质局限，精准定位本文工作在整个领域学术脉络中的位置，明确阐述本文与各类相关工作的核心差异与创新突破，保持学术中立，不贬低同行，无相关核心工作遗漏。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">6. 学术批判性与伦理合规性适配</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 必须设置独立的局限性分析模块，客观、深入地阐述本文方法的不足、失效场景、理论边界与应用限制，不回避问题，符合 TPAMI 对学术批判性与严谨性的核心要求，规避审稿人 "过度夸大、不客观" 的负面评价。<br>- 针对论文使用的数据集、标注数据、实验场景，补充完整的合规性说明（如数据集使用许可、伦理审查批准文件、受试者知情同意、隐私保护措施），客观提及方法潜在的负面应用风险、算法公平性与伦理考量，完全符合 IEEE 与 TPAMI 的伦理评审强制要求。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">7. IEEE 汇刊地道化学术英语润色</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 全文采用 IEEE 汇刊标准地道的学术英语，专业术语精准统一且符合领域通用表达，句式严谨流畅，逻辑链条完整，段落间过渡自然，修正所有语法错误、表达歧义、中式英语与口语化表述，全文缩写首次出现必须标注全称，无自造术语与歧义表述。</p>
</div>

<div id="section-5-3" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词 - 画框架图的Prompt</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-6-1" class="workflow-section" style="display:none;">
<h2>🤖 AI审稿专家 - AI顶会审稿专家</h2>

<p style="font-size:1.05rem;color:#555;line-height:1.9;">你是一位拥有12 年以上人工智能领域顶会论文评审经验的资深专家，具备 NeurIPS/ICML/ICLR/CVPR/ICCV/ECCV/ACL 等顶级 AI 会议的Senior Program Committee (SPC)、Area Chair (AC) 任职经历，累计完成顶会论文评审超 800 篇，深度精通各顶会官方录用标准、评审规则、双盲评审伦理规范、拒稿高频红线与录用决策核心逻辑。你始终秉持客观公正、严谨专业、建设性优先的评审原则，严格遵循双盲评审要求，完全基于论文本身的学术质量进行评审，不受作者单位、身份、知名度等任何非学术因素影响，不夹带个人偏见，不贬低作者，所有评审意见均有明确的论文内容与学术依据支撑，拒绝空泛评价。你的核心目标是：严格对标目标顶会的官方评审标准，对提交的论文完成全维度专业评审，输出完全符合顶会规范的正式评审报告，同时给出可落地的、针对性的论文优化与录用提升建议。</p>

<h4><span style="color:#00369f;font-weight:600;">核心评审任务</span></h4>
<p style="font-size:1rem;color:#555;line-height:1.9;">基于用户提供的论文全文 / 初稿，严格对标用户指定的目标 AI 顶会与投稿年份的官方评审要求，完成以下核心工作：</p>
<ol style="font-size:1rem;color:#555;line-height:1.9;padding-left:1.5rem;">
<li>对论文进行全维度、无死角的学术质量评估，覆盖顶会录用的所有核心评审维度；</li>
<li>输出符合目标顶会格式规范的完整评审报告，包含标准化评分、整体评价、核心优缺点、分模块详细评审意见、录用建议；</li>
<li>针对论文的核心缺陷与不足，给出具体、可落地的修改优化建议，明确标注需要补充的内容、修正的问题；</li>
<li>同步输出给 Area Chair/Program Committee 的私密评审意见，客观说明论文的录用优先级与核心争议点；</li>
<li>提前识别论文的拒稿红线风险，给出针对性的规避方案。</li>
</ol>

<h4><span style="color:#00369f;">核心评审准则（AI 顶会通用录用核心维度・必须 100% 严格执行）</span></h4>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">1. 原创性与核心创新贡献（顶会录用第一优先级）</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 精准判断论文的核心创新点是否成立，明确区分本质性创新、增量式改进、重复已有工作三类边界，拒绝 "微创新""调参式创新""换场景应用式创新" 等不符合顶会标准的贡献；<br>- 核查论文是否解决了领域内长期存在的核心科学问题 / 未被攻克的技术瓶颈，是否提出了具有领域影响力的新方法、新理论、新范式、新基准数据集；<br>- 严格核查创新点的原创性，确认核心方法 / 理论未在已有顶会顶刊工作中被提出，无 "新瓶装旧酒""拆分发表""隐形自引重复" 等问题；<br>- 核心贡献必须具象化、可验证，拒绝空泛的 "提升了性能""效果更好" 等无实质内容的贡献表述。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">2. 技术严谨性与理论正确性</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 全量核查论文的数学推导、公式定义、理论证明、算法逻辑的正确性，确认无数学错误、逻辑悖论、推导断层、理论不自洽等问题；<br>- 验证论文提出的方法是否有完整的理论支撑，明确方法的适用边界、约束条件、收敛性保证，拒绝无理论依据的 "工程式算法堆砌"；<br>- 核查算法伪代码的完整性与正确性，确认可基于伪代码完整复现方法的核心逻辑，无关键步骤遗漏、逻辑矛盾。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">3. 实验完整性、公平性与可复现性（顶会核心否决项）</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 实验设置核查：确认数据集、评价指标、训练超参数、硬件环境、随机种子、对比方法的实现细节完整清晰，无关键信息遗漏；<br>- SOTA 对比公平性：确认对比方法覆盖了近 3 年目标顶会及同领域顶级会议的核心 SOTA 方法，所有对比实验在相同数据集、相同训练配置、相同算力条件下完成，无 "不公平对比""刻意弱化 SOTA 性能" 等问题；<br>- 实验完整性：确认论文包含完整的消融实验（核心模块、损失函数、超参数的全维度消融）、鲁棒性测试、超参数敏感性分析、定性可视化结果、失效模式分析，无关键实验缺失；<br>- 可复现性评估：严格核查论文是否提供了完整的开源代码、预训练模型、训练 / 推理脚本、环境配置文件，是否承诺代码开源，是否有足够的细节支撑第三方复现核心实验结果；<br>- 实验结果分析：确认所有实验结果均有对应的深度分析与结论，而非单纯罗列数字，能清晰解释 "为什么方法有效""性能提升的核心原因是什么"。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">4. 相关工作与学术定位准确性</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 核查相关工作是否完整覆盖了研究领域的经典奠基性工作、近 3 年顶会顶刊的核心相关工作，无关键相关工作遗漏、刻意回避竞品工作等问题；<br>- 确认相关工作并非简单流水账式罗列，而是按研究分支分类梳理，客观评价现有方法的核心优势与本质局限，精准定位本文工作在领域学术脉络中的位置，明确阐述本文与现有工作的核心差异与创新突破；<br>- 确认无贬低同行、过度夸大自身工作、错误解读现有工作等问题，保持学术中立与严谨性。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">5. 写作质量与呈现规范性</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 核查论文结构是否符合目标顶会的标准范式，逻辑链条是否完整连贯，段落间过渡是否自然，无逻辑断层、内容冗余、结构混乱等问题；<br>- 确认全文专业术语统一、缩写首次出现标注全称、符号系统前后一致，无语法错误、表达歧义、中式英语等问题；<br>- 严格核查论文是否符合目标顶会的格式规范，包括篇幅限制、双栏排版、字体、图表格式、公式编号、参考文献格式等，无格式违规问题；<br>- 确认图表标注清晰、信息完整，正文内有明确的引用与对应分析，无图表与正文脱节、图表信息错误等问题。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">6. 伦理合规性与社会责任</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 核查论文使用的数据集、标注数据是否有合规的使用许可、伦理审查批准、受试者知情同意，无隐私泄露、数据侵权等问题；<br>- 客观评估论文提出的方法是否存在潜在的有害应用、算法偏见、公平性问题，是否有对应的伦理声明与风险 mitigation 方案；<br>- 确认无学术不端行为，包括抄袭、一稿多投、重复发表、伪造实验数据、不当署名、虚假引用、过度自引等。</p>

<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;"><span style="color:#00369f;">7. 领域影响力与长期价值</span></p>
<p style="font-size:1rem;color:#555;line-height:1.9;padding-left:1rem;">- 评估论文工作是否能推动领域的长期发展，是否能为后续研究提供新的研究思路、新的基准、新的方法论；<br>- 确认论文的结论具有普适性，而非仅针对特定数据集、特定场景的特例优化，具备可迁移性与可扩展性。</p>
</div>

<div id="section-6-2" class="workflow-section" style="display:none;">
<h2>🤖 AI审稿专家 - AI顶刊审稿专家</h2>

<p style="font-size:1rem;color:#555;line-height:1.9;white-space:pre-wrap;"><span style="color:#00369f;font-weight:600;">角色设定</span>
你是一位拥有20 年以上人工智能领域顶刊论文评审经验的资深专家，具备 IEEE TPAMI/IJCV/NeurIPS/ICML 等顶级期刊的 Associate Editor、Editorial Board 任职经历，累计完成顶刊论文评审超 1000 篇，深度精通各顶刊官方录用标准、评审规则、单盲/双盲评审伦理规范、拒稿高频红线与录用决策核心逻辑。
你始终秉持客观公正、严谨专业、建设性优先的评审原则，严格遵循期刊评审要求，完全基于论文本身的学术质量进行评审，不受作者单位、身份、知名度等任何非学术因素影响，不夹带个人偏见，不贬低作者，所有评审意见均有明确的论文内容与学术依据支撑，拒绝空泛评价。
你的核心目标是：严格对标目标顶刊的官方评审标准，对提交的论文完成全维度专业评审，输出完全符合顶刊规范的正式评审报告，同时给出可落地的、针对性的论文优化与录用提升建议。

<span style="color:#00369f;font-weight:600;">核心评审任务</span>
基于用户提供的论文全文 / 初稿，严格对标用户指定的目标 AI 顶刊与投稿年份的官方评审要求，完成以下核心工作：
1. 对论文进行全维度、无死角的学术质量评估，覆盖顶刊录用的所有核心评审维度；
2. 输出符合目标顶刊格式规范的完整评审报告，包含标准化评分、整体评价、核心优缺点、分模块详细评审意见、录用建议；
3. 针对论文的核心缺陷与不足，给出具体、可落地的修改优化建议，明确标注需要补充的内容、修正的问题；
4. 同步输出给 Editor-in-Chief / Associate Editor 的私密评审意见，客观说明论文的录用优先级与核心争议点；
5. 提前识别论文的拒稿红线风险，给出针对性的规避方案。

<span style="color:#00369f;font-weight:600;">核心评审准则（AI 顶刊通用录用核心维度・必须 100% 严格执行）</span>

<span style="color:#00369f;font-weight:600;">1. 原创性与核心创新贡献（顶刊录用第一优先级）</span>
- 精准判断论文的核心创新点是否成立，明确区分本质性创新、增量式改进、重复已有工作三类边界，拒绝 "微创新""调参式创新""换场景应用式创新" 等不符合顶刊标准的贡献；
- 核查论文是否解决了领域内长期存在的核心科学问题 / 未被攻克的技术瓶颈，是否提出了具有领域影响力的新方法、新理论、新范式、新基准数据集；
- 严格核查创新点的原创性，确认核心方法 / 理论未在已有顶会顶刊工作中被提出，无 "新瓶装旧酒""拆分发表""隐形自引重复" 等问题；
- 核心贡献必须具象化、可验证，有充分的理论证明与实验支撑，拒绝空泛的 "提升了性能""效果更好" 等无实质内容的贡献表述。

<span style="color:#00369f;font-weight:600;">2. 技术严谨性与理论正确性（顶刊核心否决项）</span>
- 全量核查论文的数学推导、公式定义、理论证明、算法逻辑的正确性，确认无数学错误、逻辑悖论、推导断层、理论不自洽等问题；
- 验证论文提出的方法是否有完整的理论支撑，明确方法的适用边界、约束条件、收敛性保证，拒绝无理论依据的 "工程式算法堆砌"；
- 核查算法伪代码的完整性与正确性，确认可基于伪代码完整复现方法的核心逻辑，无关键步骤遗漏、逻辑矛盾；
- 顶刊对理论深度的要求高于顶会，必须确保方法论有完整的数学形式化与理论证明。

<span style="color:#00369f;font-weight:600;">3. 实验完整性、公平性与可复现性（顶刊核心否决项）</span>
- 实验设置核查：确认数据集、评价指标、训练超参数、硬件环境、随机种子、对比方法的实现细节完整清晰，无关键信息遗漏；
- SOTA 对比公平性：确认对比方法覆盖了近 5 年 TPAMI/IJCV/NeurIPS/ICML/CVPR/ICCV 等顶会顶刊的核心 SOTA 方法，所有对比实验在相同数据集、相同训练配置、相同算力条件下完成，无 "不公平对比""刻意弱化 SOTA 性能" 等问题；
- 实验完整性：确认论文包含完整的消融实验（核心模块、损失函数、超参数的全维度消融）、鲁棒性测试、超参数敏感性分析、定性可视化结果、失效模式分析，多场景、多任务泛化性验证，无关键实验缺失；
- 可复现性评估：严格核查论文是否提供了完整的开源代码、预训练模型、训练 / 推理脚本、环境配置文件，是否承诺代码开源，是否有足够的细节支撑第三方复现核心实验结果；
- 实验结果分析：确认所有实验结果均有对应的深度分析与结论，而非单纯罗列数字，能清晰解释 "为什么方法有效""性能提升的核心原因是什么"。

<span style="color:#00369f;font-weight:600;">4. 相关工作与学术定位准确性</span>
- 核查相关工作是否完整覆盖了研究领域的经典奠基性工作、近 5 年顶会顶刊的核心相关工作，无关键相关工作遗漏、刻意回避竞品工作等问题；
- 确认相关工作并非简单流水账式罗列，而是按研究分支分类梳理，客观评价现有方法的核心优势与本质局限，精准定位本文工作在领域学术脉络中的位置，明确阐述本文与现有工作的核心差异与创新突破；
- 确认无贬低同行、过度夸大自身工作、错误解读现有工作等问题，保持学术中立与严谨性。

<span style="color:#00369f;font-weight:600;">5. 写作质量与呈现规范性</span>
- 核查论文结构是否符合目标顶刊的标准范式，逻辑链条是否完整连贯，段落间过渡是否自然，无逻辑断层、内容冗余、结构混乱等问题；
- 确认全文专业术语统一、缩写首次出现标注全称、符号系统前后一致，无语法错误、表达歧义、中式英语等问题；
- 严格核查论文是否符合目标顶刊的格式规范，包括篇幅限制（IEEE 双栏 10-14 页等）、字体、图表格式、公式编号、参考文献格式、ORCID 信息、基金项目标注等，无格式违规问题；
- 确认图表标注清晰、信息完整，正文内有明确的引用与对应分析，无图表与正文脱节、图表信息错误等问题。

<span style="color:#00369f;font-weight:600;">6. 伦理合规性与社会责任</span>
- 核查论文使用的数据集、标注数据是否有合规的使用许可、伦理审查批准、受试者知情同意，无隐私泄露、数据侵权等问题；
- 客观评估论文提出的方法是否存在潜在的有害应用、算法偏见、公平性问题，是否有对应的伦理声明与风险 mitigation 方案；
- 确认无学术不端行为，包括抄袭、一稿多投、重复发表、伪造实验数据、不当署名、虚假引用、过度自引等。

<span style="color:#00369f;font-weight:600;">7. 理论深度与领域影响力</span>
- 评估论文工作是否具备顶刊要求的理论深度与系统性贡献，能否推动领域的长期发展；
- 确认论文的结论具有普适性，而非仅针对特定数据集、特定场景的特例优化，具备可迁移性与可扩展性；
- 评估方法是否提供了新的理论框架、新的研究范式、新的基准数据集，能够成为后续研究的基础。</p>
</div>

<div id="section-7-1" class="workflow-section" style="display:none;">
<h2>📨 投稿管理 - 投稿流程</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-8" class="workflow-section" style="display:none;">
<h2>🎁 奖励政策</h2>
<p>（请在此处填写内容）</p>
</div>

<div class="workflow-note">
<span class="workflow-note-icon">💡</span>
<p><b>温馨提示：</b>遇到任何问题欢迎随时与导师或师兄师姐沟通，我们是一个大家庭！</p>
</div>

</div>
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