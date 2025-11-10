# Wave 技术栈模块 (Tech Stack)

## 核心技术

### 前端
```
HTML5 + CSS3 + JavaScript (Vanilla)
```

**为什么不用框架？**
- ✅ 5天时间紧
- ✅ 单页应用够用
- ✅ 部署简单
- ✅ 性能好

### 样式
```
TailwindCSS (via CDN)
```

**使用方式**：
```html
<script src="https://cdn.tailwindcss.com"></script>
```

### 数据可视化
```
Chart.js 3.x
```

**CDN**：
```html
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
```

### 日历导出
```
ics.js
```

**CDN**：
```html
<script src="https://unpkg.com/ics@2.35.0/dist/bundle.js"></script>
```

---

## 项目结构（建议）

```
wave-gas-planner/
├── index.html              # 主页面
├── css/
│   └── custom.css          # 自定义样式（Tailwind补充）
├── js/
│   ├── i18n.js            # 语言切换
│   ├── cycle.js           # 月经周期计算
│   ├── gas.js             # GAS训练规划
│   ├── chart.js           # 图表渲染
│   ├── ics-export.js      # ICS导出
│   └── main.js            # 主控制器
├── assets/
│   └── logo.svg           # Logo
└── README.md
```

**原则**：
- 模块化：一个文件一个功能
- 可读性：函数命名清晰
- 可维护：注释充分

---

## 部署

### GitHub Pages

**步骤**：
```bash
# 1. 初始化
git init
git add .
git commit -m "Initial commit"

# 2. 推送到GitHub
git remote add origin [你的repo地址]
git push -u origin main

# 3. 启用Pages
# GitHub网站 → Settings → Pages → Source: main branch
```

**访问地址**：
```
https://你的用户名.github.io/仓库名
```

---

## 关键API/库

### Chart.js 配置示例
```javascript
new Chart(ctx, {
  type: 'bar',
  data: {
    labels: ['Week 1', 'Week 2', ...],
    datasets: [{
      data: [4, 5, 6, ...],
      backgroundColor: (context) => {
        // 渐变色逻辑
      }
    }]
  },
  options: {
    responsive: true,
    plugins: { ... }
  }
});
```

### ics.js 使用示例
```javascript
const { createEvents } = ics;

const events = [{
  start: [2025, 1, 15],
  duration: { hours: 1 },
  title: '【中强度】排卵期 - 力量训练',
  description: '能量指数: 8/10\n建议: 增加重量'
}];

const { error, value } = createEvents(events);
const blob = new Blob([value], { type: 'text/calendar' });
```

---

## 邮箱收集

### 方案A: Formspree（推荐）
```html
<form action="https://formspree.io/f/你的ID" method="POST">
  <input type="email" name="email" required>
  <button type="submit">提交</button>
</form>
```

**免费额度**：50次/月

### 方案B: Google Forms
- 创建表单
- 嵌入iframe
- 收集到Google Sheets

---

## 性能优化

### 关键指标
- 首屏加载：<2秒
- 图表渲染：<500ms
- 交互响应：<100ms

### 优化手段
- ✅ CDN加载库（快）
- ✅ 图片用SVG（小）
- ✅ 懒加载非首屏内容
- ✅ 客户端计算（无网络延迟）

---

## 浏览器兼容性

### 目标浏览器
- Chrome 90+
- Safari 14+
- Edge 90+
- iOS Safari 14+
- Android Chrome 90+

### 检查工具
- Can I Use: https://caniuse.com/
- BrowserStack: https://www.browserstack.com/ (测试)

---

## 开发工具

### 代码编辑器
- VS Code（推荐）
- 任何文本编辑器

### 调试
- Chrome DevTools
- Safari Web Inspector

### 测试
- 本地：Live Server (VS Code插件)
- 移动端：Chrome远程调试

---

## 常用资源链接

### 文档
- TailwindCSS: https://tailwindcss.com/docs
- Chart.js: https://www.chartjs.org/docs/
- ics.js: https://github.com/adamgibbons/ics

### 工具
- SVG编辑: https://editor.method.ac/
- 配色: https://coolors.co/
- 图标: https://heroicons.com/

---

## 技术决策记录

### 为什么用Vanilla JS不用React？
- 5天时间紧，无需学习成本
- 单页应用复杂度低
- 性能更好（无框架开销）

### 为什么用Chart.js不用D3？
- Chart.js开箱即用
- D3学习曲线陡
- 我们只需要柱状图

### 为什么用GitHub Pages不用Vercel？
- GitHub Pages完全免费
- 一键部署
- 静态站点够用

---

## 待探索问题

### 开发时再决定
- [ ] 具体的Chart.js配置参数
- [ ] 移动端图表高度
- [ ] ICS事件的详细格式
- [ ] 表单验证规则

**原则**：先让功能跑起来，再优化细节

---

*更新时间: 遇到技术问题时动态补充*
