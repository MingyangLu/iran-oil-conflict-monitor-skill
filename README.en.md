# Iran Oil Conflict Monitor

`iran-oil-conflict-monitor` is an intelligence and market-analysis skill designed for crude oil workflows. It tracks US-Iran conflict developments, Strait of Hormuz shipping conditions, Trump and US official statements, Iranian leadership statements, and the likely impact of those events on `Brent`, `WTI`, and broader oil risk premium.

Its goal is not to produce generic news summaries. Instead, it turns fast-moving geopolitical information into output that looks closer to a sell-side morning note or a trading-desk briefing, with strong emphasis on verification, timestamps, source quality, and oil-market transmission channels.

## Use Cases

- Monitor the latest US-Iran conflict developments over the past 24 to 72 hours
- Track tanker, LPG carrier, delay, and reopening signals in the Strait of Hormuz
- Retrieve Trump's latest Iran-, Middle East-, or oil-related posts and public remarks
- Verify statements from Iran's supreme leader, president, foreign ministry, parliament speaker, and other senior officials
- Assess the likely impact on `Brent`, `WTI`, and shipping-related risk premium
- Generate a fixed-format morning note with a bullish/bearish scoring model

## Core Capabilities

- Prioritizes official sources and major media confirmation
- Incorporates Trump's social-post workflow, with `Truth Social` treated as the primary platform
- Separates real physical-supply disruption from pure headline-driven risk premium
- Uses a fixed morning-note template for consistent output
- Provides a `-5` to `+5` oil-impact score mapped to strong bullish / bullish / neutral / bearish / strong bearish

## Source Priority

1. Official US and Iranian pages
2. Trump's original posting platform and verifiable reproductions
3. Shipping and Strait-of-Hormuz flow reporting
4. Market-relevant confirmation from Reuters, AP, Bloomberg, WSJ, FT, and similar outlets
5. Latest `Brent` / `WTI` price action

## Default Output

By default, the skill generates a fixed-format Chinese morning report with sections such as:

- One-line conclusion
- Key overnight changes
- Verified facts table
- Bullish / bearish quantitative score
- Score breakdown
- Market impact analysis
- Scenario view
- Risk notes
- Source links

The structure can also be translated to English if requested.

## Scoring Logic

The score starts at `0` and is adjusted using these dimensions:

- Real supply disruption risk
- Strait of Hormuz transit risk
- US policy and military signaling
- Iranian signaling and actions
- Whether the market has already priced in the event

The final score is clamped between `-5` and `+5`:

- `+4` to `+5`: Strong Bullish
- `+2` to `+3`: Moderately Bullish
- `-1` to `+1`: Neutral
- `-2` to `-3`: Moderately Bearish
- `-4` to `-5`: Strong Bearish

## Example Prompts

```text
Use $iran-oil-conflict-monitor to review the latest 48-hour US-Iran developments, focusing on Strait of Hormuz tanker traffic, White House remarks, and statements from Iranian leaders, then assess the likely impact on Brent and WTI.
```

```text
Use $iran-oil-conflict-monitor to generate today's morning note with a bullish/bearish score, and explain whether Trump's latest Truth Social posts are affecting oil prices.
```

```text
Use $iran-oil-conflict-monitor to find Trump's latest Iran-related posts over the past 24 hours, prioritize original Truth Social posts, then check whether they were mirrored to X and assess the oil-market impact.
```

## File Structure

- `SKILL.md`
  Trigger description, workflow, report template, and scoring rules
- `references/source-map.md`
  Source priorities, judgment rules, and platform-verification guidance
- `agents/openai.yaml`
  UI metadata and default prompt

## Design Principles

- Verify first, interpret second
- Prefer original statements before media paraphrases
- Separate transport disruption from sentiment-driven trading
- Produce output that can be used directly in research or trading workflows
