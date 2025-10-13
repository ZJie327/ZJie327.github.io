---
title: "HTML 演示文章-对话框"
date: 2025-10-11
comments: true
---

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
  <div id="time-display1" style="margin-top: 15px;"></div>
  
  <script>
    function showTime() {
      const now = new Date();
      document.getElementById('time-display1').innerHTML = 
        `<strong>当前时间：${now.toLocaleString()}</strong>`;
    }
  </script>
</div>

## 继续文章内容
又回到了 Markdown 格式...

<div class="custom-class" style="color: red;">
  这是自定义 HTML 内容
</div>

<details>
<summary>点击展开</summary>
这里是隐藏的内容
</details>

## 连续警告框
<div class="alert-sequence">
  <button class="dialog-button" onclick="showAlerts()">显示连续警告框</button>
</div>

<script>
function showAlerts() {
  alert("这是第一个提示！");
  alert("小心了！！！");
  alert("NO!!!");
}
</script>

## 确认对话框

<button class="dialog-button" onclick="showConfirmSequence()">连续确认对话框</button>

<script>
function showConfirmSequence() {
  if (confirm("确定要执行第一步吗？")) {
    if (confirm("ARE YOU SURE？")) {
      if (confirm("最后确认，真的要执行吗？")) {
        alert("我猜你是小瑛");
      }
    }
  }
}
</script>

## 自定义模态框

<!-- 自定义模态框 -->
<button class="dialog-button" onclick="showCustomModal('THE FIRST TIP')">显示自定义提示框</button>

<div id="customModal" style="
  display: none;
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  z-index: 1000;
">
  <div style="
    position: absolute;
    top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    background: white;
    padding: 30px;
    border-radius: 10px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.3);
    max-width: 400px;
    width: 90%;
  ">
    <h3 id="modalTitle" style="margin-top: 0;">提示</h3>
    <p id="modalMessage">这里是提示内容</p >
    <button onclick="closeCustomModal()" style="
      background: #3498db;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 5px;
      cursor: pointer;
    ">确定</button>
  </div>
</div>

<script>
let currentStep = 0;
const messages = [
  "欢迎访问我的博客！",
  "这里有很多技术内容分享",
  "希望你能找到有用的信息",
  "感谢阅读！"
];

function showCustomModal(message) {
  document.getElementById('modalMessage').textContent = message;
  document.getElementById('customModal').style.display = 'block';
}

function closeCustomModal() {
  document.getElementById('customModal').style.display = 'none';
  currentStep++;
  if (currentStep < messages.length) {
    setTimeout(() => showCustomModal(messages[currentStep]), 500);
  } else {
    currentStep = 0; // 重置
  }
}
</script>

## Toast提示(轻量级)

<button class="dialog-button" onclick="showToastSequence()">显示连续Toast提示</button>

<div id="toastContainer" style="
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 1000;
"></div>

<script>
function showToast(message, type = 'info') {
  const toast = document.createElement('div');
  const colors = {
    info: '#3498db',
    success: '#2ecc71',
    warning: '#f39c12',
    error: '#e74c3c'
  };
  
  toast.style.cssText = `
    background: ${colors[type]};
    color: white;
    padding: 15px 20px;
    margin-bottom: 10px;
    border-radius: 5px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    transform: translateX(100%);
    transition: transform 0.3s ease;
    max-width: 300px;
  `;
  
  toast.textContent = message;
  document.getElementById('toastContainer').appendChild(toast);
  
  // 动画进入
  setTimeout(() => toast.style.transform = 'translateX(0)', 100);
  
  // 自动消失
  setTimeout(() => {
    toast.style.transform = 'translateX(100%)';
    setTimeout(() => toast.remove(), 300);
  }, 3000);
}

function showToastSequence() {
  showToast('页面加载完成', 'success');
  setTimeout(() => showToast('新内容已更新', 'info'), 1000);
  setTimeout(() => showToast('请检查千里传音阁', 'warning'), 2000);
  setTimeout(() => showToast('操作成功！', 'success'), 3000);
}
</script>

