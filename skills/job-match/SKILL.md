---
name: job-match
description: Check how well a resume matches a job description with PokeBot, giving a match score out of 100, covered and missing keywords, and tailoring advice. Use when the user asks how well their resume fits a job posting, wants an ATS or keyword check against a job, or asks what their resume is missing for a specific job.
---

# Resume-to-job match with PokeBot

Use PokeBot's `match-resume-to-job` tool.

1. You need two texts from the user: their resume and the job description. Use what they pasted or attached in this chat, and ask for anything missing. Never write or guess either text.
2. Call `match-resume-to-job` with resume_text and job_description. If the user named the job title, pass it as target_job_title.
3. Show the result as PokeBot returned it: the match score, the covered and missing keywords, and the recommendations. Don't change PokeBot's score or add your own.
4. If the result has a link to the saved copy, share it.

## Saving

The result is saved to the user's PokeBot account by default. If the user asks not to save it, set save_to_account to false. The resume text itself isn't saved.

## Limits and errors

- If PokeBot returns a usage-limit message, show it to the user as it is, including its link, and don't retry.
- If PokeBot says the resume or the job description is missing, ask the user for it.

## If PokeBot isn't connected

If PokeBot's tools aren't available in this chat, tell the user how to turn them on, and in the same message offer to help without PokeBot instead:

1. Connect PokeBot from this plugin's **Connectors** tab, or from **Customize > Connectors**, and sign in with a PokeBot account. A free account works. On a Team or Enterprise plan, an Owner may need to add PokeBot first.
2. Turn PokeBot on for this chat with **+ > Connectors**. In Claude Code, run `/mcp` and sign in to pokebot instead.

If you help without PokeBot, don't present your own scores or advice as PokeBot's.
