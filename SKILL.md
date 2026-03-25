---
name: iran-oil-conflict-monitor
description: Use this skill when the user wants current, web-verified information about US-Iran conflict developments, Strait of Hormuz tanker traffic, statements from the US president or Iranian leaders, Trump posts on Truth Social or related social platforms, sanctions or military escalation, and an analysis of how those developments may affect Brent, WTI, or broader crude oil prices. Also use it for Chinese requests about “美伊冲突”, “霍尔木兹”, “油轮通过量”, “特朗普/美国总统讲话/推文/发帖”, “伊朗最高领袖讲话”, and oil-price impact analysis.
---

# Iran Oil Conflict Monitor

## Overview

Use this skill to turn fast-moving US-Iran conflict news into a market-oriented crude oil impact note. The skill is for current-event monitoring, not historical essays, so it should verify live information on the web before drawing conclusions.

## When To Use It

Use this skill when the request involves one or more of the following:

- Current US-Iran military, diplomatic, or sanctions developments
- Strait of Hormuz shipping flow, tanker delays, insurance risk, or transit disruptions
- Statements by the US president, the White House, Iran's supreme leader, Iran's president, or Iran's foreign ministry
- Trump social posts, “特朗普推文”, Truth Social posts, reposts, or platform-verification requests
- Market interpretation for Brent, WTI, Middle East sour crude, tanker rates, or oil risk premium
- Chinese monitoring requests about “美伊冲突” and the impact on crude prices

## Core Workflow

### 1. Define the market question first

Before searching, identify:

- Time window: default to the last 24 to 72 hours unless the user requests another range
- Market lens: spot reaction, 1- to 5-day trading impact, or medium-term supply outlook
- Instruments: Brent, WTI, Dubai/Oman, oil tanker rates, or general crude risk sentiment

### 2. Gather information in priority order

Always browse for current information. Prefer primary or highly authoritative sources first, then use major wire services to confirm market relevance.

Priority order:

1. Official statements and transcripts
2. Trump original social posts and official platform pages
3. Shipping / chokepoint / tanker-flow data
4. Major wire reporting that ties events to market reaction
5. Direct price checks for Brent and WTI

Read [references/source-map.md](references/source-map.md) for source priorities.

### 3. Verify before interpreting

For each major claim, try to confirm at least one of these:

- Exact quote or transcript from an official source
- A second independent report from a major wire service
- A data source or analyst note that quantifies tanker flow, delays, exports, or price moves

If a claim is not independently confirmed, label it clearly as unconfirmed or preliminary.

### 4. Convert events into oil-market channels

Map each development into one or more transmission channels:

- Physical supply risk: export losses, production outages, sanctions tightening
- Transit risk: Strait of Hormuz closures, inspections, rerouting, slower convoying, insurance costs
- Political risk premium: threats, retaliation warnings, military deployments
- De-escalation pressure: ceasefire talks, back-channel diplomacy, toned-down rhetoric
- Demand / macro offset: risk-off growth fears, stronger USD, recession concerns

### 5. Produce an explicit impact view

State the likely direction and strength of impact:

- Bullish for oil
- Bearish for oil
- Short-term spike risk only
- Headline noise with limited fundamental impact

Then explain whether the effect is:

- Immediate but likely to fade
- Likely to persist for several sessions
- Structural if it materially changes exports or shipping access

## Output Format

Default to a short market note in fixed morning-note format unless the user asks for another style.

### Morning Note Template

Use this structure and keep the headings stable:

```markdown
# 美伊冲突与原油市场晨报

## 一句话结论
- [一句话概括今日对油价的核心判断]

## 今晨核心变化
- [变化1：事件 + 时间 + 对油价含义]
- [变化2：事件 + 时间 + 对油价含义]
- [变化3：事件 + 时间 + 对油价含义]

## 关键事实核验
| 类别 | 最新情况 | 时间 | 对油价传导 | 可信度 |
| --- | --- | --- | --- | --- |
| 霍尔木兹通行 | [当前通过量/拥堵/是否扰动] | [时间] | [供应/运输/风险溢价] | [高/中/低] |
| 美国表态 | [总统/白宫/财政部核心表态] | [时间] | [升级/缓和/制裁] | [高/中/低] |
| 伊朗表态 | [最高领袖/总统/外交部核心表态] | [时间] | [升级/缓和/报复风险] | [高/中/低] |
| 市场表现 | [Brent/WTI方向或幅度] | [时间] | [验证还是背离] | [高/中/低] |

## 利多/利空量化评分
- 综合得分：**[+5 到 -5]**
- 结论标签：**[强利多 / 偏利多 / 中性 / 偏利空 / 强利空]**
- 核心驱动：[供应中断 / 航运受阻 / 制裁升级 / 口头威胁 / 缓和信号 / 宏观压制]

## 评分拆解
| 维度 | 观察 | 分值 |
| --- | --- | --- |
| 实际供给风险 | [是否影响真实出口桶数] | [-2 到 +2] |
| 霍尔木兹运输风险 | [是否出现延误/扣押/绕航/保险上升] | [-2 到 +2] |
| 美方政策与军事动作 | [制裁/部署/打击/降温] | [-1 到 +1] |
| 伊方表态与行动 | [威胁/克制/实际行动] | [-1 到 +1] |
| 市场已计价程度 | [若消息已被市场提前消化可减分] | [-1 到 +1] |

## 市场影响分析
- Brent： [偏多 / 中性 / 偏空]，原因：[...]
- WTI： [偏多 / 中性 / 偏空]，原因：[...]
- 持续性： [日内脉冲 / 1-3日 / 多日持续]
- 性质： [风险溢价主导 / 基本面主导 / 两者叠加]

## 三种情景
- 基准情景： [...]
- 利多情景： [...]
- 利空情景： [...]

## 风险提示
- [未核实信息]
- [数据滞后]
- [翻译口径偏差]

## 信息来源
- [来源1]
- [来源2]
- [来源3]
```

