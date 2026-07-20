# 🛡️ Bilibili Search Purify (B站搜索结果纯净版)

> 拒绝算法绑架，还你一个干净、高效的B站搜索体验！

当我们满怀期待地在B站搜索诸如“美食教程”、“学习资料”时，搜索结果往往会被算法硬塞入大量**毫不相关**的擦边球、标题党或是营销号的搞笑视频。

本项目旨在通过 Tampermonkey (油猴) 脚本，**动态、无感**地屏蔽所有与搜索词无关的推荐视频，以及那些依靠低俗标题博眼球的垃圾内容。

<img src="https://houlir2.dpdns.org/2026/07/ad1d8f25ccffb77e23041ede0bdcb4b9.png" alt="屏幕截图 2026-07-20 104105" style="zoom: 80%;" />

<img src="https://houlir2.dpdns.org/2026/07/9d12634fa5adfaa65e78c6126b2fae87.png" alt="屏幕截图 2026-07-20 104035" style="zoom:80%;" />

## ✨ 核心特性

- 🎯 **强相关模式 (Strict Match)**：动态抓取你的搜索关键词。如果视频标题未包含搜索词，直接将其屏蔽！彻底解决算法“挂羊头卖狗肉”的问题。
- 🚫 **多维黑名单拦截**：内置强大的正则表达式词库，覆盖「擦边/软色情」、「夸张标题党」、「无聊烂梗」三大类。只要命中，绝对消失。
- ⚡ **零延迟、无闪烁体验**：采用 `requestAnimationFrame` 结合 `MutationObserver` 钩子，在浏览器渲染画面前瞬间介入，将垃圾视频掐死在摇篮里，不会出现“先看到视频又消失”的闪烁感。
- 🔄 **完美支持无限下拉与翻页**：兼容B站最新的前端单页路由机制，无论怎么翻页，过滤器永不掉线。

## 📦 安装说明

1. 确保你的浏览器已安装 [Tampermonkey](https://www.tampermonkey.net/) 插件。
2. 点击此处一键安装脚本：**[GreasyFork 安装链接](https://greasyfork.org/zh-CN/scripts/587793-b%E7%AB%99%E6%90%9C%E7%B4%A2%E7%BB%93%E6%9E%9C%E7%BA%AF%E5%87%80%E7%89%88-%E5%BC%BA%E7%9B%B8%E5%85%B3-%E5%8E%BB%E6%93%A6%E8%BE%B9)**

## 🛠️ 自定义配置

如果你想添加自己讨厌的词汇或UP主，只需在油猴管理面板中编辑本脚本，修改以下两处即可：

```javascript
// 扩充屏蔽词
const BLACKLIST_WORDS = [
    /你的屏蔽词1/, /你的屏蔽词2/
];

// 屏蔽特定UP主
const BLACKLIST_UP_NAMES = [
    "讨厌的UP主A", "讨厌的UP主B"
];