## 多步骤表单对话框

<!-- 多步骤表单对话框 -->
<button class="dialog-button" id="multiStepBtn">多步骤对话框</button>

<div id="multiStepModal" class="modal-overlay" style="display: none;">
  <div class="modal-content">
    <!-- 步骤1 -->
    <div id="step1">
      <h3>步骤 1: 基本信息</h3>
      <input type="text" id="userName" placeholder="请输入姓名" class="form-input">
      <div class="button-group">
        <button class="dialog-button" id="nextBtn1">下一步</button>
      </div>
    </div>
    <!-- 步骤2 -->
    <div id="step2" style="display: none;">
      <h3>步骤 2: 选择偏好</h3>
      <select id="userPreference" class="form-input">
        <option value="tech">技术文章</option>
        <option value="design">设计相关</option>
        <option value="life">生活分享</option>
      </select>
      <div class="button-group">
        <button class="dialog-button dialog-button-secondary" id="prevBtn">上一步</button>
        <button class="dialog-button dialog-button-success" id="submitBtn">提交</button>
      </div>
    </div>
  </div>
</div>

<style>
.modal-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  z-index: 1000;
  display: none;
}

.modal-content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: white;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.3);
  max-width: 500px;
  width: 90%;
}

.form-input {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ddd;
  border-radius: 4px;
  box-sizing: border-box;
}

.button-group {
  text-align: right;
  margin-top: 20px;
}

.dialog-button-secondary {
  background: linear-gradient(135deg, #95a5a6 0%, #7f8c8d 100%) !important;
}

.dialog-button-success {
  background: linear-gradient(135deg, #2ecc71 0%, #27ae60 100%) !important;
}
</style>

<script>
// 使用 DOMContentLoaded 确保页面加载完成
document.addEventListener('DOMContentLoaded', function() {
  // 获取元素
  const multiStepBtn = document.getElementById('multiStepBtn');
  const multiStepModal = document.getElementById('multiStepModal');
  const nextBtn1 = document.getElementById('nextBtn1');
  const prevBtn = document.getElementById('prevBtn');
  const submitBtn = document.getElementById('submitBtn');
  
  let currentStep = 1;
  
  // 显示步骤
  function showStep(step) {
    document.getElementById('step1').style.display = step === 1 ? 'block' : 'none';
    document.getElementById('step2').style.display = step === 2 ? 'block' : 'none';
    currentStep = step;
  }
  
  // 打开对话框
  multiStepBtn.addEventListener('click', function() {
    multiStepModal.style.display = 'block';
    showStep(1);
  });
  
  // 下一步
  nextBtn1.addEventListener('click', function() {
    const name = document.getElementById('userName').value;
    if (!name.trim()) {
      alert('请输入姓名');
      return;
    }
    showStep(2);
  });
  
  // 上一步
  prevBtn.addEventListener('click', function() {
    showStep(1);
  });
  
  // 提交
  submitBtn.addEventListener('click', function() {
    const name = document.getElementById('userName').value;
    const preference = document.getElementById('userPreference').value;
    
    alert(`感谢 ${name}！你的偏好是：${preference}`);
    multiStepModal.style.display = 'none';
    
    // 重置表单
    document.getElementById('userName').value = '';
    document.getElementById('userPreference').value = 'tech';
    showStep(1);
  });
  
  // 点击模态框外部关闭
  multiStepModal.addEventListener('click', function(e) {
    if (e.target === this) {
      this.style.display = 'none';
    }
  });
});
</script>


## 输入提示框

<button class="dialog-button" onclick="showPromptSequence()">连续输入对话框</button>

<script>
function showPromptSequence() {
  const name = prompt("请输入你的姓名：");
  if (name) {
    const email = prompt(`你好 ${name}，请输入你的邮箱：`);
    if (email) {
      const message = prompt("最后，请输入你的留言：");
      if (message) {
        alert(`感谢 ${name}！我们会通过 ${email} 联系你。`);
      }
    }
  }
}
</script>

## 加载状态对话框

<button class="dialog-button" onclick="showLoadingSequence()">显示加载过程</button>

<div id="loadingModal" style="display: none; /* 同上modal样式 */">
  <div style="text-align: center;">
    <div style="
      width: 40px;
      height: 40px;
      border: 4px solid #f3f3f3;
      border-top: 4px solid #3498db;
      border-radius: 50%;
      animation: spin 1s linear infinite;
      margin: 0 auto 20px;
    "></div>
    <p id="loadingMessage">正在加载...</p >
  </div>
</div>

<style>
@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}
</style>

<script>
function showLoadingSequence() {
  const modal = document.getElementById('loadingModal');
  const message = document.getElementById('loadingMessage');
  
  modal.style.display = 'block';
  message.textContent = '正在初始化...';
  
  setTimeout(() => {
    message.textContent = '加载内容...';
    setTimeout(() => {
      message.textContent = '几乎完成了...';
      setTimeout(() => {
        modal.style.display = 'none';
        alert('所有内容加载完成！');
      }, 1000);
    }, 1500);
  }, 1000);
}
</script>

## 用户引导

<button class="dialog-button" onclick="startUserGuide()">开始用户引导</button>

<div id="guideModal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0,0,0,0.8); z-index: 1000;">
  <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); background: white; padding: 30px; border-radius: 15px; max-width: 500px; width: 90%;">
    <h3 id="guideTitle" style="color: #2c3e50; margin-top: 0;">欢迎使用引导</h3>
    <p id="guideContent" style="color: #7f8c8d; line-height: 1.6;">引导内容将在这里显示</p >
    <div style="text-align: right; margin-top: 25px;">
      <button onclick="prevGuideStep()" style="background: #95a5a6; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; margin-right: 10px;">上一步</button>
      <button onclick="nextGuideStep()" style="background: #3498db; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer;">下一步</button>
    </div>
    <div style="text-align: center; margin-top: 20px;">
      <span id="guideProgress" style="color: #bdc3c7;">1/4</span>
    </div>
  </div>
