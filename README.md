<div align="center">

# 网腾无限AI - 电商运营与爆款文案专家

**一个基于 Vue 3 + Vite + Vanilla CSS 构建的极简 AI 微应用，具备深色玻璃拟态自适应交互与微信端 H5 体验**

Vue 3 · TypeScript · Vite · Vanilla CSS · 开源协议 MIT

[![GitHub stars](https://img.shields.io/github/stars/WT-Agent/ai-dianshang?style=social)](https://github.com/WT-Agent/ai-dianshang)
[![GitHub license](https://img.shields.io/github/license/WT-Agent/ai-dianshang)](https://github.com/WT-Agent/ai-dianshang/blob/main/LICENSE)

[在线演示](#在线演示) · [快速启动](#快速启动) · [参与贡献](#参与贡献) · [支持一下](#支持一下)

</div>

## 关于我们

团队成员均来自 C9 等顶尖学府，在字节、腾讯、阿里的工程师组成，全职创业研发开源 AI 应用产品，让所有人感受 AI 的魅力。

本项目是网腾无限 AI 微应用的标准开发模版，内置了毛玻璃深色主题样式系统、移动端与 PC 端自适应响应式框架、API 中转代理配置与流量裂变逻辑。

**我们不搞概念，不卖课，只写能跑起来的代码。**

欢迎 Star、Fork、提 Issue，一起让这个项目变得更好用。

核心特性：
- **极简自适应交互**：提供毛玻璃质感的深色玻璃拟态自适应 Web 界面，高度适配移动端 H5 微信浏览器与 PC 体验。
- **一键零成本部署**：纯静态前端结构，支持零成本部署于 Vercel、GitHub Pages 或 CDN/OSS 静态托管服务。
- **安全开发代理**：本地开发支持使用个人 API 密钥发起代理请求，密钥由 Vite 服务器中转，无需担心前端泄露。
- **裂变解锁与留存**：内置微信朋友圈扫码分享拦截与额度重置机制，提升流量转化与留存。

## 4 大核心功能模块

1. **商品核心卖点与痛点爆破**：深入剖析目标人群核心痛点，提炼 3 个差异化超级卖点与买点利益承诺。
2. **高转化主图/详情页文案与主视觉规划**：设计 5 张主图文案与视觉构图建议，提供“痛点引发-产品解法-权威背书-促单闭环”黄金架构详情页。
3. **短视频种草脚本与黄金3秒吸睛开头**：提供 3 个高吸引力黄金 3 秒吸睛开头，搭配镜头画面、口播台词与 BGM 音效指导。
4. **直播间促成成交话术与限时优惠促单**：撰写主播逼单与助播双簧话术、价格锚点对比、限时赠品倒计时与库存紧迫感打造。

## 5 大 AI 评估指标

1. **文案转化力 (`copywritingConversion`)**：评估文案刺激消费决策与促进下单转化的综合爆发力。
2. **卖点清晰度 (`sellingPointClarity`)**：评估产品差异化核心卖点与利益点的传达精准度。
3. **流量钩子强度 (`trafficHookStrength`)**：评估黄金3秒吸睛开头与短视频/主图视觉抓人眼球的吸引力。
4. **平台规则合规度 (`platformCompliance`)**：评估文案是否符合各大电商平台广告法及违禁词合规要求。
5. **人群画像匹配度 (`customerPersonaMatch`)**：评估生成内容与目标客群痛点及消费心理的契合程度。

## 快速启动

### 1. 克隆项目
```bash
git clone https://github.com/WT-Agent/ai-dianshang.git
cd ai-dianshang
```

### 2. 安装依赖
项目强制使用 pnpm 作为包管理器：
```bash
pnpm install
```

### 3. 配置本地开发环境变量
复制并修改环境变量配置文件：
```bash
cp .env.example .env
```
根据微应用的功能类型，在 `.env` 中配置您的开发者密钥：
- `DEEPSEEK_API_KEY`: 您的 DeepSeek 开发者 API 密钥（用于文本生成任务）
- `DASHSCOPE_API_KEY`: 您的通义千问/通义万相开发者 API 密钥（用于多模态与生图任务）

### 4. 启动本地开发服务
```bash
pnpm dev
```
启动成功后在浏览器访问控制台输出的地址即可。

### 5. 生产构建打包
```bash
pnpm build
```
打包后生成的 `dist` 目录即为纯静态网页资源，可直接上传部署。

## 脚手架集成说明

本模板由私有总控仓库 `ai.wuxian.xyz` 中的 `@wuxian/cli` 脚手架统一管理，支持以下批量运维操作：

### 初始化或更新单个子项目

```bash
node bin/cli.js ai-dianshang
```

脚手架将自动：
1. 读取子仓库的 `README.md` 首行作为 Prompt 主题。
2. 注入 Vue 3 静态页面结构及标准配置文件。
3. 保留原有的 `.git` 配置与 `README.md`，不覆盖个性化内容。

### 批量同步所有子项目

```bash
node bin/cli.js all
```

将模板的最新变更（如 SSO 逻辑、额度控制）一键同步至全部 31 个子项目。

### Agent 配置维护接口

```bash
# 读取子项目配置
node bin/cli.js get ai-dianshang

# 写入/更新配置（支持热更新 prompt、model、title、temperature 等）
node bin/cli.js set ai-dianshang prompt "你是一位精通淘宝天猫、京东、小红书、抖音电商及拼多多等全平台算法与爆款逻辑的顶级电商运营与文案策划专家..."
node bin/cli.js set ai-dianshang model deepseek-chat
```

## 联系方式

- GitHub Issues: [提交反馈](https://github.com/WT-Agent/ai-dianshang/issues)
- 邮箱: us@wuxian.xyz

## 打赏支持

如果本项目对您有帮助，欢迎请作者喝杯咖啡。您的支持是持续维护与更新的动力。

<div align="center">

**微信支付** | **支付宝**
:---:|:---:
<img src="https://ai.wuxian.xyz/assets/tenpay.png" width="200" alt="微信支付"> | <img src="https://ai.wuxian.xyz/assets/alipay.png" width="200" alt="支付宝">

</div>

## 版权与许可

本项目基于 MIT License 开源协议。

Copyright (c) 2026. All rights reserved.
