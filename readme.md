# FastCraftX - EagercraftX1.8逆向开发资源库

⚠️ 逆向工程研究 | 仅供学习参考 | 请遵守相关法律法规

## 🔍 项目概述
本项目是对 Eaglercraft Minecraft 1.8 浏览器版客户端的逆向工程研究成果，包含逆向分析工具、解码工具以及处理后的核心文件。

## 📦 逆向内容

### 1. 核心文件
- decompressed_bundle.js - 逆向提取并解压的游戏核心逻辑
- 签名分析 - Eaglercraft 客户端签名验证机制分析
- 资源包结构 - 游戏资源文件 (.epk) 格式解析

### 2. 逆向工具
- Base64 解码器 (base64.html) - 完整的数据提取工具
- GZIP 解压支持 - 浏览器端直接解压压缩数据
- 文件类型识别 - 自动识别 Eaglercraft 文件格式

## 🛠️ 逆向工具功能

### Base64 解码器 (base64.html)
 
** 功能特性 **：
✅ 提取 data:URL 中的纯 base64 数据
✅ 解码 Eaglercraft 签名文件
✅ 解压 GZIP 压缩的 bundle 文件
✅ 文件类型自动识别
✅ 十六进制预览与文本预览
✅ 文件下载支持
  

### 解码流程
 
原始 base64 数据 → 提取纯 base64 → 解码为 ArrayBuffer →
→ 识别文件类型 → 如为 GZIP 则解压 → 获取可读内容
  

## 🔬 技术分析

### 文件结构分析
 
** Eaglercraft 客户端结构 **：
 
1. 签名文件 (signature) - 验证客户端完整性
2. Bundle 文件 - GZIP 压缩的 JavaScript 核心
3. 资源文件 (.epk) - 游戏纹理、声音等资源
4. 配置参数 - 中继服务器、游戏设置等
  

### 启动机制分析

1. 加载签名验证
2. 解码 base64 bundle
3. GZIP 解压核心代码
4. 初始化 WebSocket 连接
5. 加载游戏资源
6. 启动 Minecraft 客户端
 
## 🚀 使用说明
 
### 快速开始
 
1.使用解码工具分析原始数据
2.将解压后的文件保存为 decompressed_bundle.js
3.配置中继服务器参数
4.启动游戏客户端
 
### 解码工具使用

打开 base64.html 即可使用可视化工具：
1. 粘贴签名数据
2. 上传 bundle 文件
3. 点击解码按钮
4. 查看分析结果

 
## ⚙️ 配置参数
 
** 逆向发现的配置选项（官方文档中也有） **
 
```javascript
window.eaglercraftXOptsHints = {
    hintsVersion: 1,                     // 配置版本
    container: "game_frame",             // 游戏容器
    assetsURI: "assets.epk",             // 资源文件路径
    worldsDB: "worlds",                  // IndexedDB 数据库名
    enableDownloadOfflineButton: false,  // 离线下载按钮
    relays: [],                          // WebSocket 中继服务器
    checkRelaysForUpdates: true,         // 检查中继更新
    showBootMenuOnLaunch: false          // 启动时显示菜单
};
```
 
## 🔍 逆向发现
 
### 关键发现
 
1. 数据编码：采用 base64 嵌套 GZIP 的双重编码
2. 验证机制：客户端签名验证防止篡改
3. 网络协议：基于 WebSocket 的自定义协议
4. 资源加载：动态加载压缩资源包
 
### 文件格式
  
签名文件格式：EAGSIG (魔数: 45 41 47 53)
Bundle 格式：GZIP 压缩的 JavaScript
资源包格式：自定义 .epk 格式

 
## ⚠️ 法律声明
 
### 重要声明
  
1. 本项目仅供技术研究和学习使用
2. 请勿用于商业用途或非法目的
3. 尊重原始项目的知识产权
4. 使用者需自行承担相关责任

 
### 使用限制
 
- ❌ 不得用于破解或绕过付费功能
- ❌ 不得用于盗版或侵权用途
- ❌ 不得用于攻击或破坏服务
- ✅ 仅可用于学习和研究目的
 
 
## 🤝 贡献指南
 
** 欢迎提交 **：
 
- 新的逆向发现
- 改进的解码工具
- 技术分析文档
- Bug 修复和建议

### 求助
- 外部调用bundle反馈无法解码的问题
- bundle 过大导致无法完全反编译/反混淆的问题
 
## 📄 许可证
 
本项目作为逆向工程研究项目，使用MIT协议，遵循** 仅供学习研究 **的原则，不包含任何商业用途代码。
 
 Copyright 2025 FastNow Studio
