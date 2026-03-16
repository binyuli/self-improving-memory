# OpenClaw 工作流 - 2026-03-16

## 重要决策

### Self-Improving 技能选择
**决策：** 选择 `self-improving`（ivangdavila）而不是 `actual-self-improvement`
**原因：**
- 更稳定（16个版本迭代 vs 新发布）
- 评分 1.298 vs 3.318（虽然评分较低，但成熟度高）
- OpenClaw 专用，开箱即用
- 无需 Python 脚本，纯 Markdown 结构

**第一次学习记录：** 用户要求"装完之后要在做日常任务过程中把它用起来，我太喜欢了"

### 仓库同步策略
**决策：** 创建两个独立的私有仓库
- `binyuli/self-improving-memory` - 自我学习记忆系统
- `binyuli/lobster-skills` - 自定义技能库

**临时调整：** 为方便国内服务器访问，两个仓库都设为 PUBLIC（2026-03-16 22:16）

**同步方式：**
\`\`\`bash
# 记忆仓库
cd ~/self-improving && git add . && git commit -m "Update memory" && git push

# 技能仓库
cd /tmp/lobster-skills && git add . && git commit -m "Update skills" && git push
\`\`\`

### ClawHub 技能发布
**成功发布（4个）：**
- doc-export@1.0.0 (k9709ssvcewc1xpe9y2nyqsqdx830sff)
- memos-memory-guide@1.0.0 (k9733q25r5qvkp7kw5kvz65vgx830kt7)
- skill-packager@1.0.0 (k975q52e8y6hwejytf3rtrsm9n830em2)
- traffic-monitor@1.0.0 (k97d528ns9d2we0f9j5fys5t698315pw)

**失败原因（5个）：** Slug 已被占用
- image-search (被 TobiasLee 占用)
- openclaw-backup (被 alex3alex 占用)
- openclaw-tavily-search (被 Jacky1n7 占用)
- self-improving (被原作者 ivangdavila 占用)
- skill-vetting (被 eddygk 占用)
- unsplash (被 Brokenwatch24 占用)

**替代方案：** 用户可以选择换 slug 发布或直接使用 GitHub 仓库

## 技术配置

### Fallback 模型优化
**调整原因：** 频繁出现 "network_error"（智谱 GLM-5 API 网络中断）
**新顺序：** glm-4.7 → glm-4.6 → glm-4.5-air
**影响：** Coding Plan 套餐支持，不额外扣费

### Network Error 问题
**诊断：**
- 错误来自 `agent/embedded`
- 调用 GLM-5 API 时网络中断
- 发生频率：最近几天十几次
**可能原因：**
1. 智谱 API 网络不稳定
2. GLM-5 思考模式响应时间长
3. 服务器（香港）到国内 API 的网络抖动

## 工作流程优化

### 技能管理
**发现：** ClawHub 是专门用于技能发布的平台
**最佳实践：**
- 直接发布到 ClawHub 而非 GitHub 仓库
- 使用 `clawhub publish` 命令
- 需要 version 字段（semver 格式）

### 用户反馈
**记录：** "查屁眼里去了？" - 响应慢的反馈
**改进：** 遇到 rate limit 应立即通知用户，而非静默重试

## 待办事项

- [ ] 决定是否将失败的技能换 slug 重新发布
- [ ] 完成国内服务器克隆两个仓库
- [ ] 可能需要将仓库改回 PRIVATE（根据安全需求）
