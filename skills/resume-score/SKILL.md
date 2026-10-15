---
name: resume-score
description: Score a resume with PokeBot, giving an overall score out of 100, scores by dimension, strengths, weaknesses and recommendations. Use when the user asks to score, grade, rate or review their resume or CV.
---

# Resume score with PokeBot

Use PokeBot's `analyze-resume` tool.

1. Get the resume text: the resume the user pasted or attached in this chat. If there isn't one, ask for it. Never write or guess resume content.
2. If the user also gave a job description and wants to know how well they fit that job, use `match-resume-to-job` instead.
3. Call `analyze-resume` with resume_text set to the full resume text.
4. Show the result as PokeBot returned it: the overall score, then the main strengths, weaknesses and recommendations. Don't change PokeBot's scores or add your own.
5. If the result has a link to the saved copy, share it.

## Saving

The result is saved to the user's PokeBot account by default. If the user asks not to save it, set save_to_account to false. The resume text itself isn't saved.

## Limits and errors

- If PokeBot returns a usage-limit message, show it to the user as it is, including its link, and don't retry.
- If PokeBot says no resume text was provided, ask the user for their resume.

## If PokeBot isn't connected

If PokeBot's tools aren't available in this chat, tell the user how to turn them on, and in the same message offer to help without PokeBot instead:

1. Connect PokeBot from this plugin's **Connectors** tab, or from **Customize > Connectors**, and sign in with a PokeBot account. A free account works. On a Team or Enterprise plan, an Owner may need to add PokeBot first.
2. Turn PokeBot on for this chat with **+ > Connectors**. In Claude Code, run `/mcp` and sign in to pokebot instead.

If you help without PokeBot, don't present your own scores or feedback as PokeBot's.
