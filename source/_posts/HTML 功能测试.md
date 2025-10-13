---
title: "HTML 功能测试"
date: 2025-10-11
comments: true
---

### 测试基础 HTML
<div style="border: 2px dashed #3498db; padding: 20px;">
  <h4>HTML 区块测试</h4>
  <p>如果看到这个带边框的区域，说明 HTML 工作正常</p >
</div>

### 测试 JavaScript
<button onclick="document.getElementById('js-test').innerHTML='✅ JavaScript 工作正常!'">
  测试 JS
</button>
<div id="js-test" style="margin-top: 10px;"></div>

### 测试 CSS
<style>
.test-css {
  background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
  color: white;
  padding: 15px;
  border-radius: 8px;
}
</style>
<div class="test-css">
  CSS 样式测试 - 如果看到渐变背景，说明 CSS 工作正常
</div>

这是正常的 Markdown 文字。

<div style="background: #f0f8ff; padding: 20px; border-radius: 8px;">
  <h3>这是 HTML 区块</h3>
  <p>这里可以写任何 HTML 内容</p >
  <button onclick="alert('xiao xiang')">Click</button>
</div>

继续 Markdown 内容...

## Markdown 标题

下面是嵌入的 HTML 组件：

<div class="custom-widget">
  <style>
    .custom-widget {
      border: 2px solid #3498db;
      border-radius: 10px;
      padding: 20px;
      margin: 20px 0;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: white;
    }
    .demo-btn {
      background: #e74c3c;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
  
  <h3>🎯 交互式演示</h3>
  <p>这个区域完全用 HTML/CSS/JavaScript 创建</p >
  
  <button class="demo-btn" onclick="showTime()">显示当前时间</button>
  <div id="time-display" style="margin-top: 15px;"></div>
  
  <script>
    function showTime() {
      const now = new Date();
      document.getElementById('time-display').innerHTML = 
        `<strong>当前时间：${now.toLocaleString()}</strong>`;
    }
  </script>
</div>

## 继续文章内容
又回到了 Markdown 格式...

## 自定义样式区块

<div class="tip-box" style="
    background: #e7f3ff;
    border-left: 4px solid #2196F3;
    padding: 15px;
    margin: 20px 0;
    border-radius: 0 8px 8px 0;
">
    <strong>💡 提示：</strong>
    这是一个自定义的提示框样式
</div>

## 响应式布局

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 20px;">
  <div style="background: #ffeaa7; padding: 15px; border-radius: 8px;">
    <h4>左侧内容</h4>
    <p>网格布局的左侧</p >
  </div>
  <div style="background: #a29bfe; padding: 15px; border-radius: 8px;">
    <h4>右侧内容</h4>
    <p>网格布局的右侧</p >
  </div>
</div>
<!--
## 嵌入外部内容

<!-- 嵌入 Codepen 
<p class="codepen" data-height="300" data-theme-id="dark" data-default-tab="result" data-slug-hash="xxyz" data-user="username">
  See the Pen <a href="">Example</a > on CodePen.
</p >

<!-- 嵌入 YouTube 
<iframe width="100%" height="400" src="https://www.youtube.com/embed/视频ID" frameborder="0" allowfullscreen></iframe>
-->
## JavaScript限制

<!-- 简单的 JS 可以工作 -->
<button onclick="alert('xiao ying')">Click</button>

<!-- 但复杂的 JS 可能受浏览器安全策略限制 -->
<script>
// 某些 AJAX 请求可能被阻止
// 跨域请求可能失败
</script>

## 样式冲突

<style>
/* 这些样式只影响当前元素 */
.custom-element {
  color: red;
}
</style>
<div class="custom-element">测试</div>
<!--## 文件路径-->
<!--
 使用绝对路径 
<img src="/images/my-header-blog.img" alt="图片"> -->
<!--
 或者使用 Hexo 资源标签 
{% asset_img demo.jpg "图片描述" %}
-->

## 渐进增强

<div class="enhanced-content">
  <!-- 基础 HTML 内容 -->
  <p>基础信息展示</p>
  
  <!-- 增强的交互功能 -->
  <script>
    if (typeof Modernizr !== 'undefined') {
      // 只在支持的情况下加载高级功能
    }
  </script>
</div>

## 移动端适配
<div style="
  max-width: 100%;
  overflow-x: auto;
  padding: 15px;
  background: #5293d4ff;
">
  <!-- 确保内容在移动端正常显示 -->
</div>
<!--
## 性能考虑
 懒加载图片 
<img src="/images/placeholder.jpg" data-src="/images/actual-image.jpg" class="lazy-load">
-->
<!--
<script>
// 简单的懒加载实现
document.addEventListener('DOMContentLoaded', function() {
  const lazyImages = document.querySelectorAll('.lazy-load');
  // 懒加载逻辑...
});
</script> 
-->