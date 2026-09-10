# 🌐 BiliTool-ZH

**BiliBiliToolPro 的中文汉化自用版**（Web 界面简体中文 + B 站粉色风格美化）。

## 来源

基于 [RayWangQvQ/BiliBiliToolPro](https://github.com/RayWangQvQ/BiliBiliToolPro)（GPL-3.0）汉化，仅修改 Web 管理界面文案与样式，**零功能改动**。版权归原作者 **RayWangQvQ** 所有。

## 汉化内容

- 导航菜单、登录页、首页仪表盘
- 任务调度表：任务名（每日任务/漫画任务/充电/银瓜子换硬币等）、触发器类型、状态、操作按钮
- 历史/日志弹窗、错误页、修改密码页
- B 站主题色（#FB7299）UI 美化

## 自用部署

```bash
mkdir -p config Logs
docker build -t bili_tool_web_cn:latest .
docker run -d --name bili_tool_web \
  -p 22330:8080 \
  -e TZ=Asia/Shanghai \
  -v $(pwd)/Logs:/app/Logs \
  -v $(pwd)/config:/app/config \
  --restart unless-stopped \
  bili_tool_web_cn:latest
```

访问 `http://<服务器IP>:22330`，默认 `admin / BiliTool@2233`（登录后请改密码）。

## 致谢

由 **Hermes Agent**（Nous Research 开源智能体，主模型 DeepSeek-V4-Flash）协助完成。原项目：https://github.com/RayWangQvQ/BiliBiliToolPro
