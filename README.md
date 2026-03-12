# humanizer-plugin

A Claude Code plugin that removes AI writing patterns from text and makes it sound natural and human-written. Based on Wikipedia's comprehensive "Signs of AI writing" guide, maintained by WikiProject AI Cleanup.

---

## Install

Run this command inside Claude Code terminal:

```bash
/plugin install https://github.com/devsharma-source/humanizer-plugin
```

That's it. No manual file copying, no configuration needed. The `/humanizer` command will be available immediately after installation.

---

## Usage

```
/humanizer

[paste your text here]
```

Or ask Claude directly:

```
Please humanize this text: [your text here]
```

---

## What it does

The humanizer reads your text, identifies AI writing patterns, rewrites the problematic sections, and runs a final audit pass to catch anything that still sounds artificial.

It goes through two rounds:

1. **Draft rewrite** — fixes all identified patterns
2. **Audit pass** — asks "what still makes this obviously AI generated?" and revises again
3. **Final output** — clean, natural-sounding text with a brief summary of changes

---

## 24 patterns it removes

### Content patterns
| # | Pattern | Example before | Example after |
|---|---------|----------------|---------------|
| 1 | Significance inflation | "marking a pivotal moment in the evolution of..." | "was established in 1989 to collect regional statistics" |
| 2 | Notability name-dropping | "cited in NYT, BBC, FT, and The Hindu" | "In a 2024 NYT interview, she argued..." |
| 3 | Superficial -ing analyses | "symbolizing... reflecting... showcasing..." | removed or replaced with sourced facts |
| 4 | Promotional language | "nestled within the breathtaking region" | "is a town in the Gonder region" |
| 5 | Vague attributions | "Experts believe it plays a crucial role" | "according to a 2019 survey by..." |
| 6 | Formulaic challenges section | "Despite challenges... continues to thrive" | specific facts about actual challenges |

### Language patterns
| # | Pattern | Example before | Example after |
|---|---------|----------------|---------------|
| 7 | AI vocabulary words | "Additionally... testament... landscape... showcasing" | plain alternatives |
| 8 | Copula avoidance | "serves as... features... boasts" | "is / has" |
| 9 | Negative parallelisms | "It's not just X, it's Y" | state the point directly |
| 10 | Rule of three overuse | "innovation, inspiration, and insights" | natural number of items |
| 11 | Synonym cycling | "protagonist... main character... central figure" | repeat the clearest word |
| 12 | False ranges | "from the Big Bang to dark matter" | list topics directly |

### Style patterns
| # | Pattern | Example before | Example after |
|---|---------|----------------|---------------|
| 13 | Em dash overuse | "institutions -- not the people -- yet this continues --" | commas or periods |
| 14 | Boldface overuse | "**OKRs**, **KPIs**, **BMC**" | "OKRs, KPIs, BMC" |
| 15 | Inline-header lists | "**Performance:** Performance improved..." | converted to prose |
| 16 | Title Case Headings | "Strategic Negotiations And Partnerships" | "Strategic negotiations and partnerships" |
| 17 | Emojis in copy | "🚀 Launch Phase: 💡 Key Insight:" | removed |
| 18 | Curly quotation marks | curly "..." | straight "..." |

### Communication patterns
| # | Pattern | Example before | Example after |
|---|---------|----------------|---------------|
| 19 | Chatbot artifacts | "I hope this helps! Let me know if..." | removed entirely |
| 20 | Cutoff disclaimers | "While details are limited in available sources..." | removed or sourced |
| 21 | Sycophantic tone | "Great question! You're absolutely right!" | respond directly |

### Filler and hedging
| # | Pattern | Example before | Example after |
|---|---------|----------------|---------------|
| 22 | Filler phrases | "In order to", "Due to the fact that" | "To", "Because" |
| 23 | Excessive hedging | "could potentially possibly be argued" | "may" |
| 24 | Generic conclusions | "The future looks bright. Exciting times lie ahead." | specific plans or facts |

---

## AI vocabulary word list

These words appear far more frequently in AI-generated text post-2023. The humanizer flags and replaces them:

`Additionally` `align with` `crucial` `delve` `emphasizing` `enduring` `enhance` `fostering` `garner` `highlight` `interplay` `intricate` `intricacies` `key` (as adjective) `landscape` (abstract) `pivotal` `showcase` `tapestry` (abstract) `testament` `underscore` `valuable` `vibrant`

---

## Adding personality (not just removing patterns)

Removing AI patterns is only half the job. The humanizer also adds voice:

- Varies sentence rhythm (short punchy sentences mixed with longer ones)
- Adds opinions and reactions, not just neutral reporting
- Acknowledges complexity and uncertainty where appropriate
- Uses first person when it fits the context
- Replaces vague claims with specific details

---

## Requirements

- Claude Code (terminal version) installed
- No additional dependencies

---

## Source

Skill logic based on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.
