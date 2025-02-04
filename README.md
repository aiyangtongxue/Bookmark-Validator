# 🔖 书签可用性检测工具

**一键检测浏览器书签的存活状态**，快速清理失效链接。支持 Chrome/Firefox 等主流浏览器导出的书签文件（.html）。

[![在线试用](https://img.shields.io/badge/在线试用-点击体验-blue)](https://aiyangtongxue.github.io/Bookmark-Validator) 
[![开源协议](https://img.shields.io/github/license/aiyangtongxue/Bookmark-Validator)](LICENSE)

![界面截图](第一个版本图片.png)
![界面截图](第二个版本图片.png)
-

## ✨ 核心功能

- **智能解析**：自动识别浏览器导出的书签文件
- **批量检测**：支持同时检测数百个书签链接
- **状态可视化**：
  - ✅ 绿色标识可用链接（响应码 2xx/3xx）
  - ❌ 红色标识失效链接（超时/4xx/5xx）
- **进度追踪**：实时显示检测进度百分比
- **极简交互**：拖拽上传 + 一键式操作

---

## 🚀 快速使用

1. 从浏览器导出书签文件 (`书签 > 导出书签...`)
2. 打开本工具网页，上传导出的 `.html` 文件
3. 点击「开始检测」等待结果
4. 根据检测结果清理失效书签

---

## ⚙️ 技术亮点

```javascript
// 使用现代浏览器 API 实现
const checkAvailability = async (url) => {
  try {
    await fetch(url, { method: 'HEAD', signal: AbortSignal.timeout(5000) });
    return true;
  } catch {
    return false;
  }
};
```

- **HEAD 请求**：仅获取头部信息，节省带宽
- **超时控制**：5 秒无响应自动终止检测
- **并行处理**：异步队列提升检测效率
- **安全防护**：本地解析不上传服务器

---

## 🌈 设计理念

- **隐私优先**：所有操作在浏览器本地完成
- **响应式布局**：适配手机/平板/电脑屏幕
- **无障碍支持**：兼容屏幕阅读器操作
- **极简美学**：Material Design 设计语言

---

## 🛠️ 开发指南

```bash
# 克隆项目
git clone https://github.com/aiyangtongxue/Bookmark-Validator.git

# 本地运行
cd Bookmark-Validator && open index.html
```

欢迎提交 PR 或 [报告问题](https://github.com/aiyangtongxue/Bookmark-Validator/issues)

---

*提示：建议定期检测书签，保持收藏夹整洁高效！* 🧹
