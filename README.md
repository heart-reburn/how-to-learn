# How to Learn

A skill that coaches a learner through studying anything, using methods with strong evidence behind them: testing yourself, spaced review, explaining ideas back, and checking your own understanding. It works with Claude Code and other tools that read `SKILL.md` skills.

## What it does

The agent runs a repeating cycle:

1. **Place:** a 15-minute test finds the starting level (1 to 6).
2. **Set the bar:** it states what you must show to pass the level, before you study.
3. **Study:** sessions of practice, reading, and self-testing (60 minutes by default), logged in a progress file the agent reads each time.
4. **Check:** an oral teach-back, scored at about 80%.
5. **Rebuild:** you rewrite a one-page summary from memory.
6. **Advance:** pass, move up, and keep reviewing earlier levels.

It covers eight techniques: foundations (sleep, focus), retrieval practice, spaced repetition, elaboration, interleaving, metacognition, teach-back, and decision quality.

## Who it's for

Anyone studying a subject or building a skill who wants a coach that tests them instead of just explaining. It is not for quick factual questions; the agent answers those directly.

## Install

Claude Code, as a plugin:

```
/plugin marketplace add heart-reburn/how-to-learn
/plugin install how-to-learn@how-to-learn
```

Or copy the skill folder by hand:

```
cp -R skills/how-to-learn ~/.claude/skills/
```

Other tools that read `SKILL.md` folders: copy `skills/how-to-learn/` into that tool's skills directory.

## Example

> **You:** I have a biology exam in three weeks. Help me study cell division.
>
> **Coach:** First, a quick placement test. Close your notes and write everything you know about cell division for ten minutes.
>
> *(You write 6 facts.)*
>
> **Coach:** Good start. Now explain mitosis aloud as if to a 12-year-old.
>
> *(You stumble at how chromosomes separate.)*
>
> **Coach:** You start at Level 2: Explain. To pass, you need to explain why each phase happens, in your own words. This week: 4 sessions of 60 minutes. Session 1: make 10 cards on the phases, answer each before checking, then predict your score first.

## Evidence

The methods come from learning research: practice testing and spaced practice rated high-utility, and rereading, highlighting, and summarizing rated low (Dunlosky et al., 2013). Full sources are in [`skills/how-to-learn/references/techniques.md`](skills/how-to-learn/references/techniques.md).

The pass and drop thresholds are starting points, not research results, and the file says so.

## Repo layout

- `skills/how-to-learn/SKILL.md`: the skill.
- `skills/how-to-learn/references/`: placement test, levels, techniques, ground rules, progress-file format.
- `skills/how-to-learn/evals/`: trigger tests (should and should not load) and behavior tests (what the skill does once loaded).
- `scripts/validate.py`: checks frontmatter and file links (runs in CI). `scripts/run_evals.py` runs the evals with the Claude CLI.

## License

MIT. See [LICENSE](LICENSE).
