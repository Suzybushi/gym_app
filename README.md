[中文](README.md) | [English](README.en.md)

# 铁馆 · 训练记录

一个零依赖、单文件、打开即用的健身训练记录 Web App（PWA 风格）。数据只保存在浏览器 `localStorage`，无账号、无后端、不上传数据；首次打开页面需要联网加载。

## 功能

- **两套内置计划**
  - 推-拉-腿-休 四日力量计划（231 协议）
  - Left AIC + Right BC 修复计划（B1 / B2 / 休息循环 + 每日 A 碎片保底）
- **训练记录**：力量动作记录重量 / 次数；修复动作按组勾选完成；按日期保存
- **替代动作**：一键切换动作变体，记录互不干扰
- **沿用上次**：力量动作自动显示上次数据，可一键填入
- **修复计划专属**：完整技术要点、时长类动作倒计时（静压 / 拉伸 / 行走等）、按组完成勾选
- **每日营养估算**：按体重与目标（增肌 / 塑型 / 减重）计算热量与三大营养素
- **计划导入**：粘贴训练计划文本（表格、编号、圆点、Markdown 标题均可），自动解析成 Day / 动作
- **数据备份**：导出 / 导入 JSON 备份，换设备可恢复
- **跨平台**：Windows / iOS / Android 的现代浏览器均可使用；iOS Safari 和 Android Chrome 可添加到主屏幕

## 兼容性

- **Windows**：Chrome / Edge / Firefox
- **iOS**：Safari（可添加到主屏幕）
- **Android**：Chrome / Edge / Firefox（可添加到主屏幕）
- 无需安装原生客户端，浏览器打开即用。

## 计划理念

内置的修复计划参考了以下两类矫正性训练理念：

- **CES（Corrective Exercise Specialist，NASM 矫正性训练）**：抑制 → 拉长 → 激活 → 整合
- **PRI（Postural Restoration Institute）**：Left AIC / Right BC、ZOA（Zone of Apposition）、沉左肋 / 松右链

本计划是个人训练方案，不代表 NASM、PRI 或任何机构的官方认证、课程或治疗方案，也不构成医疗建议。

## 在线使用

https://suzybushi.github.io/gym_app/

## 本地运行

直接双击 `index.html` 通常可用。如果浏览器限制 `file://` 下的 `localStorage`，改用下面的本地服务器：

```bash
python -m http.server 8000
```

然后打开 http://localhost:8000/

## 使用说明

1. 首次启动选择一套内置计划，或粘贴导入自己的计划。
2. 顶部日期条可校准「今天是第几天」：力量计划是 Day A/B/C/D，修复计划是 B1/B2/休。
3. 点动作卡展开：力量动作填写重量 / 次数；修复动作按组勾选完成。
4. 修复计划每天都有「碎片保底 · 方案 A」卡片，休息日默认展开。
5. 右上角 `＋` 可切换内置计划或导入新计划；`⬇` 导出全部数据备份。

## 数据与隐私

- 存储位置：浏览器 `localStorage`，key 为 `gymlog.v1`
- 不上传服务器，无账号、无追踪
- 换手机或换网址时，用 app 内的「导出数据备份 / 导入数据备份」迁移
- 清除浏览器网站数据会丢失训练记录

## 项目结构

```
index.html      # 全部 UI、样式、数据与逻辑
.quality-pass   # 本地提交前的质量门禁凭证，运行 app 不需要
README.md       # 中文说明
README.en.md    # English version
```

无构建步骤，无 npm 依赖。

## 部署到 GitHub Pages

1. 打开仓库 **Settings → Pages**
2. **Source** 选择 `Deploy from a branch`
3. **Branch** 选 `main`，**Folder** 选 `/ (root)`
4. 点 **Save**，等待 1~3 分钟
5. 访问 https://suzybushi.github.io/gym_app/

> GitHub Pages 对 private 仓库可能需要付费计划；如果无法使用，可以把 `index.html` 拖到 Netlify Drop 等静态托管服务。

## 免责声明

本项目是个人训练记录工具，不构成医疗建议。内置计划参考 CES 与 PRI 理念，但不代表 NASM、PRI 或任何机构的官方认证或背书。训练中出现疼痛或不适，请停止并咨询专业人士。
