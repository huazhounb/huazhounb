## Hi there 👋
<img src="/src/header_.png">
<!-- 实时时间显示组件 -->
<div id="realtime-clock" style="
  background: #1e1e2e;
  color: #a6e3a1;
  padding: 1rem;
  border-radius: 12px;
  font-family: 'Courier New', monospace;
  text-align: center;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
">
  <div id="date" style="font-size: 1.2rem; opacity: 0.8">2025年6月12日</div>
  <div id="time" style="font-size: 2.5rem; font-weight: bold">00:00:00</div>
  <div id="timezone" style="font-size: 0.9rem; margin-top: 8px">UTC+8</div>
</div>

<script>
  function updateTime() {
    const now = new Date();
    // 格式化日期（中文）
    const dateStr = now.toLocaleDateString('zh-CN', { 
      year: 'numeric', 
      month: 'long', 
      day: 'numeric',
      weekday: 'long'
    });
    // 格式化时间（24小时制）
    const timeStr = now.toLocaleTimeString('zh-CN', { 
      hour: '2-digit', 
      minute: '2-digit', 
      second: '2-digit',
      hour12: false
    });
    // 显示时区
    const tz = `UTC${now.getTimezoneOffset() > 0 ? '-' : '+'}${Math.abs(now.getTimezoneOffset())/60}`;
    
    document.getElementById('date').innerText = dateStr;
    document.getElementById('time').innerText = timeStr;
    document.getElementById('timezone').innerText = tz;
  }
  
  // 立即更新并启动每秒刷新
  updateTime();
  setInterval(updateTime, 1000);
</script>
<!--
**huazhounb/huazhounb** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
Here are some ideas to get you started:
- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
