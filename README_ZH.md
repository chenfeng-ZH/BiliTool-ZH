# BiliBiliToolPro 中文界面汉化版

[![GitHub Stars](https://img.shields.io/github/stars/RayWangQvQ/BiliBiliToolPro?style=flat-square)](https://github.com/RayWangQvQ/BiliBiliToolPro)

本项目是 [RayWangQvQ/BiliBiliToolPro](https://github.com/RayWangQvQ/BiliBiliToolPro) 的 **Web 界面中文化分支**，仅对 Web 管理界面的显示文案进行了简体中文汉化，**不修改任何功能逻辑**。

> ⚠️ **版权声明**：本项目基于原作者的 GPL-3.0 协议开源。原项目作者为 **RayWangQvQ**，原仓库地址：https://github.com/RayWangQvQ/BiliBiliToolPro
> 请尊重原作者权益，使用本分支时请保留原 LICENSE 与本说明。

## 汉化内容

- 🔤 **导航菜单**：首页、任务调度、配置（每日任务/漫画任务/漫画大会员/银瓜子换硬币/充电任务/大会员权益/大会员积分/直播抽奖/粉丝勋章/批量取关）、管理
- 🔐 **登录页 / 管理页**：用户名、密码、修改密码等全部汉化
- 📋 **任务调度页**：状态（运行中/空闲/已暂停）、任务名称、触发器、下次运行/上次运行、操作（立即触发/启用/禁用/历史）
- 📜 **历史/日志弹窗**：执行历史、错误详情、执行详情、日志终端、加载更多
- ℹ️ **其他**：错误页、未找到页面等

## 与原版的差异

- 仅修改 `src/Ray.BiliBiliTool.Web/Components/` 下 14 个 `.razor` 界面文件的显示文本
- 零功能改动，零依赖变更，与原版任务逻辑完全一致
- 配置页面（每日任务配置等）原版已是中文，未改动

## Docker 部署

```bash
# 方式一：一键构建并启动
git clone https://github.com/chenfeng-ZH/BiliTool-ZH.git
cd BiliTool-ZH
mkdir -p config Logs
wget -O config/cookies.json https://raw.githubusercontent.com/RayWangQvQ/BiliBiliToolPro/main/docker/sample/config/cookies.json
docker build -t bili_tool_web_cn:latest .
docker run -d --name="bili_tool_web" \
  -p 22330:8080 \
  -e TZ=Asia/Shanghai \
  -v $(pwd)/Logs:/app/Logs \
  -v $(pwd)/config:/app/config \
  --restart unless-stopped \
  bili_tool_web_cn:latest
```

访问 `http://<服务器IP>:22330`，默认账号 `admin` / 密码 `BiliTool@2233`（首次登录后请修改密码）。

> 提示：直接使用原版官方镜像 `ghcr.io/raywangqvq/bili_tool_web` 也可以运行本汉化，只需将代码中的 `.razor` 替换后自行构建。

## 授权协议

本项目遵循 **GPL-3.0** 协议，与原项目一致。任何使用、修改、分发本项目的代码，必须：
1. 保留原作者的版权声明与本 README 说明
2. 以相同的 GPL-3.0 协议开源
3. 注明修改内容

原项目所有者为 **RayWangQvQ**（https://github.com/RayWangQvQ），一切版权归原作者所有，本分支仅做汉化翻译。

## 致谢

🌐 本汉化版由 **Hermes Agent**（Nous Research 出品的开源 AI 智能体，https://hermes-agent.nousresearch.com ）协助完成，主模型：**DeepSeek-V4-Flash**，界面识别辅助：**Grok-4.6**。

## 免责声明

本工具仅用于学习和测试，请勿滥用。作者不对使用本工具产生的任何后果负责。请遵守 B 站用户协议。