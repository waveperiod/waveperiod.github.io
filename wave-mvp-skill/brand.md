# Wave 品牌模块 (Brand)

## Logo

### 主符号
```
({})
```

**含义**：
- 花括号 = 代码/系统/理性
- 圆括号 = 包容/周期/循环
- 合体 = 理性与感性的平衡

### 颜色
- 主色：#D60D0D (Wave红)
- 使用场景：Logo、CTA按钮、重点标记

---

## 配色系统

### 核心色
```css
--wave-red: #D60D0D;           /* 品牌红 */
--wave-black: #000000;         /* 黑色 */
--white: #FFFFFF;              /* 白色 */
```

### 能量渐变色（数据可视化用）
```css
--coral-gradient: linear-gradient(180deg, 
  #FF6B6B 0%,    /* 高能量 */
  #FFB8B8 50%,   /* 中能量 */
  #FFE5E5 100%   /* 低能量 */
);
```

### 功能色
```css
--gray-light: #E5E5E5;         /* 未激活/禁用 */
--success: #10B981;            /* 完成状态 */
```

---

## 视觉风格

### 关键词
- 极简几何
- 数据可视化
- 黑白为主
- 红橙点缀

### 参考
- 上传的图2：柱状图 + 渐变 + 圆点标记
- 风格：类似 Whoop/Oura 的专业运动科技感

### 禁止
- ❌ 少女粉
- ❌ 可爱卡通
- ❌ 过度装饰
- ❌ 复杂纹理

---

## 文案原则

### 核心理念
1. **激素是隐藏优势，不是负担**
2. **从被动承受到主动掌握**
3. **自己做最懂自己的人**

### 核心话术
> 该冲的时候冲，该歇的时候歇

### 语言风格
- 专业但不术语化
- 温暖但不矫情
- 赋能但不说教

---

## 文案对照表

### ❌ 避免使用
| 不说 | 原因 |
|------|------|
| "大姨妈" | 俗称，不专业 |
| "经期不适合运动" | 负面暗示 |
| "激素让你情绪化" | 污名化 |
| "女生就是这样" | 性别刻板印象 |
| "忍一忍就过去了" | 消极被动 |

### ✅ 推荐使用
| 而说 | 原因 |
|------|------|
| "月经期" | 专业中性 |
| "这周适合恢复性训练" | 建设性建议 |
| "这几天情绪敏感度更高" | 中性描述 |
| "每个人的周期都是独特的" | 个性化 |
| "主动调整节奏" | 积极赋能 |

---

## 双语文案模板

### Hero Section
```javascript
{
  zh: {
    title: "12周，让激素成为你的健身教练",
    subtitle: "该冲的时候冲，该歇的时候歇",
    cta: "开始规划我的12周"
  },
  en: {
    title: "12 Weeks: Turn Your Hormones Into Your Fitness Coach",
    subtitle: "Push when it's time to push, rest when it's time to rest",
    cta: "Start My 12-Week Plan"
  }
}
```

### 月经周期阶段
```javascript
phases: {
  zh: {
    menstrual: { name: "月经期", emoji: "🌙", tip: "适合恢复性训练" },
    follicular: { name: "卵泡期", emoji: "🌱", tip: "能量上升期" },
    ovulation: { name: "排卵期", emoji: "⚡", tip: "巅峰表现期" },
    luteal: { name: "黄体期", emoji: "🌗", tip: "适度调整期" }
  },
  en: {
    menstrual: { name: "Menstrual", emoji: "🌙", tip: "Recovery mode" },
    follicular: { name: "Follicular", emoji: "🌱", tip: "Energy rising" },
    ovulation: { name: "Ovulation", emoji: "⚡", tip: "Peak performance" },
    luteal: { name: "Luteal", emoji: "🌗", tip: "Moderate intensity" }
  }
}
```

---

## 品牌参考文档

### 完整工具包
参考项目文件：
- `/mnt/project/Wave-Brand-Communication-Toolkit.md`
- `/mnt/project/Wave-Deep-Pain-Points-Supplement.md`

### 使用方式
- 写文案前先看一遍
- 不确定时随时查阅
- 保持品牌一致性

---

## 品牌一致性检查清单

每次发布内容前检查：

### 视觉
- [ ] Logo颜色正确 (#D60D0D)
- [ ] 主色调是黑白红
- [ ] 数据可视化用渐变色
- [ ] 无少女粉/可爱风元素

### 文案
- [ ] 无负面暗示词汇
- [ ] 无医学术语（或有解释）
- [ ] 体现赋能和主动性
- [ ] 符合核心理念

### 调性
- [ ] 专业但易懂
- [ ] 温暖但不矫情
- [ ] 理性但不冷漠

---

*更新时间: 根据实际使用动态调整*