</div>

<script>
const guideSteps = [
  { title: "欢迎来到我的博客", content: "这里将带你了解博客的主要功能" },
  { title: "文章阅读", content: "你可以浏览各种技术文章和教程" },
  { title: "互动功能", content: "欢迎在文章下方留言评论" },
  { title: "完成引导", content: "现在开始探索吧！如有问题随时联系我" }
];

let currentGuideStep = 0;

function startUserGuide() {
  currentGuideStep = 0;
  showGuideStep(currentGuideStep);
  document.getElementById('guideModal').style.display = 'block';
}

function showGuideStep(step) {
  document.getElementById('guideTitle').textContent = guideSteps[step].title;
  document.getElementById('guideContent').textContent = guideSteps[step].content;
  document.getElementById('guideProgress').textContent = `${step + 1}/${guideSteps.length}`;
  
  // 更新按钮状态
  document.querySelector('button[onclick="prevGuideStep()"]').style.display = 
    step === 0 ? 'none' : 'inline-block';
  
  const nextButton = document.querySelector('button[onclick="nextGuideStep()"]');
  nextButton.textContent = step === guideSteps.length - 1 ? '完成' : '下一步';
}

function nextGuideStep() {
  if (currentGuideStep < guideSteps.length - 1) {
    currentGuideStep++;
    showGuideStep(currentGuideStep);
  } else {
    document.getElementById('guideModal').style.display = 'none';
    alert('引导完成！欢迎探索博客内容。');
  }
}

function prevGuideStep() {
  if (currentGuideStep > 0) {
    currentGuideStep--;
    showGuideStep(currentGuideStep);
  }
}
</script>


