# OpenMausBot session base

- **Date:** 17 Aug 2026
- **Live page:** https://plucky-basin-ze4g.here.now/ (password-gated)
- **Local HTML:** `~/Documents/openmausbot-session-base/site/`

Start here. Code stays in Herdr.

The Poppy fleet is the front desk for a work session. Herdr, Pi, and Grok Build still own the repo. A task on a bot is one session. Do not keep piling onto “A bit of everything.”

## MiniMax PR

Yes — the first PR had to go to the real repo.

| PR | Target | Status |
|---|---|---|
| [collectivewinca/OpenMausBot #1](https://github.com/collectivewinca/OpenMausBot/pull/1) | our fork | Ignore. 314 commits behind. Would drop Qwen, Hermes, Kimi, Droid, Antigravity. |
| [milind-soni/OpenMausBot #212](https://github.com/milind-soni/OpenMausBot/pull/212) | upstream `main` | Open. Ahead by 1, behind 0. MiniMax only. |

A PR on the fork is a note to ourselves. Only #212 can land in the app other people install.

## How to start a session

1. Open OpenMausBot. Do not reopen Poppy’s old “A bit of everything” thread.
2. New task on Poppy, or skip straight to the specialist.
3. First line is the job in one sentence.
4. When something has to land in a repo, move to Herdr. The bots do not share this workspace.

Flow: **New task → Name the job → Specialist (or Poppy routes) → Herdr only if files change → Sage writes the close.**

Paste this as the first message on a new Poppy task:

```
New session. Do not continue the old “A bit of everything” thread.

Job: [one sentence]

Route to the right specialist. Do not rewrite bots.json or any settings.json. Do not tell me to restart. Do not touch theme.
```

End the day in Sage: “Write down what we decided and what’s still open.”

## Who takes the session

| If the session is | Open | Engine |
|---|---|---|
| Unclear / several roles | Poppy, new task | `poppy` · grok-4.6 |
| Research / what’s going on | Scout | Grok, or DeepSeek Flash |
| Draft / announce / post | Buzz | claude-sonnet-5 |
| Intro / JD / outreach — no send | Zeus | claude-sonnet-5 |
| Secrets / leak check | Vault | claude-sonnet-5 |
| Remember what we decided | Sage | claude-sonnet-5 |
| MINY / mixtape / catalog | Vinyl | claude-sonnet-5 |
| Markets | Odds | grok-4.6 |
| Code / scripts / glue | Forge | `glm` · GLM 5.2 |

## Extra model subs

These sit in the model picker on every bot. They are instances, not extra sidebar bots.

| Instance | Source | Model | State 17 Aug |
|---|---|---|---|
| `deepseek` | Ollama Cloud | deepseek-v4-flash | Works |
| `glm` | Ollama Cloud | glm-5.2 | Works · Forge uses this |
| `qwen` | Alibaba token plan | qwen3.8-max | 429 · quota resets 19 Aug 18:25 UTC |

Do not put Qwen on a session until the plan resets. The DashScope standard key is invalid, so there is no backup Qwen path.

## What is in a repo

| Thing | Where |
|---|---|
| App source | [milind-soni/OpenMausBot](https://github.com/milind-soni/OpenMausBot) |
| Installed DMG | [openmausbot-releases](https://github.com/milind-soni/openmausbot-releases) · we are on 0.1.20, latest is 0.1.23 |
| Our fork | [collectivewinca/OpenMausBot](https://github.com/collectivewinca/OpenMausBot) |
| MiniMax that can ship | [upstream PR #212](https://github.com/milind-soni/OpenMausBot/pull/212) |
| Fork-only MiniMax (ignore) | [fork PR #1](https://github.com/collectivewinca/OpenMausBot/pull/1) |
| Sidebar bots + instances | `~/.openmausbot/` on this Mac. Not in git. |
| Picker labels for DeepSeek/GLM/Qwen | Local edit in the app `grok` driver. An update wipes it. |

Theme cannot be changed. The UI is hardcoded dark. Poppy once edited Gemini CLI settings instead.

## Do not

- Rewrite `~/.openmausbot/bots.json` from a shell while the app is running. The in-memory store will overwrite it.
- Create bots except through `POST /api/bots` then `PATCH`.
- Edit `~/.gemini/settings.json` for an OpenMausBot theme.
- Point Poppy at `scout`. Poppy stays on instance `poppy`.
- Treat the fork PR as submitted to the product.
