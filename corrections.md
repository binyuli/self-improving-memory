# Corrections Log

## [2026-03-16] Preference: Active Skill Usage
**Context**: User requested to actively use self-improving skill after installation
**User said**: "装完之后你要在做日常任务过程中把它用起来，我太喜欢了"
**Action**: Will actively record corrections, preferences, and self-reflections
**Pattern**: First occurrence (1/3 for promotion)


## [2026-03-16] Feedback: Response Latency
**Context**: User asked "查屁眼里去了？" indicating frustration with slow response
**Issue**: Took too long to complete installation task due to ClawHub rate limit
**Better approach**: Should have notified user immediately when hitting rate limit, instead of silently retrying
**Pattern**: First occurrence (1/3 for promotion)


## [2026-03-16] Workflow: GitHub & ClawHub Management
**Context**: User asked to publish skills to ClawHub instead of GitHub
**User said**: "我突然想起我是不是可以将我的skill upload到clawhub，不用放到github"
**Lesson**: ClawHub is the dedicated platform for skill publishing, not GitHub
**Action**:
  - Created two separate private repos for different purposes
  - Published 4 skills successfully to ClawHub
  - 5 skills failed due to slug conflicts (already taken)
  - Used `clawhub publish --version "1.0.0" for all skills
**Pattern**: First occurrence (1/3 for promotion)

## [2026-03-16] Feedback: Response Latency (Reinforced)
**Context**: User expressed frustration with slow response again
**User said**: "查屁眼里去了？"
**Issue**: Rate limit at ClawHub caused delays
**Lesson**: Always notify user immediately when hitting rate limit
**Pattern**: Second occurrence (2/3 for promotion) - **PROMOTE TO MEMORY.md**

## [2026-03-16] Preference: Public Repositories for China Access
**Context**: User needs to clone repos from mainland China server
**User said**: "把这俩仓库暂时设为public,不然我国内服务器clone不下来"
**Action**: Changed both `self-improving-memory` and `lobster-skills` to PUBLIC
**Note**: Temporary change for easier access; can revert to private later
**Pattern**: First occurrence (1/3 for promotion)

## [2026-03-16] Feedback: Clarify Intent Earlier
**Context**: User was confused about session/template requests
**User said**: "你们不同机器上的龙虾之间能不能共享技能和关于我的记忆"
**Issue**: Assistant didn't understand the actual need initially
**Lesson**: Ask for clarification when ambiguous requests arise
**Pattern**: First occurrence (1/3 for promotion)
