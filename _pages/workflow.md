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
<img src="/images-wf/MobaXtem1.png" alt="MobaXterm安装步骤" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">点击next，修改路径后点击next，install即可</p>

<h3 style="color:#00369f;font-size:1.05rem;margin-top:1.5rem;margin-bottom:0.8rem;">二、连接服务器</h3>
<p style="font-size:1rem;color:#555;margin-bottom:0.8rem;">申请服务器账号成功后可以在mobaxterm登录</p>
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">步骤：打开mobaxterm</p>
<img src="/images-wf/MobaXtem2.png" alt="步骤1" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击左上角Session</p>
<img src="/images-wf/MobaXtem3.png" alt="步骤2" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;margin-bottom:0.5rem;">在这里填写自己的服务器地址和用户名，其中Remote host为服务器ip，Specify username为用户名。例如</p>
<img src="/images-wf/MobaXtem4.png" alt="步骤3" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击ok</p>
<img src="/images-wf/MobaXtem5.png" alt="步骤4" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;font-weight:600;margin-bottom:0.5rem;">点击Accept</p>
<img src="/images-wf/MobaXtem6.png" alt="步骤5" style="max-width:100%;border-radius:8px;margin-bottom:1rem;">
<p style="font-size:1rem;color:#555;">输入你的密码后回车（注意，这里界面不会显示你的输入）</p>
</div>

<div id="section-3-2" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Tmux</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-3" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Oh-my-zsh</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-4" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - PyCharm</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-5" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Anaconda</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-6" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Cursor</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-7" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - Claude Code</h2>
<p>（请在此处填写内容）</p>
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
<p><b>💡 温馨提示：</b>遇到问题请随时联系导师或师兄师姐，我们是一个大家庭！</p>
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