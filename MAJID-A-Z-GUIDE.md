# MAJID A-Z Guide — claude-mem (Reminder)

> This is a fork/copy on the Majid7692 account. Original repo: thedotmack/claude-mem.
> Original author/credit and Apache-2.0 license are preserved (see LICENSE).
> This copy does NOT claim the original code was written by Majid7692.
> Only change in this copy so far: this A-Z guide was added as a reminder, plus item A below (provider comparison).

## 1. Ye kya hai? (What is it)
Persistent memory compression system built for Claude Code. It captures what an agent does during sessions, compresses it with AI, and injects relevant context back into future sessions, so work continues even after a session ends or reconnects.

## 2. Benefits (Fayde)
- Context survives across sessions — dobara wahi kaam samjhana nahi parta.
- Progressive disclosure — pehle chhota index, phir detail, is se token bachat hoti hai (README ke mutabiq ~10x token savings by filtering before fetching).
- Smart search — 3-layer workflow: search -> timeline -> get_observations.
- Privacy control — `<private>` tags se sensitive content ko storage se exclude karo.
- Works with Claude Code, OpenClaw, Codex, Gemini, Hermes, Copilot, OpenCode and more.

## 3. Requirements (Zaroorat)
- Node.js 20.0.0 or higher
- Claude Code latest with plugin support (for Claude Code use)
- Bun and uv auto-installed if missing; SQLite bundled.

## 4. Install — A to Z
A. Upstream README / docs ko pehle check karo (docs.claude-mem.ai).
B. Single command install (Claude Code ke liye):
   ```
   npx claude-mem install
   ```
C. Ya plugin marketplace se:
   ```
   /plugin marketplace add thedotmack/claude-mem
   /plugin install claude-mem
   ```
   Phir Claude Code restart karo.
D. Doosre IDEs ke liye `npx claude-mem install --ide <name>` use hota hai, masalan opencode, t3code, antigravity, omp, pi — exact naam upstream docs se confirm karo.
E. Installer ke baad sign-in pooch sakta hai (email magic link). Sign-in ke baghair bhi `--provider` flag ya `CLAUDE_MEM_ONLINE_OPTIN=false` se install complete ho sakta hai (CI/non-interactive ke liye).

## 5. First use
- Naya session shuru karo — pichli sessions ka context automatically appear hoga.
- Memory search ke liye: pehle `search` se index lo, phir `timeline` se context dekho, phir sirf zaroori IDs ke liye `get_observations` lo. Poora data pehle hi mat uthao.

## 6. Safety — IMPORTANT (Personal data / API)
- Is repo me koi personal data, password, ya API key commit NAHI karni.
- Keys sirf local environment me rakho, kabhi GitHub par public mat karo.
- Screenshots opt-in hain, by default off — on karne se pehle socho ke screenshot me private cheez to nahi.
- `<private>` tag use karo jab content sensitive ho.

## 7. Item A — Local vs Cloud provider comparison (Added 2026-11-04, approved by MAJID)
Simple matlab: claude-mem ek diary hai, is diary ko chalane ke 3 tareeqay hain. Koi cheez khareedna zaroori nahi, ye sirf farq samajhne ke liye hai.

| Tareeqa | Kaise chalta hai | Kab theek hai |
|---|---|---|
| 1. claude-mem observer (hosted / cloud) | Email magic link se sign-in, card nahi chahiye, 30 din free trial. Trial khatam ho to automatically Anthropic plan par wapas, jab tak subscribe na karo. | Shuru me try karne ke liye, ya jab apni key lagana na chaho. |
| 2. Apni key — OpenRouter ya Gemini | Tumhari apni key, kharcha aur control tumhara. Key kabhi repo me nahi, sirf local environment me. | Lambi use ke liye, ya jab privacy aur cost apne haath me rakhni ho. |
| 3. Anthropic plan | Koi extra key nahi, seedha plan se chalta hai, plan ki limit ke andar. | Jab extra setup nahi chahiye aur plan hi kaafi ho. |

Sign-in skip karna ho to:
- `--provider` flag use karo, ya
- `CLAUDE_MEM_ONLINE_OPTIN=false` set karo (CI / non-interactive install ke liye).

Kab kaun sa choose karo (yaad rakhne ke liye):
- Shuru me: observer trial theek hai.
- Lambi use me: apni key ya plan.
- Privacy zyada chahiye to: apni key + `<private>` tags.

## 8. Reminder / Next step
- Jab upstream me naya version aaye, fork ko sync karo, phir ye guide dobara check karo ke install command badla to nahi.
- Agar memory kaam na kare: pehle Node version, phir plugin restart, phir upstream Troubleshooting section dekho.
