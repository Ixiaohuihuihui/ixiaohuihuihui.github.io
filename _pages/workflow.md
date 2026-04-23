---
layout: page-no-nav
title: "课题组WorkFlow"
permalink: /workflow/
author_profile: false
---

<style>
.workflow-wrapper {
    display: flex;
    max-width: 1100px;
    margin: 0 auto;
    padding: 2rem 1rem;
    gap: 2rem;
}

.workflow-sidebar {
    width: 220px;
    flex-shrink: 0;
    position: sticky;
    top: 2rem;
    height: fit-content;
}

.workflow-nav {
    background: #f8f9fa;
    border-radius: 12px;
    padding: 1rem 0;
}

.workflow-nav-item {
    display: block;
    padding: 0.8rem 1.5rem;
    color: #333;
    text-decoration: none;
    cursor: pointer;
    transition: all 0.2s;
    border-left: 3px solid transparent;
}

.workflow-nav-item:hover {
    background: #e9ecef;
    color: #00369f;
}

.workflow-nav-item.active {
    background: #e8f0ff;
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
    border: 1px solid #e0e0e0;
}

.workflow-section h2 {
    color: #00369f;
    font-size: 1.3rem;
    margin-bottom: 1rem;
    padding-bottom: 0.5rem;
    border-bottom: 2px solid #f0f0f0;
}

.workflow-section p {
    color: #555;
    line-height: 1.7;
}

.sub-item {
    padding: 0.5rem 1rem;
    margin-left: 1rem;
    color: #666;
    cursor: pointer;
    font-size: 0.9rem;
}

.sub-item:hover {
    color: #00369f;
}

.back-link {
    display: inline-block;
    margin-bottom: 1.5rem;
    color: #00369f;
    text-decoration: none;
    font-weight: 500;
}

.back-link:hover {
    text-decoration: underline;
}
</style>

<div class="workflow-wrapper">
<nav class="workflow-sidebar">
<div class="workflow-nav">
<a class="workflow-nav-item" href="#section-1" onclick="showSection('section-1', this)">📌 流程规范</a>
<a class="workflow-nav-item" href="#section-2" onclick="showSection('section-2', this)">🖥️ 服务器账号领取</a>
<a class="workflow-nav-item" href="#section-3" onclick="showSection('section-3', this)">📦 软件安装</a>
<a class="workflow-nav-item" href="#section-4" onclick="showSection('section-4', this)">📝 论文写作</a>
<a class="workflow-nav-item" href="#section-5" onclick="showSection('section-5', this)">💡 写论文提示词</a>
<a class="workflow-nav-item" href="#section-6" onclick="showSection('section-6', this)">🤖 AI审稿专家的Prompt</a>
<a class="workflow-nav-item" href="#section-7" onclick="showSection('section-7', this)">📨 投稿管理</a>
<a class="workflow-nav-item" href="#section-8" onclick="showSection('section-8', this)">🎁 奖励政策</a>
</div>
</nav>

<div class="workflow-content">
<a href="/#-ktzwf" class="back-link">← 返回课题组日常</a>

<div id="section-1" class="workflow-section">
<h2>📌 流程规范</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-2" class="workflow-section" style="display:none;">
<h2>🖥️ 服务器账号领取</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-3" class="workflow-section" style="display:none;">
<h2>📦 软件安装</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-4" class="workflow-section" style="display:none;">
<h2>📝 论文写作</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-5" class="workflow-section" style="display:none;">
<h2>💡 写论文提示词</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-6" class="workflow-section" style="display:none;">
<h2>🤖 AI审稿专家的Prompt</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-7" class="workflow-section" style="display:none;">
<h2>📨 投稿管理</h2>
<p>（请在此处填写内容）</p>
</div>

<div id="section-8" class="workflow-section" style="display:none;">
<h2>🎁 奖励政策</h2>
<p>（请在此处填写内容）</p>
</div>
</div>
</div>

<script>
function showSection(id, element) {
    document.querySelectorAll('.workflow-section').forEach(function(section) {
        section.style.display = 'none';
    });
    document.getElementById(id).style.display = 'block';

    document.querySelectorAll('.workflow-nav-item').forEach(function(item) {
        item.classList.remove('active');
    });
    element.classList.add('active');
}

// Show first section by default
document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('.workflow-nav-item').click();
});
</script>

<div class="workflow-note">
<b>温馨提示：</b>遇到任何问题欢迎随时与导师或师兄师姐沟通，我们是一个大家庭！
</div>
</div>