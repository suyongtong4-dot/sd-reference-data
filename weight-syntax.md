# Prompt Weight Syntax

Weighting syntax is **per-interface**. The two syntaxes below belong to different tools and use different multipliers per level. Do not carry a number from one into the other.

## AUTOMATIC1111 / WebUI

| Syntax | Effect |
|---|---|
| `(term)` | Multiplies the term by roughly **1.1** |
| `[term]` | Divides by roughly the same (**~1.1**) |
| `((term))` | Nesting compounds, lands near **1.21** |
| `(term:1.3)` | Explicit value goes inside the parentheses with a colon |

## NovelAI

| Syntax | Effect |
|---|---|
| `{}` | Strengthens the term |
| Multiplier per level | **Not the same as WebUI** — the numbers above must not be carried across |

> The specific per-level multiplier for NovelAI is deliberately left out here rather than guessed. If you know it, a pull request is welcome.

## The range that works

| Boundary | What happens |
|---|---|
| Below **0.4** | The token gets ignored |
| **0.4 – 1.6** | Usable range |
| Above **1.6** | The model over-fits the concept and the frame starts to break |

**Weight decays left to right.** Put the landscape tag first and your subject shrinks — order matters as much as the numbers.

## Two failure modes worth knowing before you hit them

1. **Joining concepts with `AND` at equal weight tends to fuse them.** A prompt asking for cabbage and meat returned cabbage wrapped around meat. Comma separation or plain adjacency almost never does this.
2. **Pushing one element too high contaminates its neighbours.** A test prompt that raised several hair colours at once produced a frame where the whole composition fell apart.

## Before you reach for heavier weighting

English morphology is not free — prompt parsers tokenize, and verb form changes output on its own. Describing a figure with `run` produced no running pose across the test batch; changing that single token to `running` produced the pose immediately, same model and same settings.

When an action will not appear, reach for the participle **before** reaching for brackets. It is cheaper and in practice works more often.
