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
<p>（请在此处填写内容）</p>
</div>

<div id="section-2" class="workflow-section" style="display:none;">
<h2>🖥️ 服务器账号领取</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3-1" class="workflow-section" style="display:none;">
<h2>📦 软件安装 - MobaXterm</h2>
<p>（请在此处填写内容）</p>
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