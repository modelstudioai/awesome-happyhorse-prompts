# Contributing

🌐 **Language:** English · [🇨🇳 中文](Contributing.md)

We welcome high-quality HappyHorse 1.0 / 1.1 prompt cases, API tips, creative workflows, and documentation improvements.

## Submission Guidelines

- Keep cases curated; avoid duplicates.
- Prefer reusable prompt templates or API call examples.
- When updating the README, keep the structure consistent.
- Host video samples on GitHub user-attachments (`https://github.com/user-attachments/assets/...`) and keep them under 10 MB.

## Case Format

Each case should include:

1. **Title** — short scenario description.
2. **Prompt** — full prompt text (Chinese or English; you may keep the original language).
3. **Parameters** — model, resolution, duration, etc.
4. **Output** — link to the rendered video or image.

Example:

```markdown
### Case 1: Ancient-style fantasy scene

**Prompt:**
```
一位身穿白色长袍的仙子，站在云雾缭绕的山峰之上，衣袂飘动，远处仙鹤飞过...
```

**Parameters:** T2V-14B | 1080P | 10s

https://github.com/user-attachments/assets/xxxx-xxxx-xxxx
```

## How to Submit

1. Fork this repository.
2. Add your case to the matching `cases/*.md` file.
3. Open a Pull Request.

> **Localization note**: when contributing prompts in non-English languages, please keep the prompt body verbatim. If you also want it surfaced in the English mirror, add a short English **"Prompt intent"** block above the prompt that summarizes the scenario, control levers, and what to swap when adapting to other briefs — do *not* re-translate the prompt itself.

Thanks for contributing!