If the user asks for English, keep the same structure but translate the headings.

## Quant Scoring Rules

Always provide a score when the user asks for price impact, even if the evidence is mixed.

### Score Range

- `+4` to `+5`: strong bullish for oil
- `+2` to `+3`: moderately bullish for oil
- `-1` to `+1`: neutral / mixed / mostly headline noise
- `-2` to `-3`: moderately bearish for oil
- `-4` to `-5`: strong bearish for oil

### Factor Weights

Start at `0`, then add or subtract:

- Actual supply disruption: `+2` if confirmed export or production loss, `+1` if credible near-term risk, `0` if none
- Strait of Hormuz transit disruption: `+2` if confirmed obstruction or seizures affecting flow, `+1` if delays / insurer warnings / escorts rise, `0` if traffic remains normal, `-1` if disruption fears clearly ease
- US policy / military signal: `+1` for sanctions tightening or clear military escalation, `0` for rhetoric only, `-1` for explicit de-escalation
- Iranian signal / action: `+1` for credible retaliation threat or operational action, `0` for rhetoric only, `-1` for clear restraint or conciliatory signaling
- Market pre-pricing adjustment: `-1` if the event appears heavily priced in already, `0` if unclear, `+1` if the market is clearly underpricing the development

Clamp the final score to the `-5` to `+5` range.

### Label Mapping

- `+4` to `+5`: 强利多
- `+2` to `+3`: 偏利多
- `-1` to `+1`: 中性
- `-2` to `-3`: 偏利空
- `-4` to `-5`: 强利空

### Scoring Discipline

- Do not give a high bullish score based on speeches alone unless there is a credible operational channel
- Reduce the score when shipping data, export flows, and official actions do not confirm the rhetoric
- If Brent / WTI initially spike but quickly retrace, mention that the score may reflect fading risk premium rather than durable tightness
- If facts conflict, keep the score near neutral and explain the disagreement instead of forcing conviction

## Analysis Heuristics

Use these rules of thumb:

- Direct threats to close or harass traffic in the Strait of Hormuz are usually bullish for oil even before any confirmed closure
- Confirmed disruption to tanker transit matters more than rhetoric alone
- Official US or Iranian statements matter most when they imply immediate military action, sanctions enforcement, or de-escalation
- A sharp intraday oil move without corresponding shipping or supply evidence may be mainly a risk-premium move
- If the market is already pricing in escalation, repeated rhetoric can have diminishing price impact

## Special Guidance For Statements

For US statements, prefer:

- White House transcript pages
- Remarks, press briefings, executive orders, and presidential statements
- US Treasury sanctions releases when sanctions are part of the story

For Trump social posts, prefer:

- Truth Social official account pages for `@realDonaldTrump` when accessible
- Official campaign or presidential pages that embed or reproduce the post
- Major wire reports that explicitly quote a Truth Social post and timestamp it
- X only as a secondary signal unless the post is clearly from Trump's official account and can be verified as original rather than reposted commentary

For Iranian statements, prefer:

- khamenei.ir
- president.ir
- mfa.gov.ir
- IRNA

If the authoritative source is in Persian, rely on an official English page when available. Otherwise, use a major wire service translation and say that the wording is mediated through translation.

## Special Guidance For Trump Posts

When the user asks where Trump is posting or wants “特朗普推文”, treat the question as platform verification first and content retrieval second.

Current default assumption:

- Trump's primary posting platform is Truth Social
- X may contain official account activity, reposts, clips, or mirrored content, but should not be assumed to be the primary source without verification

Search workflow:

1. Look for the original post on Truth Social or an official page that embeds it
2. Confirm date and exact wording through a major wire service if the Truth Social page is inaccessible
3. Check whether the same message also appeared on X, and label it as cross-posted, mirrored, or unverified if needed
4. In the answer, distinguish clearly between:
   - original Trump post
   - media paraphrase of the post
   - repost / screenshot / clip shared by others

When reporting platform findings, explicitly say:

- where he primarily posts now
- whether the cited item is a Truth Social original
- whether an X version exists
- whether the wording comes from the original platform or from press quotation

## Special Guidance For Hormuz / Shipping

When the user asks about “霍尔木兹当前油船通过量” or similar, separate:

- Baseline capacity / historical importance
- Current traffic estimates
- Actual disruption signs such as queues, rerouting, AIS gaps, naval escorts, seizures, or insurer warnings

Do not present rough social-media ship counts as hard fact unless corroborated by a reputable shipping or wire source.

## What Good Answers Look Like

Good answers are:

- Current and source-linked
- Clear about what is verified versus inferred
- Focused on oil transmission channels, not just geopolitics
- Honest about uncertainty

Bad answers:

- Treat any speech as equally market-moving
- Ignore whether barrels are actually at risk
- Skip timestamps
- Mix rumors with verified developments
